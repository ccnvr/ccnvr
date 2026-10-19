# Security Policy

## Supported versions

Only the latest release receives security fixes. Please reproduce any issue
against the most recent version listed on the
[Releases](https://github.com/ccnvr/ccnvr/releases) page before reporting.

## Reporting a vulnerability

**Do not open a public issue for security problems.**

Use GitHub's private reporting instead:

1. Go to the [Security tab](https://github.com/ccnvr/ccnvr/security/advisories/new)
   and open a draft advisory, or
2. Contact us through https://ccnvr.com/docs/contact and state that the
   report is a security issue.

Please include:

- CCNVR version (visible in **System info**)
- Deployment method (Windows / Linux / Docker) and OS version
- Affected component (web console, RTSP/ONVIF/GB28181 stack, media server,
  license handling)
- Steps to reproduce, and a proof of concept if you have one
- Whether the issue is already public

## What to expect

- Acknowledgement within 3 business days
- An assessment and, where applicable, a fix timeline
- Credit in the release notes once a fix ships, unless you ask to stay
  anonymous

## Scope

In scope: the CCNVR server, its web console, bundled media server, and the
default configuration shipped in release packages.

Out of scope: vulnerabilities in third-party cameras or NVR hardware,
issues that require an already-compromised host, and reports produced solely
by automated scanners without a demonstrated impact.
