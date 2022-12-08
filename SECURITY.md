# Security Policy

### Third Party Applications

Vulnerabilities found in TextMaster third party applications should be reported to the application owner(s). You should only report vulnerabilities in TextMaster third party applications to TextMaster under this program if you do not receive a satisfactory response from the owner(s).

### Eligibility

The scope of the bug bounty program is limited to these scopes. Valid vulnerabilities on any domain not explicitly listed in scope will be accepted, but are ineligible for a reward.

All software components that are used within the TextMaster application may be exploited in your attack, including bugs in the Ruby interpreter (MRI), the Ruby on Rails framework, as well as third party libraries that we use (such as Ruby gems).

{% hint style="info" %}
**Tips:** Bugs in third party components only qualify if you can prove that they can be used to successfully attack TextMaster.
{% endhint %}

If you need further clarification of the rules or scope of our bug bounty program, you may email us at [bounty@textmaster.com](mailto:bounty@textmaster.com).

### Bounty Rewards

Our maximum bounty reward is `$5000` for a critical vulnerability.

Bounty amounts will be determined with [CVSS 3.0](https://www.first.org/cvss/calculator/3.0) using Base, Temporal and Environment scores. In most cases, we will only triage and reward vulnerabilities with a CVSS score greater than 0. A CVSS score under 3 will result in a $50 bounty. Scores greater than or equal to 3 will be determined by the calculator.

In rare cases, we may choose to accept and award a bonus for an issue with a CVSS score of 0 when we see a high potential for future security impact, and make a change as a result of the report.

The formula used to calculate the bounty reward can be expressed as follows where `b` is the bounty amount, `C` is the CVSS score, and `N` is a constant that creates a direct correlation between `bmax` and `Cmax:`

$$
∀C(0≤C≤10)
$$

$$
n = 3.0
$$

$$
N = bmax / (Cmax)^n
$$

$$
b=N×(C^n)
$$

Which gives the following bounty amounts for various CVSS scores:

| CVSS Score | Bounty Amount ($) |
| ---------- | ----------------- |
| 1          | ~~5~~ -> 50       |
| 2          | ~~40~~ -> 50      |
| 3          | 135               |
| 4          | 320               |
| 5          | 625               |
| 6          | 1080              |
| 7          | 1715              |
| 8          | 2560              |
| 9          | 3645              |
| 10         | 5000              |

While our bounty table states the minimum bounty per severity, CVSS scores for non-core properties listed in scope will be determined with Environment Score modifiers set to Low for `Confidentiality`, `Integrity` and `Availability` requirements.

_TextMaster Core_ includes `app.textmaster.com` and `api.textmaster.com`. All other scopes are part of the _Non-Core_ category.

{% hint style="info" %}
**Tips:** More detailed information on CVSS can be found in the specification document: [https://www.first.org/cvss/v3.0/specification-document](https://www.first.org/cvss/v3.0/specification-document)
{% endhint %}

### Participation

The following rules **must** be followed for participating in this program and deem any rewards:

* This program is not open to minors, individuals who are on sanctions lists, or who are in countries (e.g. Cuba, Iran, North Korea, Sudan and Syria) on sanctions lists
* The use of commercial scanners is prohibited (e.g. Nessus)
* Rules for reporting an issue must have been followed
* Do not disclose any issues publicly before they have been resolved
* Do not contact TextMaster's support by any means in relation to this bounty program (pre-validating reports, testing against support, asking for updates, etc.). Use the [bounty@textmaster.com](mailto:bounty@textmaster.com) dedicated email address instead
* You are not an employee of TextMaster; employees should report bugs to the internal bug bounty program
* TextMaster reserves the right to modify the rules for this program or deem any submissions invalid at any time. TextMaster may cancel the bug bounty program without notice at any time
* You hereby represent, warrant and covenant that any content you submit to TextMaster is an original work of authorship and that you are legally entitled to grant the rights and privileges conveyed by these terms. You further represent, warrant, and covenant that the consent of no other person or entity is or will be necessary for TextMaster to use the submitted content
* By submitting content to TextMaster, you irrevocably waive all moral rights which you may have in the content
* All content submitted by you to TextMaster under this program is licensed under the [MIT License](https://opensource.org/licenses/MIT)
* You must report any discovered vulnerability to TextMaster as soon as you have validated the vulnerability
* Failure to follow any of the foregoing rules will disqualify you from participating in this program

{% hint style="info" %}
**Tips:** Make sure to review our [Disclosure Guidelines](disclosure-guidelines.md).
{% endhint %}

### Scope

#### Eligible

The following scopes are eligible to the program, but not necessarily to a bounty reward. The ones listed at the top have precedence over of the ones listed after.

| Scope                | Env      | Severity                                  | Reward                                     |
| -------------------- | -------- | ----------------------------------------- | ------------------------------------------ |
| `app.textmaster.com` | Core     | <mark style="color:red;">Critical</mark>  | <mark style="color:green;">Eligible</mark> |
| `api.textmaster.com` | Core     | <mark style="color:red;">Critical</mark>  | <mark style="color:green;">Eligible</mark> |
| `textmaster.com`     | Non-core | <mark style="color:orange;">Medium</mark> | <mark style="color:red;">Ineligible</mark> |
| `*.textmaster.com`   | Non-core | <mark style="color:orange;">Medium</mark> | <mark style="color:red;">Ineligible</mark> |
| 3rd party apps       | Non-core | <mark style="color:green;">Low</mark>     | <mark style="color:red;">Ineligible</mark> |

#### Ineligible

The following scopes are not eligible to the program.

| Scope                          | Description                                                                                                                                                            |
| ------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `docs.textmaster.com`          | Operated by a third party                                                                                                                                              |
| `images.textmaster.com`        | Operated by a third party                                                                                                                                              |
| `storage-proxy.textmaster.com` | TextMaster allows clients to upload any file they want on our storage network. Being able to upload a file is not a vulnerability, this is the intended functionality. |
| `status.textmaster.com`        | Operated by a third party                                                                                                                                              |
| `*.subtitly.io`                |                                                                                                                                                                        |
| `*.textmaster.co`              |                                                                                                                                                                        |
| `*.textmaster.io`              |                                                                                                                                                                        |
| `*.textmasters.com`            |                                                                                                                                                                        |
| Other                          |                                                                                                                                                                        |
| Spam                           |                                                                                                                                                                        |

### Known Issues

The following vulnerabilities have already been reported and triaged, and won't be fixed. Reporting them will not be eligible for a bounty reward and will be closed as `Not Applicable`.

* [Tab nabbing](https://en.wikipedia.org/wiki/Tabnabbing)
* Password reset tokens not expiring when changing email address
* Reflected XSS that requires full control of an HTTP header, such as `Referer`, `Host`, etc.
* CSRF for Login or Logout - Any login / logout CSRF will be ineligible unless it is chained together with another vulnerability to demonstrate impact

### Ineligible Issues

TextMaster does not consider the following to be eligible vulnerabilities under this program. In most cases, these issues will be closed as `Not Applicable`.

* Distributed Denial of Service
* Content spoofing
* Social Engineering, including phishing
* Email flooding
* Unconfirmed reports from automated vulnerability scanners
* Disclosure of server or software version numbers
* Generic examples of `Host` header attacks without evidence of the ability to target a remote victim
* Reports related to permitted password strength
* Perceived security weaknesses without evidence of the ability to target a remote victim. For example, credentials are transmitted in POST body as plain text, missing rate limits, brute forcing without demonstrating impact, etc.
* Self-XSS without a reasonable attack scenario. In general, we accept these reports when there are a maximum of two steps required. For example, pasting a malicious payload into an editor and then clicking to preview it would be two steps.
* Open Redirects without demonstrating additional security impact
* Reports exploiting the behavior of, or vulnerabilities in, outdated browsers
* False reports, or reports lacking evidence of a vulnerability
* Reports of broken links or unclaimed social media accounts (unless chained with an impactful exploit)

### Miscellaneous

You are responsible for any tax implications resulting from payouts, depending on your country of residency and citizenship. TextMaster reserves the right to cancel this program at any time, and the decision to pay a bounty is entirely at our discretion.

Testing and submission must not violate any law, or disrupt or compromise any data that is not your own. There may be additional restrictions on your ability to submit content or receive a bounty, depending on your local laws.

TextMaster considers activities conducted consistent with this program to constitute “authorized” conduct under the Computer Fraud and Abuse Act. If legal action is initiated by a third party against you, and you have fully complied with this program, TextMaster will take steps to make it known, either to the public or to the court, that your actions were conducted in compliance with the TextMaster policy.

Upon TextMaster's request, you will execute, acknowledge and delivery such further instruments, and will otherwise cooperate and do all other acts as may be necessary or appropriate in order to perfect or carry out the purpose and intent of these terms.

The formula used to calculate the bounty amount is the courtesy of [https://github.com/EdOverflow/bounty-formula](https://github.com/EdOverflow/bounty-formula) and is under MIT license.
