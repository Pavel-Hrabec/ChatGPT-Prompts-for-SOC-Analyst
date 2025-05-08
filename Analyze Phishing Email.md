Analyze the provided email and assess the likelihood of it being a phishing attempt.

The analysis should include:
1. An evaluation of specific sections of the email that indicate phishing (e.g., sender address, links, tone, urgency, request for personal information).
2. A list of recommended verification checks to confirm the legitimacy of the email.
3. A direct attempt to perform these checks when possible (e.g., checking domain reputation, link validity).
4. An overall likelihood rating (e.g., High, Moderate, Low) of the email being phishing.

# Steps

1. Extract and analyze components of the email, such as:
   - **Sender Information**: Check for mismatched domain names, unusual sender addresses, or typos.
   - **Email Content**: Review tone, language, grammar, and urgency.
   - **Links**: Inspect hyperlinks for suspicious domains.
   - **Attachments**: Identify suspicious or unusual file types or presence.
   - **Requests**: Look for sensitive requests like login information, payment details, or account credentials.

2. Highlight and explain suspicious elements found in the email.

3. Provide a list of recommended verification steps:
   - Cross-validate sender domain against official sources (e.g., corporate website).
   - Check link destinations' reputation via trusted tools.
   - Verify email headers for anomalies, if provided.
   - Contact the supposed sender using official channels.

4. Attempt basic verifications yourself, when possible, such as analyzing links or cross-checking sender domains.

5. Summarize findings, providing:
   - A clear likelihood assessment (High/Moderate/Low).
   - A rationale for the assessment based on the analysis.
   - Actionable steps to confirm legitimacy.

# Output Format

The output should be structured in detailed bullet points or paragraphs:
- **Likelihood of Phishing**: Overall assessment (High/Moderate/Low).
- **Highlighted Suspicious Sections**: Specific quotes or sections from the email and why they are suspicious.
- **Verification Checks**: Steps the user should take to confirm validity (or results of checks already performed, if possible).
- **Final Recommendation**: Conclude whether the user should proceed cautiously, ignore, or report the email.

# Example

### Likelihood of Phishing:
High

### Highlighted Suspicious Sections:
- **Sender Email Address**: `service-support@paypall-security.com` (misspelled "paypal").
- **Tone and Urgency**: "Your account will be frozen in 24 hours if no action is taken. Click here to secure your account." (uses urgency to provoke action).
- **Suspicious Link**: Hovering over `http://secure.paypal.com-login.net` reveals a non-official PayPal domain.
- **Request**: "Enter your login credentials to verify your account" (unnecessary for legitimate services).

### Verification Checks:
1. **Domain Analysis**: The sender's domain `paypall-security.com` does not match PayPal's official site `paypal.com` (Result: Domain likely fake).
2. **Link Inspection**: Link redirects to a domain unrelated to PayPal (Result: Domain flagged as phishing).
3. **Grammar Check**: Spelling mistakes in the email suggest it is not professionally written.

### Final Recommendation:
Do not interact with the email. Report it to PayPal's official phishing email report (`phishing@paypal.com`) and delete it immediately.

# Notes

- Ensure to provide actionable insights, even if unable to perform certain verification. For example: "Check the full headers of the email using [steps for header extraction]."
- Clearly mark when assumptions are made due to incomplete information. Example: "Based on sender name alone, further verification is necessary."

Email to analyze:

