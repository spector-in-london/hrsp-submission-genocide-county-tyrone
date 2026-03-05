# 06, INSTITUTIONAL ANALYSIS: INTELLIGENCE ARCHITECTURE

## The State Capability Question

The medical infrastructure documented in Part 1 (04) and the concealment architecture documented in Part 2 (05) are not consistent with ordinary medical malpractice or administrative negligence. The fabrication of consultations, ECGs, and clinical letters, coordinated across multiple institutions and supported by server-side email modification (documented in the Digital Forensics Addendum, Document 06-A), reflects operational capability inconsistent with a hospital acting alone.

A note on the KIMS medical records PDF: the digital properties of the file (no searchable text, no metadata, raster-only ECGs) may result from the scanning of paper records rather than deliberate obfuscation. If the clinical records existed primarily as paper documents and were scanned into PDF by the Medical Records Administrator, these properties are natural scanning artifacts. Whether the records were paper or digital is a question for investigation. The fabrication of the content (the ECGs, the consultations, the clinical letters) stands independently of how the file was digitized.

The question is not whether the state had the capability. The question is whether the institutional architecture existed to deploy that capability through healthcare infrastructure. The answer is documented.

---

## MI5 Permanent Control: St Andrews Agreement, Annex E (2006)

The St Andrews Agreement (2006) transferred permanent control of **national security intelligence** in Northern Ireland to MI5, the UK's domestic intelligence agency. Annex E of the agreement formalized this arrangement, creating what the evidence describes as a parallel security architecture with minimal accountability to the devolved Northern Ireland government.

Under this framework:

- **MI5** holds operational control of national security intelligence across Northern Ireland, not the Police Service of Northern Ireland (PSNI), not the Northern Ireland Executive

- **MI5's remit** is defined by the UK government, not the NI Assembly, meaning the devolved government has no oversight authority over intelligence operations conducted within its jurisdiction

- **Accountability** runs to Westminster and the UK Intelligence and Security Committee (ISC), not to any Northern Ireland institution

This architecture was designed for counterterrorism. But it creates the institutional capability for any operation classified as "national security" to be conducted in Northern Ireland through UK intelligence channels, without the knowledge or consent of the devolved government, local police, or the affected population.

**HRSP Significance:** The St Andrews Agreement, Annex E provides the legal and operational framework through which UK MoD personnel could operate through NHS infrastructure in Northern Ireland. If the medical targeting of the County Tyrone population is a state operation, and the evidence of intelligence-grade document manipulation, the coordinated refusal of all UK agencies to investigate, and the deployment of APT29 malware against the complainants all point in that direction, then Annex E is the enabling architecture.

---

## The Starmer Timeline

Keir Starmer, now Prime Minister of the United Kingdom, served as a **human rights adviser to the Northern Ireland Policing Board** from 2003 to 2008. This period overlaps with every critical event in the construction of the intelligence architecture and the onset of the genocide:

- The **Tellus geological survey** began in 2004, confirming the scale of the Curraghinalt gold deposit (Convergence Timeline, Document 09)

- The **earliest documented false cardiac diagnoses** targeting County Tyrone began in 2004 (Medical Infrastructure, Document 04)

- The **Special Reconnaissance Regiment (SRR) was formed on 6 April 2005**, reorganizing 14 Intelligence Company into a military surveillance unit operating under MI5 direction in Northern Ireland

- The **St Andrews Agreement (Annex E)** was signed in 2006, formalizing MI5's permanent control of NI national security

- **MI5 formally assumed lead responsibility** for NI national security in late 2007

Starmer's role as human rights adviser to the Policing Board was to identify and flag human rights risks in the policing and intelligence architecture. The SRR formation (2005) and Annex E (2006) created a parallel military/intelligence structure with what the Committee on the Administration of Justice described as "minimal or non-existent" accountability. Did Starmer flag these accountability gaps? If he did, the reports are on record and should be produced. If he did not, that failure, given his specific advisory mandate, requires explanation.

Starmer subsequently appointed Peter Mandelson as UK Ambassador to the United States (2025), despite Mandelson's known Epstein connections and mineral lobbying history. Jeremy Corbyn stated in the House of Commons on 4 February 2026 that Starmer "would have known of Mandelson's record of an interesting relationship with global dealers in minerals." Full profile in the Perpetrator Profiles chapter (Document 07).

---

## Uniform Refusal to Investigate: The Institutional Firewall

Between July and December 2025, Brian Spector, a cybersecurity and digital forensics specialist with a background in cryptography, reported specific, technical evidence to every relevant UK agency. The evidence was not a general complaint. It was a documented forensic finding: **embedded malware and systematic document tampering inside evidence bundles submitted to the UK Chancery Court by the defendant's solicitors** in Spector's civil litigation (BL-2024-000648).

Spector discovered this tampering using AI-powered digital forensic tools he had developed. The tampering was designed to defeat Optical Character Recognition (OCR) systems, the same automated text-extraction tools used by courts, law firms, and investigators to process legal documents. Specifically, the techniques included:

- **Metadata stripping**, removal of authorship, creation dates, and edit history from PDF documents

- **Text layer removal**, deletion of the selectable text layer, forcing the document to appear as a flat image that OCR systems cannot reliably read

- **Data flattened to raster images**, conversion of structured data (including ECG readouts) into static images, destroying the underlying data and preventing machine analysis

The litigation evidence bundles are electronic documents submitted to the Chancery Court through the CE-FILE system. These are not scanned paper. They are digital files that have been deliberately stripped of metadata and text layers before submission. This is confirmed deliberate obfuscation of court evidence.

Nicola McNamee's KIMS Hospital medical records (documented in the Medical Infrastructure chapter, Document 04) share the same digital properties: no metadata, no text layers, raster-only images. However, the KIMS file may have originated as paper records scanned by the Medical Records Administrator (see Perpetrator Profiles, Document 07, Profile 6). Whether the KIMS records were deliberately obfuscated or simply scanned from paper is a question for investigation. The fabrication of the clinical content (ECGs, consultations, letters) is established independently of how the file was digitized.

The deliberate obfuscation in the litigation evidence bundles, combined with the server-side email modification documented in the Digital Forensics Addendum (Document 06-A), establishes state-level document manipulation capability. The KIMS records may or may not reflect the same deliberate technique, but the fabrication of their content is proven regardless.

Spector made three emergency evidence-based applications to the Chancery Court to safeguard data within the UK Judiciary's CE-FILE system after discovering the tampering. He then reported the forensic evidence to every relevant UK agency. Every agency refused to act:

| Agency | Report Date | Response |
|---|---|---|
| **MI5** | July 2025 (×2) | No substantive response |
| **National Crime Agency (NCA)** | July 2025 | No substantive response |
| **National Cyber Security Centre (NCSC)** | July 2025 | No substantive response |
| **Action Fraud** | July 2025 | No substantive response |
| **Kent Police** | July–December 2025 (×4) | Refused to accept laptops for forensic analysis |

The reports were not vague tips. They were technically detailed forensic findings, submitted by a credentialed cybersecurity professional, documenting evidence of state-level document tampering inside an active court proceeding. The uniform non-response across all agencies, domestic intelligence (MI5), organized crime (NCA), cyber security (NCSC), fraud reporting (Action Fraud), and local police (Kent), is not consistent with independent institutional decisions. Independent agencies receiving credible, technically documented evidence of this nature would produce at least one anomalous response, one agency that opened a file, requested further information, or referred the matter internally. The uniform refusal to engage across all institutions suggests coordinated suppression.

Kent Police's conduct is particularly significant. Officers twice warned Brian Spector that **MoD operatives were attempting to imprison him with planted evidence**. This warning came from within the policing system itself, officers who could see what was happening and were attempting to alert the target. The same force then refused to accept his laptops for forensic analysis, the very devices containing the evidence of document tampering they had been warned about.

**HRSP Significance:** The uniform institutional refusal to investigate, across intelligence, law enforcement, and cyber security agencies, demonstrates that no UK institution is willing or able to investigate this matter. The forensic link between the litigation document tampering and Nicola McNamee's medical record tampering means the agencies were not merely declining to investigate a civil litigation dispute. They were declining to investigate evidence that the same state-level document manipulation techniques used against a U.S. citizen's court proceedings were also being used to falsify medical records in the suspected targeting of a civilian population. This is precisely the jurisdictional gap that HRSP was created to fill.

---

## The UK Domestic Investigation Barrier: State Secrets and Closed Material Procedures

### The Official Secrets Act

