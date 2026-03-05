# 06-A: DIGITAL FORENSICS ADDENDUM: EMAIL INFRASTRUCTURE TAMPERING

**Addendum to Section 06: Intelligence Architecture**

**Version 1.0, 5 March 2026**

**Classification: Evidence, Chain of Custody Maintained**

---

## How to Read This Document

This document presents forensic evidence that the victims' email system was compromised at the server level by an actor with administrative access to Microsoft's infrastructure. The evidence is technical, but the concepts are straightforward. Every technical term is explained the first time it appears. The reader does not need a background in computer science to follow the analysis.

The document is structured as follows:

1. **What we found** (the forensic evidence, in plain language)

2. **Why it matters** (what it proves about state-level access)

3. **How email systems work** (the background needed to understand the evidence)

4. **The detailed forensic analysis** (for technical reviewers)

5. **The self-concealing architecture** (how TC Notes produce undetectable evidence tampering)

6. **The Disclosure Review Document and the Hotmail trap** (how the TC Note connects to the civil litigation)

7. **Can we prove an earlier modification existed?** (recovery of overwritten evidence)

8. **Evidentiary requests** (what a subpoena to Microsoft would reveal)

---

## Section 1: What We Found

### The Email

On 8 November 2023, Nicola McNamee forwarded an email thread to her partner Brian Spector. The thread was a conversation between Nicola and a cosmetic surgery clinic in Lithuania called Nordesthetics, running from 30 October to 8 November 2023. The conversation is ordinary: Nicola was inquiring about surgery, sending photos, sharing medical documents.

The email had five attachments:

1. A letter from Dr. Shaumik Adhya describing a cardiology consultation on 9 May 2023

2. A drug avoidance list for Brugada Syndrome

3. A drug avoidance list for Long QT Syndrome

4. A personal photo (IMG_4928.HEIC)

5. A personal photo (IMG_4929.HEIC)

### The Problem

**The cardiology consultation on 9 May 2023 never happened.** The hospital's own internal records contradict it. Administrative notes show staff leaving voicemails for a patient who was supposedly sitting in the clinic that evening. Follow-up calls were made the next morning to a patient who had allegedly attended the previous night. The appointment booking ID does not match the date field. The letter from this non-existent consultation is a fabrication. (Full analysis in Section 04 of the main submission.)

**The fabricated letter was attached to a real email.** Nicola's correspondence with Nordesthetics is genuine. But someone added a document from a consultation that never happened into this email, making it appear that Nicola herself possessed and was distributing the fabricated letter.

### The Forensic Evidence

Every email attachment carries two hidden timestamps that are not visible to the user but are embedded in the email's internal structure:

- **Creation-date**: When the attachment was first added to the email

- **Modification-date**: When the attachment was last changed

Here is what those timestamps show:

| Attachment | Creation Date | Modification Date |
|---|---|---|
| Dr. Adhya letter (fabricated) | 4 Nov 2023, 07:08:16 | **16 Mar 2024, 21:56:26** |
| Brugada drug list | 4 Nov 2023, 07:08:16 | **16 Mar 2024, 21:56:26** |
| Long QT drug list | 4 Nov 2023, 07:08:17 | **16 Mar 2024, 21:56:26** |
| Photo IMG_4928 | 4 Nov 2023, 07:14:17 | **16 Mar 2024, 21:56:26** |
| Photo IMG_4929 | 4 Nov 2023, 07:14:17 | **16 Mar 2024, 21:56:26** |

All five attachments show a modification date of **16 March 2024 at 21:56:26 GMT**. All five. The same second.

The email was sent on 8 November 2023. The attachments were last modified four and a half months later.

**A user does not go back to a forwarded email from November and modify all five attachments at the exact same second in March. This is not human behavior. This is a server-side operation.**

---

## Section 2: Why This Matters

### What a Simultaneous Modification-Date Means

When Microsoft's email system (Exchange Online) modifies a stored email, for example by adding an attachment or changing the message body, it rebuilds the entire email from its internal database representation into the standard email format (called MIME). During this rebuild, it stamps a new modification-date on every attachment in the message. This is why all five attachments have the same modification-date to the second: the email was rebuilt in a single operation.

This type of operation requires one of two things:

1. **Administrative access to the email account**, using Microsoft's management tools or programming interfaces (called APIs), or

2. **Direct access to the email infrastructure**, compelled by a legal instrument served on Microsoft

Normal users do not have the ability to modify emails that have already been sent and delivered. Once an email lands in your inbox, you can delete it, move it, or flag it, but you cannot change its attachments or body content. The modification we observe here was performed at a level above the normal user: at the server level, where the email is stored.

### The Timing: 16 March 2024

The modification date of 16 March 2024 is significant for three reasons:

1. **15 March 2024**: One day earlier, Lilia Severina, an identified APT29 operative deployed malware against Nicola McNamee's devices **ON A WORK CALL** when she compelled her to open a URL she knew would load surveillance malware on her computer. This is documented in the forensic reports included in a parallel EEA filing described in 01. The email modification and the malware deployment occurred within 24 hours of each other.

2. **December 2023**: Three months earlier, the planned murder of Nicola McNamee in Istanbul was disrupted when Dr. Ercan Karacaoglu ordered an independent echocardiogram that disproved the fabricated cardiac diagnoses. (Full analysis in Section 04.)

