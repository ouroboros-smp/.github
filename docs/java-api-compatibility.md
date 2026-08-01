# Java API compatibility workflow

`java-api-compatibility.yml` gives organization repositories one standard CI
entrypoint for API and release contracts. Each caller owns a Gradle
`apiCompatibilityCheck` task appropriate to its API, while the shared workflow
owns checkout, Java setup, package credentials, tag/version validation, and
report collection.

```yaml
jobs:
  api-contract:
    uses: ouroboros-smp/.github/.github/workflows/java-api-compatibility.yml@main
    with:
      gradle_tasks: ":chorus-api:check :chorus-api:apiCompatibilityCheck"
      version_property: mod_version
      tag_prefix: v
      report_paths: chorus-api/build/reports/japicmp.*
    secrets: inherit
```

API repositories must expose an `apiCompatibilityCheck` task that compares the
current artifact with the oldest supported baseline in its current compatibility
series. A new major or minor compatibility series sets its own version as the
initial baseline; subsequent releases compare against that immutable package.

For private GitHub Packages, grant every consumer repository read access under
the package's settings. Callers use their repository-scoped GITHUB_TOKEN;
default CI dependency resolution must not include Maven Local, which could hide
a missing permission or substitute a mutable artifact for the published version.