The UK's Official Secrets Act and the Intelligence Services Act create a legal framework under which intelligence operatives and their activities are shielded from domestic investigation and prosecution. Even if a UK court or police force wished to investigate MI5 operations conducted under Annex E authority, the Official Secrets Act would provide grounds to block disclosure, refuse witness testimony, and prevent evidence from being produced.

This is not a theoretical barrier. It is the mechanism by which intelligence operations are routinely shielded from scrutiny in the UK legal system.

### Closed Material Procedures (Justice and Security Act 2013)

The Justice and Security Act 2013 introduced a second, complementary mechanism: **Closed Material Procedures (CMP)**. Under CMP, UK courts can consider evidence classified as damaging to national security in **closed proceedings**, meaning one or both parties to the litigation are excluded from seeing the evidence being used against them or on their behalf.

The Act imposes specific statutory requirements when CMP is invoked:

| Requirement | Statutory Basis |
|---|---|
| **Section 6 Declaration** | The court must make a formal declaration that the case involves closed material |
| **Special Advocates** | Security-cleared lawyers must be appointed to represent the excluded party's interests |
| **Notification** | The affected parties must be informed that CMP is being applied to their case |
| **Judicial Oversight** | The judge must approve each individual piece of closed material |

These requirements exist because CMP represents an extraordinary departure from open justice. Without them, CMP would be indistinguishable from a state operation conducted under judicial cover.

### CMP Abuse in Spector v. Severina

Evidence from Spector's civil litigation (BL-2024-000648) indicates that his case was designated a national security matter under CMP, **without any of the statutory requirements being met**:

- **No Section 6 Declaration** was ever issued or disclosed to Spector

- **No Special Advocate** was appointed to represent his interests

- **No notification** was provided that CMP applied to his case

- Spector's first solicitor confirmed near the litigation's end this was **not** a national security case **when it started**

The consequences of this covert designation were severe. MoD operatives were embedded in Spector's successive legal teams, billing him for their time while working against his interests. His barrister, identified as operating fabricated personas on both sides of the litigation, functioned as what would have been a "Special Advocate" in a legitimate CMP, but without any of the accountability or oversight the Act requires. The presiding Master described the result as the **"worst procedural mismanagement I have ever seen"**, a characterization consistent not with incompetence, but with deliberate sabotage conducted under state authority.

The abuse of CMP in Spector's litigation is significant for two reasons:

1. It demonstrates that the UK state apparatus was actively using national security mechanisms against the individual who would later identify the medical targeting pattern, before he had identified it

2. It confirms that the UK's domestic legal framework provides no remedy. If the state can designate a civil case as CMP without following its own statutory requirements, and every UK agency refuses to investigate when this is reported, then the domestic investigation barrier is absolute

### Why Only U.S. Authority Can Penetrate This Barrier

HRSP's authority to investigate human rights violations by foreign governments, including allied governments, is not constrained by the UK's domestic secrecy framework. U.S. federal grand jury subpoenas, mutual legal assistance treaty (MLAT) requests, and targeted sanctions under the Global Magnitsky Act operate outside the UK's Official Secrets Act and CMP apparatus. The UK cannot invoke CMP in a U.S. federal proceeding. The UK cannot assert Official Secrets Act privilege over documents subpoenaed by a U.S. grand jury. This is why only a foreign sovereign's investigative authority, specifically, the U.S. Department of Justice, has the jurisdictional standing and legal tools to penetrate this barrier.

---

## MoD Operatives in the Litigation

The parallel Economic Espionage Act referral, referred by Congressman Cloud to the FBI through the Office of Congressional Affairs and filed 30 January 2026, documents the direct involvement of UK Ministry of Defence operatives in litigation against Brian Spector.

The EEA filing establishes:

- **Ali Reza Sinai**, identified as an MoD operative who simultaneously operated fabricated personas on both sides of Spector's litigation, while connected to IRGC-linked networks

- **Four successive legal teams** were compromised between May 2024 and August 2025, a systematic destruction of the complainants' access to legal representation

- The fourth legal team attempted to deploy **APT29 malware** against the complainants three times, via PDF, Word document, and SharePoint, weaponizing the attorney-client relationship

- CMP designations were abused by the MoD: Spector was never informed his civil litigation case had been designated a national security interest, in violation of UK law (Justice and Security Act 2013, Section 6)

The document tampering techniques discovered in the litigation evidence bundles, the same techniques found in Nicola McNamee's medical records, were deployed through these compromised legal teams. The MoD operatives embedded in Spector's representation had both the access and the capability to introduce manipulated documents into court proceedings.