3. **Late April 2024**: Six weeks later, the civil litigation Spector v. Severina (BL-2024-000648) was filed. The modified email, with the fabricated Adhya letter now embedded in a legitimate correspondence thread, would appear in any email production or discovery process as evidence that Nicola herself had been distributing the fabricated consultation letter.

### The Two-Modification Theory

The 16 March 2024 date may not be the first time this email was modified. There is reason to believe an earlier modification occurred before December 2023, and that the March 2024 modification was performed to overwrite the evidence of the earlier tampering.

Here is the logic:

The fabricated Adhya letter describes a consultation on 9 May 2023 and contains drug avoidance instructions for surgery. Nicola was planning elective surgery in Istanbul for December 2023. For the fabricated medical narrative to function (see Section 04 of the main submission), Nicola needed to have this letter in her possession before she traveled. The letter needed to be something she believed was genuine, something she would carry to Istanbul and share with the surgical team.

If the letter was planted in her email before December 2023, then the original modification-date on the attachments would have been a date in late 2023, before the surgery. That date would be forensic proof that the email was tampered with before the planned murder, connecting the email modification to the kill operation.

After the murder attempt failed in December 2023, the perpetrators had a problem: the server-side modification timestamps pointed to a date before the failed murder. That evidence needed to be cleaned. On 15 March 2024, they deployed malware against Nicola's devices (providing a plausible alternative explanation for any account access). On 16 March 2024, they modified the email again, overwriting the previous modification-dates with the new timestamp.

The March 2024 date is not the crime. It is the cover-up of the crime. The original modification, the one that planted the fabricated letter before Nicola traveled to Istanbul, is the act that connects the email tampering to the attempted murder.

### Why This Points to a State Actor

Modifying an email on Microsoft's Exchange Online servers is not something a private individual can do, even a skilled hacker. It requires either:

1. **Compromise of the Microsoft 365 tenant's administrative account**, which would be logged in Microsoft's audit systems, or

2. **An OAuth application with mailbox write permissions**, which would require either the tenant administrator's consent or a method of bypassing consent (which itself requires administrative or infrastructure-level access), or

3. **A legal instrument served on Microsoft**, compelling the company to provide the access. In the United Kingdom, this instrument is called a **Technical Capability Notice** (TCN), issued under Section 253 of the Investigatory Powers Act 2016. A TCN can compel a communications provider to maintain the technical capability to give effect to interception warrants. In practice, this means Microsoft can be legally required to provide write access to a specific email tenant, including the ability to insert, modify, or delete email messages.

The third option is the most consistent with the evidence for the following reason: it explains why the modification occurred in a way that is self-concealing.

---

## Section 3: How Email Systems Work (Background)

This section explains the technical concepts needed to understand the forensic evidence. Readers familiar with email infrastructure may skip to Section 4.

### What is Exchange Online?

Microsoft Exchange Online is the email server that powers Microsoft 365 (formerly Office 365). When a business or individual subscribes to Microsoft 365 and uses an email address like `nic@drey.fi`, their emails are stored on Microsoft's servers in data centers around the world. The email is not stored on the user's computer. The user's computer (running Outlook, for example) downloads a copy of the email for display, but the authoritative version lives on Microsoft's server.

### What is a Tenant?

A "tenant" is Microsoft's term for a customer's dedicated space on their servers. The `drey.fi` domain has a tenant with the identifier `1d280f39-236d-4896-bf98-cd0419803c06`. Every email, every document, every user account associated with `drey.fi` lives inside this tenant.

### What is the Microsoft Graph API?

The Graph API is Microsoft's programming interface. It allows software to interact with Microsoft 365 data, including emails, calendars, and files. With the right permissions, the Graph API can read emails, send emails, modify emails, add attachments to existing emails, and delete emails.

Critically, the Graph API can modify emails that have already been sent and delivered. A normal user interacting with Outlook cannot do this. But software using the Graph API with administrative permissions can.

### What is MIME?

MIME (Multipurpose Internet Mail Extensions) is the standard format for email messages. When you receive an email with attachments, the email is stored internally as a MIME document: a structured text file that contains the message body and the attachments, all encoded together. Each attachment is a separate "part" of the MIME document, and each part carries metadata including filenames, content types, creation-dates, and modification-dates.

### What Happens When an Email is Modified via API?

When software modifies an email through the Graph API (for example, by adding an attachment), Microsoft's Exchange system does the following:

1. Updates the message in its internal database

2. Regenerates the MIME representation of the entire message

3. During regeneration, stamps a new `modification-date` on every MIME part (every attachment)

4. The previous modification-dates are overwritten. They are not preserved in the MIME output.

This is why all five attachments in the Nordesthetics email have the same modification-date: the email was modified through a single API operation, and Exchange regenerated the entire MIME structure, stamping every part with the same timestamp.

### What is DKIM?

DKIM (DomainKeys Identified Mail) is a cryptographic signature that email servers attach to outgoing messages. It works like a wax seal on a letter: it proves the message came from the claimed sender and has not been altered in transit.

The Nordesthetics email has no DKIM signature:

```
authentication-results: dkim=none (message not signed)
 header.d=none;
 dmarc=none action=none header.from=drey.fi;
```

For an email sent within a Microsoft 365 tenant (from `nic@drey.fi` to `brian@drey.fi`), the absence of DKIM is not conclusive on its own, as internal messages may not always be DKIM-signed. However, it means there is no cryptographic proof that the message has not been modified since it was sent. If the message had been DKIM-signed, any server-side modification would have broken the signature, creating visible evidence of tampering. The absence of DKIM means the modification left no cryptographic trace.

