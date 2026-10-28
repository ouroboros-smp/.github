# Security policy

Report security vulnerabilities in private. Do not open a public GitHub issue, and do not post the details in Discord.

## Reporting a vulnerability

Prefer GitHub private vulnerability reporting on the repository that contains the affected code.

1. Open that repository's **Security** tab.
2. Choose **Report a vulnerability**.

The same form is at `https://github.com/ouroboros-smp/<repository>/security/advisories/new`. Replace `<repository>` with the repository name, such as the mod, fork, bot, or website where the problem lives.

The report opens a private security advisory. Include the technical details, the impact, and any proof of concept, and keep the conversation in that advisory.

If private vulnerability reporting is turned off for that repository, do not describe the vulnerability in a public issue. Open a public issue that only asks a maintainer to enable private vulnerability reporting.

## Supported versions

Each repository supports security fixes for its current release. Older releases are unsupported unless that repository's own README or release notes name them as supported. Unreleased work on a development branch is not a supported version. A fork is covered for changes made in this organization, not for unmodified upstream code.

## Expected response

A report should receive an acknowledgement within 7 days. The next update is an assessment of the report. When a fix is needed, the fix and the public disclosure are coordinated through the GitHub security advisory.

Give the maintainers time to investigate before disclosing the vulnerability in public.