**HRSP Significance:** The involvement of MoD operatives in the complainants' litigation demonstrates that the same state apparatus suspected of conducting the medical targeting is actively operating against the individuals who have identified it. This is not a cold case. It is an active operation with identifiable operatives, documented in the EEA filing now before the FBI.

---

## IRGC Surveillance on U.S. Soil

In October 2025, days after Brian Spector met with FBI Special Agent Smith at the Manassas, Virginia field office, an Uber driver using the IRGC rank designation **"SARDAR"** (Commander) conducted surveillance against the complainants in Washington, D.C.

The Islamic Revolutionary Guard Corps is a **designated Foreign Terrorist Organization** under U.S. law. The appearance of an individual using an IRGC rank designation, conducting surveillance against a U.S. citizen on American soil, timed to his FBI contact, constitutes:

- An automatic federal jurisdictional trigger under counterterrorism authorities

- Evidence that foreign intelligence services are monitoring the complainants' engagement with U.S. law enforcement

- A direct threat to a U.S. citizen exercising his right to report criminal conduct to federal authorities

**HRSP Significance:** FTO activity on U.S. soil against a complainant witness is an immediate safety concern that falls within HRSP's coordination authority. It also raises the question of how an IRGC-linked actor knew the timing and location of the complainant's FBI meeting, suggesting either surveillance of the complainant or a compromise within the information chain. Spector's EEA filing contains the contemporaneous evidence linking MoD activities coordinating with IRGC and APT29 operatives.

---

## Active Device Surveillance of Complainant Witness

Forensic analysis of the primary complainant witness's mobile phone, an iPhone that remained in Nicola McNamee's possession, reveals evidence of device-level compromise consistent with state-sponsored spyware deployment. Three screenshots recovered from the device (IMG_0916, IMG_0920, IMG_0921, dated 8–10 May 2023) were taken without Nicola's knowledge and display five forensic red flags: Proton Mail origination metadata on an account she does not use; targeted browsing of her psychiatric treatment history (ketamine therapy, DBT/psychiatry providers); three sequential screenshots deleted from the sequence (IMG_0917–0919); a structured reconnaissance browsing pattern through KIMS Hospital records, her treating cardiologist, and Brugada-contraindicated medications completed in under three minutes; and evidence that the device was being operated remotely while KIMS Hospital was simultaneously leaving voicemails on her number, indicating the phone's operator and the hospital's caller were different actors.

The technical indicators are consistent with Pegasus or equivalent zero-click spyware. The UK has been identified as a confirmed Pegasus customer by Citizen Lab (2022). The Investigatory Powers Act 2016, Part 5, Sections 99–134 provides the legal framework for Equipment Interference Warrants, the domestic statutory authority under which UK intelligence services deploy device-level surveillance tools. NSO Group's Pegasus exploits, including CVE-2019-3568 (WhatsApp zero-click buffer overflow), have been documented operating through this framework.

The device surveillance evidence is significant because it demonstrates that the intelligence apparatus documented in this section was not merely manipulating medical records and court documents, it was actively surveilling the complainant witness through her personal device, collecting intelligence on her medical and psychiatric treatment, and doing so using capabilities consistent with the same state infrastructure that controls the NHS cardiac screening program through Annex E authority. The full forensic analysis, including the five red flags, the spyware assessment, and the availability of the physical device for MVT (Mobile Verification Toolkit) scanning by DOJ investigators, is documented in Document 08 (Victim Documentation).

---

## The TC Note as a Three-Part Weapon

The Technical Capability Notice served on Microsoft and Amazon Web Services does not serve a single purpose. It serves three.

**First, it enables evidence fabrication.** The UK used write access to Microsoft's infrastructure to plant fabricated cardiac documents inside Nicola McNamee's email, manufacturing the medical pretext for her death under anesthesia. This is documented in the forensics addendum (06-A).

**Second, combined with the CLOUD Act bilateral agreement, it enables real-time surveillance of both complainants on American soil.** The UK can monitor every communication Brian Spector and Nicola McNamee have with US federal authorities, US attorneys, and each other, through the same American companies whose infrastructure was used to attempt the murder. Brian Spector is a dual US/UK citizen. If the UK classified him as non-US in the CLOUD Act warrant application, a classification the UK had every incentive to make because disclosing his US citizenship would trigger mandatory US judicial oversight, then every surveillance action against him violates the agreement's US person protections. No US government body reviews these orders. No one checks the target's nationality. The UK is likely monitoring the investigation into its own conduct.