### What is a Technical Capability Notice?

Think of it this way. Your email is not on your computer. It is on Microsoft's computer, in a data center. Microsoft controls that computer. You are a guest in their building.

Now imagine the UK government walks into Microsoft's building and says: "We need you to build us a back door into this person's email. Not just to read it. We need to be able to change it, add things to it, and delete things from it. And you are not allowed to tell the person. You are not allowed to tell anyone. If you refuse, you face criminal prosecution."

That is a Technical Capability Notice.

Under UK law (the Investigatory Powers Act 2016, Section 253), the Secretary of State can issue a Technical Capability Notice (TCN) to any communications provider: Microsoft, Google, Apple, or any company that handles electronic communications. The TCN does not target a specific person. It targets the company. It compels the company to build and maintain the technical systems needed to comply with future warrants. The TCN builds the back door. A separate warrant opens it.

In the context of email, a TCN served on Microsoft requires the company to maintain the ability to:

- Read emails in a specified tenant

- Modify emails in a specified tenant (change content, alter attachments)

- Insert new emails into a mailbox (emails the user never sent or received)

- Delete emails from a mailbox

- Provide these capabilities without alerting the tenant administrator or users

### How a Warrant is Obtained

The UK uses a "double lock" system to authorize interception warrants:

1. **Political authorization.** The Secretary of State (a senior government minister) personally authorizes the warrant. This is a political decision, not a judicial one.

2. **Judicial review.** An independent Judicial Commissioner (a senior judge) reviews and approves the warrant. This is the judicial check.

Both approvals are required. In theory, the Judicial Commissioner provides independent oversight. In practice, the Commissioner reviews the case on paper, without hearing from the target, without adversarial argument, and without the target ever knowing the warrant exists. The target has no opportunity to challenge the warrant before it takes effect.

### Warrant Duration and Renewal

- **Standard targeted warrants:** Valid for **6 months** from the date of issue, renewable indefinitely by the same double lock process.

- **Bulk personal dataset warrants:** Valid for **12 months** (extended from 6 months by the Investigatory Powers (Amendment) Act 2024).

- **Urgent warrants:** If the government claims urgency, the Secretary of State can authorize a warrant without prior judicial approval. The warrant takes effect immediately but is only valid for **5 working days** unless a Judicial Commissioner subsequently approves it. This means the government can obtain write access to a target's email within hours, with judicial review happening after the fact.

### How Fast Can Access Be Activated?

Once Microsoft receives a valid warrant backed by an existing TCN, the technical capability is already in place. The TCN required Microsoft to build the infrastructure in advance. The warrant simply activates it for a specific target. Access can be enabled in minutes, not days. There is no delay for "building" anything. The back door already exists. The warrant is the key.

### The Secrecy Obligation

The TCN and all warrants issued under it are classified. Microsoft is legally prohibited from disclosing their existence to:

- The target (you)

- Your lawyers

- Any court, including the court hearing your civil litigation

- Any foreign government, including the United States

- The public

If Microsoft refuses to comply or discloses the TCN, the company faces criminal prosecution under UK law. If Microsoft wants to challenge the TCN, it has **28 days** to request a review, and the review process can take up to **180 days**. During that entire period, Microsoft must comply with the notice.

### What This Means in Practice

The UK government can compel Microsoft to provide write access to any email account hosted on Microsoft's servers. This includes Microsoft 365 business accounts (like brian@drey.fi and nic@drey.fi) and consumer accounts (like bps1968@hotmail.com). The access is invisible to the account holder. Microsoft cannot tell anyone it exists. And the warrant can be obtained within hours under urgent provisions.

The account holder opens Outlook and sees their inbox. Everything looks normal. They have no way of knowing that someone has added an attachment to an email they received months ago, or inserted a document they never sent, or deleted a message they need. The back door is silent. The warrant is secret. Microsoft is gagged. The target is blind.

---

## Section 4: Detailed Forensic Analysis

### 4.1 Email Header Analysis

**File:** `FW_ Nordesthetics Clinic in Lithuania - Mommy Makeover - Photos.eml`

| Header Field | Value | Significance |
|---|---|---|
| From | Nicola McNamee `<nic@drey.fi>` | Sender |
| To | Brian Spector `<brian@drey.fi>` | Recipient (same tenant) |
| Date | Wed, 8 Nov 2023 08:24:58 UTC | Date of forward |
| Message-ID | `<LO4P265MB70793248ACEACD16875FA88AB5A8A@LO4P265MB7079.GBRP265.PROD.OUTLOOK.COM>` | Unique message identifier |
| Tenant ID | `1d280f39-236d-4896-bf98-cd0419803c06` | Microsoft 365 tenant for drey.fi |
| Auth Mechanism | 04 (MAPI) | Message submitted via MAPI (Outlook client) |
| DKIM | none (message not signed) | No cryptographic signature |
| DMARC | none | No domain authentication |
| Mailbox Type | HOSTED | Exchange Online (cloud-hosted) |
| Traffic Type | Email | Standard email, not calendar/contact |

### 4.2 Routing Chain

The email traversed five hops:

| Hop | Server | Timestamp | Protocol |
|---|---|---|---|
| 5 (origin) | LO4P265MB7079 (loopback) | 8 Nov 2023 08:24:59 | MAPI id 15.20.6954.028 |
| 4 | LO4P265MB7079 to LO6P265MB6907 | 8 Nov 2023 08:24:59 | SMTP (TLS 1.2) |
| 3 | LO6P265MB6907 to CWLP265MB6136 | 8 Nov 2023 08:25:01 | HTTPS |
| 2 | Gmail API (evidence preservation) | 25 Apr 2025 10:34:50 | HTTPREST |
| 1 | Gmail delivery | 25 Apr 2025 07:34:52 | SMTP |

Hops 3 through 5 are entirely within Microsoft's GBRP265.PROD.OUTLOOK.COM infrastructure (UK-region Exchange Online servers). Hops 1 and 2 reflect the message being forwarded to Gmail on 25 April 2025 as part of evidence preservation.

The routing chain is consistent with a legitimate internal Exchange message. The modification we identify did not alter the routing headers, because the modification occurred after delivery, on the stored message, not during transit.

### 4.3 Attachment Forensics: The Modification-Date Anomaly

Each attachment's Content-Disposition header contains creation-date and modification-date fields:

**Attachment 1 (Fabricated Adhya Letter):**
```
Content-Disposition: attachment;
 filename="2023-05-11-initial-consultation-with-dr-shaumik-adhya-
 on-tuesday-9-may-2023-84dde236-df0f-4b03-bb59-eac651752dcd.pdf";
 size="125123";
 creation-date="Sat, 04 Nov 2023 07:08:16 GMT";
 modification-date="Sat, 16 Mar 2024 21:56:26 GMT"
```

**All five attachments share:**
- Creation dates clustering at 04 Nov 2023 (07:08 for PDFs, 07:14 for photos)

- Modification date: **16 Mar 2024 21:56:26 GMT** (identical across all five)

**Why this is anomalous:**

In normal email operation, the modification-date of an attachment should equal its creation-date. Email attachments are not editable after the message is sent. There is no user-facing mechanism in Outlook, Outlook Web Access, or any standard email client to modify the attachments of a sent or received message.

The only mechanisms that can modify a delivered message's attachments are:

1. Microsoft Graph API with `Mail.ReadWrite` permissions

2. Exchange Web Services (EWS) with impersonation or application permissions

3. Exchange Online PowerShell with administrative access

4. Microsoft's own compliance and eDiscovery infrastructure

5. Direct infrastructure access compelled by a legal instrument

All five of these mechanisms would produce the same forensic artifact: a simultaneous modification-date across all MIME parts when the MIME structure is regenerated.

### 4.4 The Fabricated Adhya Letter: PDF Metadata

The attached PDF was extracted and analyzed:

| Field | Value |
|---|---|
| Filename | `2023-05-11-initial-consultation-with-dr-shaumik-adhya-on-tuesday-9-may-2023-84dde236-df0f-4b03-bb59-eac651752dcd.pdf` |
| Creator | wkhtmltopdf 0.12.6 |
| Producer | Qt 4.8.7 |
| Creation Date | 11 May 2023 20:43:38 UTC |
| Pages | 2 |
| Hash | Available in evidence package on request |

**Filename analysis:**

The filename follows the format: `[ISO-date]-[URL-slug-title]-[UUIDv4].pdf`

This is the output format of a web application, not a human-created filename. The UUID (`84dde236-df0f-4b03-bb59-eac651752dcd`) is a database record identifier. The slug-case formatting (lowercase, hyphens between words) is standard for web-generated URL-safe filenames. No human names a file this way.

**PDF creator analysis:**

`wkhtmltopdf` is a command-line tool that converts HTML web pages to PDF documents. It is a server-side tool used by web applications to generate downloadable documents from HTML templates. It is not a word processor, not a clinical system, and not any tool a cardiologist would use to write a letter.

The Producer field (`Qt 4.8.7`) indicates the PDF was rendered using the Qt framework's PDF backend, which is the default rendering engine when wkhtmltopdf runs on a **Linux server**. This is distinct from the November 2023 clearance letter, which shows Producer `macOS Version 14.0 Quartz PDFContext`, indicating it was generated or processed on a Mac.

Both letters were created using wkhtmltopdf 0.12.6, meaning they originate from the same web-based clinical letter generation system (likely Dr. Adhya's practice management software at dradhya.com). But they were rendered on different platforms: the fabricated May letter on a Linux server, the genuine November letter on macOS. This is consistent with the May letter being generated through the web application's server-side rendering pipeline without human involvement, while the November letter was generated during or after an actual clinical interaction.

**Internal contradictions in the letter text:**

The letter body contains "Thanks very much for coming to see me today" and "I do hope you found this evening's consultation helpful," language that implies the letter was written on the day of the consultation (9 May 2023, a Tuesday). But the letter header states "Date of Letter: 11 May 2023" (a Thursday), and the PDF creation timestamp confirms the document was generated on 11 May 2023 at 20:43 UTC. The boilerplate phrases "today" and "this evening" were carried over from a template without being updated to reflect the two-day gap between the claimed consultation and the document generation. This is a fabrication error: the template was filled in as if the letter was being dictated on the day of the consultation, but the PDF was not generated until two days later.

### 4.5 Comparison: May Letter vs. November Letter

The fabricated May letter and the genuine November 2023 clearance letter contain materially different clinical recommendations:

| Recommendation | May 2023 (Fabricated) | November 2023 (Genuine) |
|---|---|---|
| Propofol | "I would suggest avoiding Propofol" (total avoidance) | "avoiding a continuous infusion of Propofol above 4mg/kg/min" (dose-limited) |
| Ketamine | "and preferably Ketamine" (avoid) | Not mentioned |
| Tramadol | "and Tramadol" (avoid) | Not mentioned |
| Bupivacaine | "using Lidocaine with adrenalin rather than Bupivacaine" | "using Lidocaine with adrenaline rather than Bupivacaine" |

If the same cardiologist saw the same patient for the same conditions six months apart, and the conditions had not changed (the November letter describes the same diagnoses), there is no clinical reason for the drug recommendations to differ. The difference exists because the May letter was not written during a consultation. It was generated from a template by someone who did not have the clinical knowledge to reproduce the November recommendations exactly.

### 4.6 The Thread-Index Timestamp

The email's Thread-Index header decodes to a conversation creation timestamp of **30 October 2023 15:23:03 UTC**, which matches the first message in the Nordesthetics thread (Nicola's reply to Jolanta at 15:23 on 30 October 2023). The Thread-Index is generated by Exchange at the time the conversation is created and is not modified by subsequent message edits. Its consistency with the known conversation timeline confirms that the original email thread is genuine. The modification targeted the attachments, not the conversation structure.

