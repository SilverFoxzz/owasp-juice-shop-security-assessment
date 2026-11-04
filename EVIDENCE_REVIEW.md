# Portfolio evidence review — source-to-claim audit

**Source:** original 58-page *OWASP Report*, May 2026. **Portfolio scope:** academic lab review, not a professional penetration test. The screenshots below were extracted from the attached original document and cropped or pixel-level redacted for public use. The editable case study and README were written as secondary summaries; no tests were rerun.

| Asset | Source page / section | Supported interpretation | Do not claim |
|---|---|---|---|
| `01_sql_injection_login_input.png` | p. 9 / §2.3.2 | SQL-style input shown in lab login form | Credentials were obtained or data exfiltrated |
| `02_sql_injection_success_banner.png` | p. 10 / §2.3.2–2.3.5 | Juice Shop Login Admin challenge marked solved | Real-world compromise |
| `03_order_history_devtools.png` | pp. 17–18 / §3.3 | Authenticated order-history view and network capture | IDOR, cross-account access, missed server-side authorisation |
| `04_product_api_json_metadata.png` | p. 27 / §4.3.2 | Metadata present in product JSON response | Sensitive private records exposed |
| `05_verbose_express_error.png` | p. 27 / §4.3.2 | Express version and stack information in HTTP 500 page | Remote code execution or follow-on compromise |
| `06_weak_password_registration.png` | p. 36 / §5.3.1 | Registration form and minimum-length requirement; source text documents credential `12345` | Screenshot alone reveals the password value |
| `07_password_reset_confirmation.png` | p. 39 / §5.3.2 | Successful password reset response; source text describes `123456` | Third-party account takeover |
| `08_image_url_field.png` | pp. 48–49 / §6.3.2 | Lab URL entered in profile image form | Server fetched URL or contacted protected target |
| `09_profile_image_url_http_302.png` | pp. 48–49 / §6.3.2 | Browser POST to `/profile/image/url` and 302 redirect | SSRF proven; internal access |

The academic report’s author name and student number from its cover and running headers are **excluded** from the case study and repository. Lab test emails and a test security-question answer visible in selected screenshots have been **painted over at pixel level**. Browser bookmarks/tabs were cropped from the image-URL and verbose-error screenshots. The screenshot evidence retains the important application behaviour.

**Publication check:** Owner to review all assets and the case study before uploading to GitHub. The original 58-page report should remain private unless separately sanitized and its publication permitted.

## Interpretation, ownership and limits

- The case study has been revised to identify the actions documented in the original coursework: virtualised lab setup, manual test submissions, browser Network-panel inspection, finding interpretation and mitigation recommendations.
- The PDF includes **detail crops** of the same nine sanitised evidence screenshots. The repository’s `evidence/` directory retains the wider context crops; detail crops were not generated, retouched or filled in to create any new technical result.
- Source-page references were checked against the original 58-page document. Unverified hypotheses (cross-account access and SSRF) remain explicitly unverified.
- No additional vulnerabilities, external targets, retests, risk scores or remediation verifications are claimed.
- Before public posting, the project owner should still review the nine pictures and choose whether to show a public author name or username.