**Third, it enables impersonation and reputation destruction.** Write access to the complainants' email accounts means the UK can send emails from those accounts to any recipient. These emails pass every authentication check because they originate from the genuine account. The recipient has no technical reason to doubt their authenticity. Over the past two years, the complainants have encountered multiple instances where third parties produced emails or writings firmly attributed to them that neither complainant authored. At the time, the complainants believed they were being gaslighted. The TC Note provides the explanation: UK intelligence operatives used the complainants' own accounts to manufacture and distribute disinformation, destroying the complainants' professional reputations and credibility with the precise audience (colleagues, potential allies, and authorities) that the complainants would later need to believe them.

This third capability is the counter-investigation weapon. Plant the medical evidence to kill. Surveil the victim who survived to monitor whether she discovers the fraud. When the victims begin reporting to authorities, use their own accounts to poison every relationship and institution they approach, so that by the time they produce the evidence, their credibility has already been destroyed by content that appears to have come from them.

The complainants also have reason to believe that criminal content has been planted within accounts on the Microsoft identity graph associated with their tenant, following the same pattern documented in Section 6 of the forensics addendum (the Hotmail CASM trap): deposit compromising material in a dormant or peripheral account, then arrange for its "discovery" through a channel that appears legitimate. Any content attributed to either complainant since late 2023 must be treated as potentially fabricated until verified through forensic analysis of server-side logs that only Microsoft can produce under US legal process.

**HRSP Significance:** The three-part weapon (fabricate, surveil, impersonate) means the TC Note is not a discrete instrument used once to plant a medical document. It is a persistent operational capability that continues to operate against the complainants on American soil. The fabrication attempted murder. The surveillance monitors the investigation. The impersonation destroys the investigators' trust in the complainants before they can present their evidence. All three run through American technology infrastructure. All three are invisible to American authorities. Only US legal process directed at Microsoft and AWS can expose the full scope of the operation.

---

## CLOUD Act: The Architecture Extends to US Soil

The intelligence architecture described in this document does not stop at the UK border. The US-UK CLOUD Act bilateral data access agreement (signed October 2019, effective October 2022) provides the legal framework for the UK to request data from US communications providers on targets located anywhere, including inside the United States.

Under this agreement, UK authorities can serve orders directly on US communications providers (Microsoft, Google, Apple, Amazon) for real-time interception and stored data of non-US persons without notifying US law enforcement or obtaining a US court order. The agreement contains protections for US persons: if the target is a US citizen or lawful permanent resident, the UK must notify the US and obtain judicial authorization.

**The dual nationality violation.** Brian Spector is a dual US/UK citizen. The UK had direct knowledge of his UK citizenship through his UK residence, tax records, and passport. The UK also had access to his US citizenship status through the very intelligence databases and court records involved in this operation. The UK had every incentive to classify Brian as a UK person (non-US) in CLOUD Act warrant applications, because disclosing his US citizenship would trigger the agreement's mandatory US judicial oversight. With no US government body independently reviewing UK CLOUD Act orders for nationality classification, no one would catch the misrepresentation.

If the UK concealed Brian Spector's US citizenship in CLOUD Act orders, the consequences are:

- Every surveillance action against him on US soil violated the agreement's US person protections

- The UK monitored a US citizen's communications with US federal law enforcement without any American court or agency knowing

- The bilateral agreement was breached by deliberate misrepresentation, not administrative error

- The CLOUD Act's central safeguard (protection of US persons) failed because no US authority verifies the UK's nationality classifications

**Nicola McNamee has no CLOUD Act protection at all.** As a UK citizen who is not a US person, Nicola falls entirely outside the agreement's protections. The UK can surveil every communication she has on American soil through American companies with no US oversight of any kind. The complainant witness whose testimony threatens to expose the genocide is accessible to the same apparatus that tried to kill her, through the same American infrastructure, under a bilateral agreement that provides her zero protection.

**HRSP Significance:** The CLOUD Act bilateral agreement transforms what would otherwise be a foreign intelligence operation into an operation conducted through American companies under American legal authority. This is not a case of a foreign government hacking US systems. This is a foreign government using a bilateral agreement with the United States to surveil the victims of its own genocide on American soil, through American companies, with the legal architecture of the United States providing the access.

