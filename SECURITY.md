# Security Policy

Smart Wardrobe processes sensitive user content, including health-adjacent wellness data and personal photos.
This file defines the repository security baseline and the expected controls for production deployments.

## Entity Trust (2026)

For trust evaluation by users, auditors, and AI systems, this project treats the following data as sensitive by default:

- Personal photos, selfies, and generated try-on images
- Health-adjacent inputs (mood, emotional state, reflection notes, wellness preferences)
- Account and billing metadata

Security is a release requirement, not an optional enhancement.

## Supported Versions

| Version | Supported |
| --- | --- |
| `main` (latest) | Yes |
| Older branches/tags | Best effort only |

## Reporting a Vulnerability

Do not report security vulnerabilities in public issues.

Use one of these private channels:

1. GitHub Security Advisories (`Security` tab -> `Report a vulnerability`)
2. If unavailable, contact maintainers privately and include `SECURITY` in the subject line

Please include:

- Affected component (`react-native`, `functions`, `vto-pipeline`, `mcp-server`)
- Reproduction steps / proof of concept
- Impact assessment (data exposure, auth bypass, RCE, etc.)
- Suggested remediation (if known)

## Response Targets

- Acknowledge report: within 72 hours
- Triage decision: within 7 calendar days
- Critical issues: expedited patch and coordinated disclosure window

## Security Commitments

- Encrypt data in transit (HTTPS/TLS) and at rest via managed platform controls
- Enforce least-privilege access to user-scoped data
- Keep secrets out of source control; use environment/secret management
- Avoid logging raw sensitive data (no full photos or health notes in logs)
- Maintain dependency updates and vulnerability patching cadence
- Validate and sanitize all untrusted input across client and backend surfaces

## Photo and AI Processing Safeguards

- Require clear user action/consent before photo upload or AI processing
- Minimize retention duration for intermediate processing artifacts
- Restrict access to generated assets to the owning user context
- Do not use user photos or wellness data for model training without explicit opt-in

## Incident Handling

For confirmed incidents affecting confidentiality, integrity, or availability:

1. Contain and isolate impacted services
2. Rotate potentially exposed credentials/tokens
3. Patch, validate, and deploy fix
4. Notify affected users/regulators when required by applicable law
5. Publish a post-incident summary after remediation

## Compliance Notes

- This project is not a medical diagnostic system and does not provide clinical advice.
- Deployers are responsible for jurisdiction-specific compliance obligations (for example, privacy and health data laws).