---

## Section 5: The Self-Concealing Architecture

### Why a Technical Capability Notice Produces Self-Concealing Evidence

This section explains why the forensic evidence we observe is consistent with access provided under a Technical Capability Notice, and why this type of access is inherently difficult to detect.

A Technical Capability Notice (TCN) under IPA 2016 s.253 creates a unique forensic problem. It is not simply a warrant that produces evidence of government access. It is an instrument that, by its design, compels the communications provider to obscure the evidence of that access. Here is why:

**Step 1: The TCN compels Microsoft to provide write access to the drey.fi tenant.**

Microsoft must build or enable the technical mechanisms for modifying email in the target tenant. This might be a special administrative account, an internal API endpoint, or a compliance tool configured for the tenant. Whatever the mechanism, Microsoft is prohibited from disclosing its existence to the tenant holder.

**Step 2: The government uses the access to modify an email (planting the fabricated Adhya letter).**

The modification is performed through Microsoft's own infrastructure. It does not traverse the internet. It does not trigger external intrusion detection systems. It does not generate login alerts to the user. It is invisible to the account holder.

**Step 3: The modification itself creates a forensic artifact (the modification-date).**

When Exchange regenerates the MIME structure after the modification, it stamps a new modification-date on every attachment. This is an unavoidable byproduct of how Exchange works. The modification-date is the fingerprint.

**Step 4: The fingerprint can be overwritten by performing another modification.**

This is the self-concealing property. Because the modification-date reflects only the MOST RECENT modification, any subsequent modification overwrites the previous timestamp. If the government needs to conceal the date of the original modification, they simply modify the email again. The new modification-date replaces the old one. The evidence of the original tampering is destroyed.

**Step 5: The provider (Microsoft) cannot disclose that this happened.**

Under the IPA, the existence of a TCN is classified. Microsoft is legally prohibited from telling the account holder that their email was accessed or modified. Microsoft is also prohibited from disclosing the TCN's existence to any court or authority outside the UK's own oversight framework (the Investigatory Powers Commissioner and the Intelligence and Security Committee). A US court or the FBI cannot be told about the TCN by Microsoft unless compelled by US legal process that overrides the UK classification.

**This creates a closed loop:**

- The government modifies the email (planting evidence)

- The modification creates a detectable artifact (the modification-date)

- The government modifies the email again (overwriting the artifact)

- Microsoft cannot disclose that either modification occurred

- The account holder sees only the final state of the email, with no history

The only way to break this loop is a **US federal subpoena to Microsoft Corporation**, compelling production of internal audit logs, version history, and records of government access requests, under US legal authority that is not subject to UK classification restrictions.

### The 15-16 March 2024 Sequence

The two-day sequence of 15-16 March 2024 is consistent with this architecture:

| Date | Event | Function |
|---|---|---|
| 15 Mar 2024 | Lilia Severina deploys malware against Nicola McNamee's devices | Provides alternative explanation for account compromise; establishes "hacker" narrative if email tampering is discovered |
| 16 Mar 2024 | Email modified on Exchange server (modification-date: 21:56:26 GMT) | Overwrites any prior modification-dates from the pre-murder period; replaces pre-December 2023 timestamps with post-failure timestamps |

The malware deployment on 15 March serves a dual purpose: it compromises Nicola's devices for ongoing surveillance, and it provides a cover story. If the email modification is ever discovered, the perpetrators can claim: "Her account was compromised by malware on 15 March. Any changes to her email after that date are attributable to the malware, not to us." The malware provides plausible deniability for the server-side modification that occurs the next day.

But this explanation fails on a technical level. The modification we observe was performed at the Exchange server level (modification-dates on stored MIME parts), not at the client level. Malware on Nicola's device could compromise her Outlook client, but it cannot modify the server-side MIME structure of a message stored in Exchange Online. The modification-date artifact is a server-side operation. The malware is a client-side operation. They are different attack surfaces.

The fact that both operations occurred within 24 hours of each other, targeting the same victim, through different technical vectors (client-side malware and server-side email modification), is consistent with a coordinated operation using both traditional cyber capabilities (malware) and lawful-access capabilities (TCN/infrastructure access).

---

## Section 6: The Disclosure Review Document and the Hotmail Trap

### The Document

On 25 March 2025, Lilia Severina's solicitors filed a Defendant's Draft Disclosure Review Document (DRD) in Spector v. Severina (BL-2024-000648). This is a standard Appendix 6 to Practice Direction 57AD, the form used in Business and Property Courts to agree what documents each side must search for and disclose. The document is preserved as evidence (file: `2025.03.25DefendantsDraftDRD.pdf`).

Section 4 of the DRD lists every email account to be searched for each custodian. For Brian Spector, the defendant's solicitors listed:

| Account | Connection to FPH Dispute |
|---|---|
| b@theonlymcs.family | Personal, but current |
| brian@drey.fi | Business (Drey, the company behind FPH) |
| brian@2real.xyz | Business |
| brian@fairplayheroes.com | Directly related to the joint venture |
| **bps1968@hotmail.com** | **None. Disused personal account predating the venture by decades.** |
| Twitter messenger | Social media |
| LinkedIn messenger | Professional networking |

Every other address on that list is a business or professional account connected to the FPH joint venture, the subject matter of the litigation. bps1968@hotmail.com is not. It is a dormant personal Hotmail account with no connection to Fairplay Heroes, Drey, or any entity in the dispute.

### How Did They Know It Existed?

Severina's solicitors had no legitimate basis for knowing this account existed. It does not appear in any document exchanged during the joint venture. It is not on any business card, email signature, or corporate record. It is a dormant Microsoft consumer account from a different era of Brian Spector's life.

The only way to identify this account is to have visibility into Brian Spector's **Microsoft identity graph**: the internal mapping that Microsoft maintains linking all accounts associated with a single user identity. When you create a Hotmail account and later subscribe to Microsoft 365 for business, Microsoft's systems link these accounts through shared identity attributes (name, phone number, recovery email, device logins). This mapping is accessible to Microsoft's own systems and to anyone with infrastructure-level access.

A Technical Capability Notice provides exactly this visibility. When the UK government compels Microsoft to provide access to the drey.fi tenant, the identity graph reveals all associated Microsoft accounts, including consumer Hotmail and Outlook.com accounts linked to the same user. The TC Note that enabled write access to brian@drey.fi also exposed the existence of bps1968@hotmail.com.

### The Trap

The inclusion of bps1968@hotmail.com in a court-ordered disclosure document is consistent with a documented intelligence technique: planting incriminating material in a target's dormant account, then using legitimate legal process to force the target to disclose the account, at which point the planted material is "discovered."

The technique operates in three phases:

**Phase 1: Plant.** Using TC Note-enabled write access to the dormant Hotmail account, the operative inserts Child Abuse and Sexual Material (CASM) or other incriminating content into the account. The account holder does not know this has happened because the account is dormant and unmonitored. The material sits there, waiting.

**Phase 2: Point.** Severina's solicitors include bps1968@hotmail.com in the court-ordered DRD. The court compels the account holder to search and disclose the contents of all listed accounts. The account holder is now legally required to open and review the dormant account.

**Phase 3: Discover.** In the course of complying with the court order, the planted material is found. The account holder is now in possession of CASM that they are legally required to report. The discovery appears to arise from routine legal process, not from intelligence operations. The account holder is discredited, potentially arrested, and the litigation collapses. The real operation (fabricated medical records, attempted murder, trade secret theft) disappears beneath the CASM allegations.

This technique has documented precedent in Russian intelligence operations. The FSB and SVR have used variants of this approach since the Soviet era: plant compromising material in a target's environment, then arrange for its "discovery" through a channel that appears legitimate. The digital version, planting CASM in a dormant email account, updates the tradecraft for the era of cloud-hosted email.

### What This Establishes

The inclusion of bps1968@hotmail.com in the DRD establishes a direct, documentable link between:

1. **The intelligence operation** (TC Note access to Microsoft infrastructure, which exposed the existence of the dormant Hotmail through the identity graph)

