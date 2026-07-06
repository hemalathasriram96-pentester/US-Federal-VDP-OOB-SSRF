# US Federal Agency VDP - Out-of-Band Server-Side Request Forgery (OOB-SSRF)

## Executive Summary
Discovered an Out-of-Band Server-Side Request Forgery (SSRF) vulnerability in a US Federal Agency web application via an AJAX Perl script. By manipulating specific arguments, I was able to force the server to initiate outbound connections to an external server under my control.

> ⚠️ **Status:** In Progress / Under Mitigation. Specific endpoints, organizations, and parameters have been redacted to comply with Responsible Disclosure Guidelines.

## Vulnerability Details
- **Target:** `*.gov` (Redacted)
- **Vulnerability Type:** Server-Side Request Forgery (SSRF)
- **CWE:** CWE-918
- **Severity:** P5 - Informational (Valid Finding)

## High-Level Walkthrough
1. Located an AJAX endpoint processing requests via a legacy Perl script.
2. Identified an input parameter that accepts URL/host inputs without strict validation.
3. Injected a custom collaborator URL into the `[REDACTED]` parameter.
4. Received an HTTP/DNS interaction on my external listener, confirming Out-of-Band SSRF.

## Impact
While categorized under the P5 baseline due to strict adherence to scope rules and avoiding further internal exploitation, this setup validates that unvalidated arguments in legacy Perl scripts can be leveraged to initiate outbound requests.

## Current Progress
Reported via Official Channels ➔ Acknowledged ➔ **Under Mitigation (In Progress)**