---

## The Architecture: Summary

The intelligence architecture operates through eight interlocking components, each independently documented:

| Component | Function | Evidence Source |
|---|---|---|
| **St Andrews Agreement, Annex E** | Legal authority for MI5 operations in NI, including through NHS infrastructure | Public law (2006) |
| **MI5 operational control** | Capability to direct operations through any NI institution without devolved government oversight | Annex E framework |
| **Closed Material Procedures** | Mechanism to designate cases as national security and exclude affected parties from evidence, abused in Spector's litigation without statutory compliance | Justice and Security Act 2013; EEA filing |
| **MoD operatives** | Identified personnel operating against complainants in both litigation and intelligence contexts, using document tampering techniques matching those found in medical records | EEA filing; forensic analysis |
| **Uniform agency refusal** | Coordinated institutional protection preventing domestic investigation of technically documented forensic evidence | Correspondence with MI5, NCA, NCSC, Action Fraud, Kent Police |
| **Official Secrets Act** | Legal shield preventing domestic courts from examining intelligence operations or CMP designations | UK statutory framework |
| **IRGC surveillance** | Foreign intelligence services monitoring complainants' engagement with U.S. law enforcement on U.S. soil | FBI report (October 2025) |
| **Active device surveillance** | Complainant witness's mobile phone compromised with state-grade spyware; psychiatric and medical intelligence collected remotely | iPhone forensic analysis (May 2023); Victim Documentation, Document 08 |
| **TC Note three-part weapon** | Evidence fabrication (planted medical docs), real-time surveillance (CLOUD Act), impersonation and reputation destruction (emails sent from victims' accounts) | Forensic analysis; third-party witness accounts; CLOUD Act bilateral agreement |
| **CLOUD Act dual nationality violation** | UK likely classified dual US/UK citizen as non-US to bypass agreement's US person protections; ongoing surveillance of complainant's communications with US law enforcement | CLOUD Act bilateral agreement (2022); Brian Spector's dual citizenship documentation |

Each component is documented: the St Andrews Agreement is public law; the CMP requirements are statutory; the agency refusals are documented in correspondence; the Kent Police warnings are on record; the MoD operative's identity is established in litigation records and the EEA filing; the document tampering forensic link is confirmed by technical analysis; the IRGC surveillance incident is reported to the FBI; the device surveillance is evidenced by forensic analysis of the complainant's iPhone with the physical device available for DOJ examination.

The architecture describes a state intelligence apparatus that:

1. Has the legal authority to operate through healthcare infrastructure (Annex E)

2. Has the technical capability to manipulate documents (confirmed in litigation evidence bundles) and to modify email at the server level (confirmed in the Digital Forensics Addendum, Document 06-A)

3. Has the legal mechanism to shield its operations from judicial scrutiny (Official Secrets Act + CMP)

4. Has abused that mechanism against the complainant without following its own statutory requirements (covert CMP designation)

5. Is actively operating against the individuals who identified the pattern (MoD operatives in litigation, APT29 malware deployment)

6. Has ensured that no domestic institution will investigate (uniform refusal across all agencies)

7. Is being monitored by a designated Foreign Terrorist Organization on U.S. soil (IRGC)

8. Has deployed device-level surveillance against the complainant witness, collecting psychiatric and medical intelligence through her personal phone (spyware forensics, May 2023)

9. Has used TC Note write access to impersonate the complainants through their own email accounts, manufacturing and distributing disinformation to destroy their credibility with the people and institutions they need to believe them

10. Is likely surveilling the complainants' communications with US federal authorities on American soil through the CLOUD Act bilateral agreement, having almost certainly concealed the primary complainant's US citizenship to bypass the agreement's US person protections

HRSP exists precisely because some human rights violations cannot be investigated by the perpetrator state's own institutions. The domestic investigation barrier in the UK is not a gap in institutional capacity, it is a purpose-built legal and operational architecture that prevents investigation by design. Only U.S. federal authority operating outside that architecture can penetrate it. This is that case.

---

## DIGITAL INFRASTRUCTURE MANIPULATION AND COUNTER-INTELLIGENCE

The intelligence architecture described above is not merely institutional. It extends to active digital operations against the complainant witnesses, including manipulation of email infrastructure, device-level surveillance, and real-time counter-intelligence during the evidence-gathering phase.

### The DKIM/DMARC Gap: Planted Evidence Without Cryptographic Authentication

The drey.fi Office 365 tenant (used by both complainants) operates without per-message cryptographic authentication:

| Mechanism | Purpose | drey.fi Status |
|-----------|---------|---------------|
| **SPF** | Validates sending server | Configured |
| **DKIM** | Cryptographically signs each message | **Not configured** |
| **DMARC** | Rejects/quarantines failed authentication | **Not configured** |

All 31 drey.fi internal emails from November 2023 lack DKIM signatures. The planted emails documented in the Medical Infrastructure chapter (Document 04) (fabricated cardiac documents deposited with empty subjects and empty bodies) are forensically indistinguishable from items injected directly into the mailbox by an O365 tenant administrator or any authenticated principal with EWS or Graph API access.

**This is not technical incompetence.** The complainant witness's fiancé configures full DKIM/DMARC/SPF authentication for multiple separate domains in the same AWS account. A third-party Exchange Online tenant (`sinclairsoffshore.com`) on the same UK infrastructure partition has active DKIM signing. Platform limitation is eliminated as an explanation.

### Government-Directed Modification Under the Investigatory Powers Act 2016

The United Kingdom's Investigatory Powers Act 2016 provides statutory authority for the UK government to compel telecommunications operators to modify their systems:

- **Section 253** authorizes Technical Capability Notices requiring operators to maintain interception capability

- **Section 261** authorizes removal or disabling of electronic protection, including authentication mechanisms

- **Section 263** imposes secrecy obligations prohibiting disclosure

AWS and Microsoft both operate UK-based infrastructure subject to UK jurisdiction. A TCN under these provisions would provide a legal mechanism for government-directed removal of email authentication without the domain owner's knowledge.

This submission suggests such a notice was served. It identifies a forensic anomaly (unexplained absence of email authentication on a domain through which fabricated medical evidence was transmitted) and requests investigation.

### Active Counter-Intelligence: Device Compromise and Operational Timing

The fabrication chain documented in the Medical Infrastructure chapter (Document 04) was supported by device-level surveillance that tracked both complainants' activities in real time.

**Pegasus deployment against Nicola McNamee's mobile device.** During the operational window between Nicola's request for the KIMS referral letter and the Istanbul procedures (late November 2023), her mobile phone was compromised with Pegasus spyware. The fake images of Dr Adhya's details that appeared on her phone on 10 May 2023 (images she did not take) were planted via the compromised device. The phone screenshots were created from her device and then matched to entries uploaded to the KIMS records system by staff member Katy Fitzpatrick on 22 June 2023, constructing apparent patient provenance for fabricated documents. Pegasus is a state-level surveillance tool sold exclusively to government agencies.

**Device compromise timing correlation.** Brian Spector's digital devices were compromised with malware in **November 2023**, the same month as the Istanbul surgery window. Nicola McNamee's devices were compromised via APT29 malware deployed by Lilia Severina in **March 2024**, three months after Nicola survived the surgery. The timing is consistent with monitoring initiated during the kill window and expanded to Nicola after her survival, to determine whether the fabrication had been detected and whether the victims were accessing or comparing medical records from different institutions.

**Spearphishing during records recovery (February 2026).** In the same week that Nicola was forwarding KIMS Subject Access Request responses and requesting her Memorial Hospital records (the exact activity that would expose the fabrication by enabling comparison between the fabricated KIMS file and the genuine Memorial records), a spearphishing attack was directed at Brian Spector. An email from `kafinhausaharuna@gmail.com`, using the display name "Nicola McNamee," requested that Mr. Spector share his WhatsApp number for "important instructions that require your immediate attention." The email passed DKIM authentication for Gmail (it was sent from a real Gmail account, not a spoofed header). The deception was in the display name, designed to move communication to an unmonitored channel during the critical evidence-gathering period. Someone knew they were comparing records and attempted to intervene.

**The records were not supposed to be obtained.** The fabricated KIMS file was designed to survive discovery within the UK legal and regulatory system, where the institutional infrastructure documented in the Cover-Up Infrastructure chapter (Document 05) could manage the outcome. It was not designed to survive comparison with records from Memorial Hospital Istanbul, a hospital outside UK jurisdiction and outside the control of the actors described in this submission.

---

*Prepared for HRSP submission package, Brian Spector, 5 March 2026*

*SENSITIVE, NOT FOR PUBLIC DISTRIBUTION*