2. **The civil litigation** (Severina's solicitors, who drafted the DRD and included an account they could only have learned about through intelligence-derived information)

This means one of two things:

**Either** Severina's solicitors independently discovered the existence of bps1968@hotmail.com through legitimate legal research (which is implausible, as there is no public record connecting this dormant account to the FPH dispute),

**Or** Severina's solicitors were provided with intelligence-derived information about Brian Spector's Microsoft account inventory, and they incorporated that information into a court filing without disclosing its source.

If the second explanation is correct, and the forensic evidence strongly supports it, this constitutes: (a) abuse of process in the Business and Property Courts, (b) laundering of intelligence-derived information into civil litigation, and (c) potential conspiracy between UK intelligence services and the defendant's legal representation to discredit and destroy the claimant through planted evidence.

### The Real Purpose of the TC Note

The TC Note was obtained to help kill Nicola McNamee.

That is the primary finding. Everything else flows from it.

Before Nicola traveled to Istanbul in December 2023 for elective surgery, someone needed to plant a fabricated cardiology letter in her email. The letter, attributed to Dr. Shaumik Adhya and describing a consultation on 9 May 2023 that never took place, established a false medical narrative: that Nicola had Long QT Syndrome, Brugada Syndrome, and progressive ischemic heart disease. This letter would travel with her to Istanbul. It would be presented to the surgical team. It would shape their anesthetic decisions. And if the operation succeeded, it would explain her death on or after the operating table as a natural cardiac event in a patient with known but inadequately investigated heart disease. (Full analysis in the Pharmacological Kill Mechanism addendum, Document 04-A.)

To plant that letter, the operatives needed write access to the drey.fi email tenant hosted on Microsoft Exchange Online. A normal user cannot add an attachment to an email that has already been sent and delivered. Only someone with server-level access can do that. The Technical Capability Notice, served on Microsoft under Section 253 of the Investigatory Powers Act 2016, provided that access.

**The TC Note was the murder weapon's delivery system.** Without it, the fabricated letter could not have been inserted into Nicola's email. Without the letter, the surgical team in Istanbul would have had no reason to believe she had cardiac disease. Without the cardiac disease narrative, her death on the operating table would have triggered a criminal investigation, not a finding of natural causes. The TC Note made the entire kill architecture possible.

The TC Note was almost certainly obtained before December 2023. The stated justification to the Judicial Commissioner who approved the warrant may have been related to the trade secret dispute, national security concerns, or any other pretext sufficient to satisfy the double lock process. Whatever was written on the warrant application, the operational purpose was to enable the insertion of fabricated medical documents into a victim's email before she was sent to die in a foreign country.

**After the murder failed**, the TC Note served three additional purposes:

1. **Cover-up.** On 16 March 2024, the email was modified again to overwrite the pre-December 2023 modification timestamps with a new date, destroying forensic evidence that the letter had been planted before the Istanbul surgery. The day before, malware was deployed against Nicola's devices to provide an alternative explanation if the email tampering was ever discovered. (Documented in Section 5 of this addendum.)

2. **Record manipulation.** The same TC Note access that enabled email tampering also provided visibility into Microsoft-hosted clinical systems (Lifebox, CompuCare) used by KIMS Hospital. File upload attributions in the KIMS record, such as the entry claiming Nicola uploaded the fabricated May letter to her own patient portal on 18 June 2023, may have been injected at the platform level rather than by the patient.

3. **The failsafe: destroy Brian Spector if he started digging.** The TC Note exposed the existence of bps1968@hotmail.com through Microsoft's identity graph. A dormant, unmonitored Hotmail account is the perfect container for planted incriminating material. The DRD filed by Severina's solicitors on 25 March 2025, which includes bps1968@hotmail.com in the court-ordered disclosure, is the mechanism for forcing the target to open that container under legal compulsion. The DRD is documentary evidence that intelligence-derived information (the existence of the dormant Hotmail) was passed to the defendant's legal team and laundered into a court order.

To summarize:

| Phase | TC Note Function | Operational Purpose |
|---|---|---|
| **Before December 2023** | Plant fabricated Adhya letter in drey.fi email | Enable the murder of Nicola McNamee by establishing false medical narrative |
| **16 March 2024** | Overwrite email modification timestamps | Destroy forensic evidence linking the email tampering to the pre-murder period |
| **Ongoing** | Manipulate KIMS clinical system records | Fabricate file upload attributions and clinical entries to support the false narrative |
| **25 March 2025** | Expose dormant Hotmail via identity graph | Provide Severina's solicitors with intelligence-derived account information for the CASM failsafe |

The TC Note was not obtained to investigate a trade secret dispute. It was obtained to kill a 38-year-old woman on an operating table in Istanbul, to make her death look natural, and to destroy the man who would investigate it if she survived. She survived because a Brown-trained surgeon ordered an echocardiogram the fabrications were designed to prevent. Brian Spector investigated because that is what he does. The failsafe was activated. The DRD is the documentary evidence of its activation.

---

## Section 7: Can We Prove an Earlier Modification Existed?

The 16 March 2024 modification-date is the timestamp of the most recent modification. If there was an earlier modification (before December 2023, planting the fabricated letter in preparation for the Istanbul operation), the March 2024 modification overwrote its timestamp.

**From the EML file alone, the earlier modification cannot be directly proven.** The modification-date field preserves only the last value.

However, the following investigative actions can recover evidence of the earlier modification:

### 7.1 Outlook Local Cache (.ost File)

Microsoft Outlook stores a local copy of emails in a database file with the extension `.ost`. If Brian Spector opened this email before 16 March 2024 (which is certain, as the email was sent to him on 8 November 2023), his Outlook cache contains the version of the message that existed before the March modification.

If a backup of Brian's computer exists from any date between 8 November 2023 and 15 March 2024 (Time Machine, cloud backup, disk clone, or any other backup mechanism), the `.ost` file in that backup would contain the earlier version. Comparing the attachment list and modification-dates between the backup version and the current version would prove:

- Whether the fabricated Adhya letter was present in the earlier version (indicating a pre-December 2023 modification)

- What the modification-dates were before the March 2024 overwrite

Brian reports that his Outlook client still downloads attachments from the server when opening this email, rather than serving them from local cache. This behavior is consistent with the server-side message having been modified after the local cache was created, causing a cache invalidation that forces re-download from the server.

### 7.2Exchange Recoverable Items (via Subpoena)

Exchange Online maintains a Recoverable Items store for each mailbox. When a message is modified, previous versions may be retained in the Recoverable Items > Versions subfolder. If any retention policy, litigation hold, or compliance hold exists on the drey.fi tenant (including holds placed by a government agency), all previous versions of the message are preserved indefinitely.

### 7.3Microsoft Unified Audit Log (via Subpoena)

Microsoft logs all administrative and API-level operations on Exchange Online mailboxes in the Unified Audit Log. Relevant log events include:

- `Update` events on the message object

- `MailItemsAccessed` events

- Graph API `PATCH` operations targeting the message

- OAuth application token grants

- Administrative consent operations

Standard retention for the Unified Audit Log is 180 days. With E5 licensing or a compliance add-on, retention extends to 1 year or 10 years. If the drey.fi tenant has extended audit log retention, records of the pre-December 2023 modification may still exist.

### 7.4 Microsoft Government Request Records

Microsoft maintains records of all government legal process received, including warrants, subpoenas, national security letters, and (to the extent Microsoft is aware of them) Technical Capability Notices or equivalent instruments from non-US jurisdictions. A US federal subpoena can compel Microsoft to produce:

- All legal process received targeting the drey.fi tenant (ID: `1d280f39-236d-4896-bf98-cd0419803c06`)

- All government requests for data or access related to the drey.fi domain

- All administrative access events that were initiated through compliance or law enforcement portals

- Any records of Technical Capability Notices or similar instruments from the United Kingdom affecting this tenant

---

## Section 8: Evidentiary Requests

### 8.1 Federal Grand Jury Subpoena to Microsoft Corporation

**Subpoena should request:**

1. All versions of the message with Message-ID `<LO4P265MB70793248ACEACD16875FA88AB5A8A@LO4P265MB7079.GBRP265.PROD.OUTLOOK.COM>`, including all prior versions, deleted versions, and modified versions from the Recoverable Items store.

2. Complete Unified Audit Log for tenant `1d280f39-236d-4896-bf98-cd0419803c06` from 1 January 2023 to present, including all MailItemsAccessed, Update, Create, and Delete events.

3. All Graph API access logs for the tenant, including application IDs, permission scopes, and timestamps of all API calls that modified mailbox content.

4. All OAuth application registrations and consent grants for the tenant, including applications granted `Mail.ReadWrite`, `Mail.ReadWrite.All`, or equivalent permissions.

5. All government legal process received targeting the drey.fi domain, the tenant ID `1d280f39-236d-4896-bf98-cd0419803c06`, or any user principal name within the tenant, from 1 January 2023 to present. This includes but is not limited to warrants, subpoenas, national security letters, MLAT requests, and any requests from the United Kingdom including Technical Capability Notices under the Investigatory Powers Act 2016.

6. Any records of administrative access to mailboxes within the tenant that were initiated through Microsoft's law enforcement compliance portal, insider threat tools, or eDiscovery infrastructure.

### 8.2 Evidence Preservation Request

The victims request that the FBI issue an immediate evidence preservation request to Microsoft Corporation for:

- All data associated with tenant `1d280f39-236d-4896-bf98-cd0419803c06`

- All audit logs, version histories, and compliance records for the tenant

- All government access records for the tenant

This preservation request is urgent. Microsoft's standard audit log retention is 180 days. Without a preservation hold, historical audit records may be automatically deleted.

---

## Conclusion

The Nordesthetics email is a legitimate correspondence thread between Nicola McNamee and a Lithuanian cosmetic surgery clinic. But it has been modified at the server level, months after it was sent, to include a fabricated clinical letter from a consultation that never took place. The forensic evidence for this modification is the simultaneous modification-date of 16 March 2024 21:56:26 GMT across all five attachments, a timestamp pattern that can only be produced by a server-side operation rebuilding the email's MIME structure.

The modification date falls one day after a documented malware attack against the victim and six weeks before civil litigation was filed. The coincidence of client-side malware deployment (15 March) and server-side email modification (16 March) is consistent with a coordinated operation using both conventional cyber capabilities and lawful-access infrastructure.

The self-concealing nature of the modification (each new modification overwrites the timestamp of the previous one) is a structural property of how Technical Capability Notices interact with email infrastructure. The government compels the provider to enable access. The access is used to modify evidence. The modification creates a forensic trace. The trace is overwritten by a subsequent modification. The provider is legally prohibited from disclosing any of it.

The TC Note is not a discrete instrument used once. It is a persistent capability serving three functions. First, evidence fabrication: the planted cardiac letter documented in this addendum. Second, real-time surveillance: combined with the US-UK CLOUD Act bilateral data access agreement, the same infrastructure enables ongoing interception of both complainants' communications on American soil, including communications with US federal law enforcement, congressional offices, and the Department of Justice. Brian Spector is a dual US/UK citizen; if the UK classified him as non-US in CLOUD Act warrant applications (a classification they had every incentive to make to avoid triggering US judicial oversight), every surveillance action against him violates the agreement's US person protections. Third, impersonation: write access to the complainants' email accounts enables UK operatives to send emails from those accounts to any recipient, with those emails passing every authentication check. Over two years, the complainants have encountered multiple instances where third parties produced emails firmly attributed to them that neither authored. The TC Note provides the mechanism: their digital identities have been turned against them to manufacture disinformation and destroy their credibility with the people and institutions they need to believe them.

The only authority capable of breaking this cycle is a US federal court, using its subpoena power to compel Microsoft Corporation, a US company, to produce records that the UK government has classified. The evidence of what was done to Nicola McNamee's email, the full scope of surveillance conducted against the complainants, and the complete record of impersonation through their accounts all exist inside Microsoft's systems. It requires US legal process to extract it.

---

*This addendum is intended for inclusion in the evidence package accompanying submissions to the FBI and the Department of Justice. All forensic findings are reproducible using standard email analysis tools (Python email library, ExifTool, PyMuPDF). Source files are preserved with cryptographic hash verification and available on request. The EML file as exported preserves the modification-date metadata in Content-Disposition headers.*
