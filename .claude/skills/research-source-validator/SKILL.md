---
name: "research-source-validator"
description: "Autonomously validates research sources based on several criteria, returning a verdict and detailed findings."
parameters:
  - name: "source_url"
    type: "string"
    description: "The URL of the research source to be validated."
    required: false
  - name: "source_text"
    type: "string"
    description: "The full text content of the research source to be validated (if no URL is available)."
    required: false
  - name: "claim_to_verify"
    type: "string"
    description: "The specific claim from the main paper that this source is being used to support. This will be used to verify if the source actually supports the claim."
    required: true
  - name: "reporting_format"
    type: "string"
    description: "The desired format for the validation report (e.g., 'verbose', 'summary', 'json'). Defaults to 'summary'."
    required: false
    default: "summary"
---

# Research Source Validator Skill

## Description
This skill automates the critical task of validating research sources. It systematically checks for peer-review status, publication recency, author credibility, potential biases, and the direct relevance of the source to a given claim.

## Functionality
The subagent autonomously performs the following checks:
1.  **Peer-Review Status**: Determines if the source is from a peer-reviewed journal or publication.
2.  **Publication Date Evaluation**: Assesses the recency of the publication, preferring newer sources unless historical context is explicitly required.
3.  **Author Credibility**: Evaluates the credentials and affiliations of the author(s).
4.  **Bias Flagging**: Identifies potential conflicts of interest, funding biases, or other forms of bias within the source.
5.  **Claim Support Verification**: Cross-references the provided `claim_to_verify` against the content of the source to determine if the source adequately supports the claim.

## Output
The skill returns a verdict (`accept`, `reject`, `escalate`) along with detailed findings based on the `reporting_format` specified.

## Example
**Input**: "Validate source for the claim: 'AI significantly improves student engagement in K-12 classrooms.' Source URL: 'https://example.edu/ai-in-k12-engagement.pdf'. Report format: 'verbose'"

**Output (example verbose format)**:
```
Verdict: Accept

**Validation Report for 'https://example.edu/ai-in-k12-engagement.pdf'**

**Claim to Verify**: "AI significantly improves student engagement in K-12 classrooms."

**1. Peer-Review Status**:
   - Status: Peer-reviewed (Published in "Journal of Educational Technology")

**2. Publication Date Evaluation**:
   - Date: 2023-08-15 (Recent - less than 2 years old)

**3. Author Credibility**:
   - Author(s): Dr. Jane Doe (Professor of Educational Psychology, University of XYZ), Dr. John Smith (Lead Researcher, EdTech Institute)
   - Credentials: Highly credible in the field of educational technology.

**4. Potential Bias**:
   - Identified Bias: None evident. Funding declared from an independent research grant.

**5. Claim Support Verification**:
   - Finding: The study presents robust quantitative data demonstrating a statistically significant increase in student engagement metrics in AI-integrated classrooms compared to control groups. The findings directly support the claim.
```