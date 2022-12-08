# Introduction

TextMaster's bug bounty program is our way to reward security researchers for finding serious security vulnerabilities.

We look forward to working with all security researchers and strive to be respectful, always assume the best and treat others as peers. We expect the same in return from all participants. To achieve this, our team strives to:

* Reply to all reports
* Be as transparent as possible, answering all inquiries about our report decisions
* Award fair value bounties based on CVSS scores
* Only close reports as `Non Applicable` when the issue reported is listed in the [Known Issues](./#known-issues), [Ineligible Issues](./#ineligible-issues) sections or lacks evidence of a vulnerability
* Reward any report mistakenly closed as invalid if we later receive and reward the same bug reported by someone else. In these situations, we will reward both security researchers
* Pay the bounty difference to the duplicate reporter in case the new report demonstrates a higher CVSS score

## Submit Vulnerability Report

We've set up a [public GitHub repository](https://github.com/textmaster/bugbounty/security/advisories) to submit vulnerability reports.

Open a new draft security advisory and follow the templates, providing as much information as possible about the potential issue you have discovered. The more information you provide, the quicker TextMaster will be able to validate the issue.

If you haven't yet, please remember to review our [Security Policy](SECURITY.md) and [Disclosure Guidelines](disclosure-guidelines.md).

Use the built-in severity calculator to get your severity vector string. Note that currently, GitHub does not support Temporal and Environmental scores. Therefor, your severity score might be lowered down after submitting your draft according to our policy.

Follow these steps to submit a new report:

1. Go to our bug bounty public repository [https://github.com/textmaster/bugbounty](https://github.com/textmaster/bugbounty)
2. Click on the Security tab
3. Click on the Advisories sub-menu
4. Click on the New draft security advisory button
5. Fill in your report following the guidelines
6. Once you're satisfied with your report, click the Create draft security advisory button
