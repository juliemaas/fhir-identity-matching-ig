<div class="note-to-balloters" markdown="1">
This Identity-focused FHIR Implementation Guide has been established upon the recommendations of ONC's FHIR at Scale Task Force (FAST) Identity Tiger Team, and has been adapted from solution documents previously published by the team. The primary objective of this Implementation Guide is to provide guidance on identity verification and patient matching as used in workflows pertinent to FHIR exchange, to facilitate cross-organizational and cross-network interoperability.



The IG may provide a foundation for future digital identity management requirements.
</div>

&emsp;&emsp;  
### About This Guide

The focus of this implementation guide is to describe how to extend the FHIR patient $match operation for use in cross-organizational workflows, that it may serve as a set of best practices for matching in similar FHIR transactions not specifically invoking $match, as well as in other transaction types.

The requirements described in this guide are intended to align with the proposed solutions of the ONC FHIR at Scale Task Force’s Identity Tiger Team as well as the security model within the proposed solutions of the ONC FHIR at Scale Task Force’s Security Tiger Team.
{:.bg-info}

This Guide is divided into several pages which are listed at the top of each page in the menu bar.

- [Home]\: The home page provides the introduction and background for this project, and general requirements that apply to all workflows described in this guide.
- [Industry Initiatives]\: This page includes a compilation of industry-wide digital identity and patient matching projects.
- [Guidance on Identity Assurance]\: This page describes best practices for patient identity verification in the most common workflows necessary to support healthcare related transactions.
- [Patient Matching]\: This page describes the appropriate usage of the patient $match operation for use in cross-organizational exchange.
- [Digital Identity]\: This page provides best practices for individual identity management in a healthcare context.
- [FHIR Artifacts]\: This page provides additional conformance artifacts for FHIR resources.

{% include link-list.md %}

&emsp;&emsp;  
### Executive Summary

This Implementation Guide provides guidance that can be used to enhance current workflows that support patient matching and Digital Identity, and envisions a longer term path for both providing more specific guidance and incorporating emerging identity concepts over time. In addition to extending the patient $match operation for cross-organizational use by highlighting best practices in the use of matching attributes and their verification prior to responding to a patient match request or interpreting match results, this specification will also offer guidance on identity assurance best practices for attribute and evidence verification and on establishing Digital Identity which is another longer-term objective for this project. 

This guide will address the two concepts of patient matching and Digital Identity with care to differentiate between the two distinct disciplines and the workflows that are usually unique to one concept or the other:  

> **Identity.**  Digital health identity refers to the technology and processes that support personal identity as it pertains to electronic health information.  Digital health identity includes not just identifiers, but also components such as matching, identity vetting (also referred to as proofing or verification), identity authentication, authorization and access control, as well as other technologies and processes. 

> **Patient Matching.**  Patient matching and record linkage help address interoperability by determining whether records - both those held within a single facility and those in different healthcare organizations – correctly refer to a specific individual.  Matching methods use demographic information, such as name and date of birth.

Research has shown that matching is improved with the strength of identity used to process a match (1, 2, 3, 4). For this reason, this Implementation Guide will provide both guidance on how to improve identity assurance and how to leverage identity assurance in matching.

&emsp;&emsp;  
### Use Cases and Roles

- Provider to Provider Health Information Exchange
- Vaccine Credentials Initiative
- Payer to Payer Exchange
- Various Business to Consumer workflows

**Patient Mediated.** Patient authorizes access to their data by a third party when it is under patient's management and not the data creator’s management (e.g. a consumer app enables the patient to manage their own data).  

**Patient Directed.** Patient authorizes access to their data to a third party through an app as in SMART app launch workflow using the patient's credentials for authenticating themselves at the data holder organization which is the data creator.  

**App-Mediated Business to Consumer (B2C).** This type of individual access lets a patient use a patient-facing app, not necessarily operated by a Covered Entity or Business Associate, to exercise their HIPAA Right of Access. Such an app would verify identity using IAL mechanisms and restrict the information given to the patient in ways that are beyond the scope of this guide. In other words, the patient is attempting to access their health data without using a credential from the data creator or intermediary data holder.  

**B2B TPO.** This business-to-business workflow involves a Covered Entity with an exchange purpose of Treatment, Payment, or Operations.  

**B2B Coverage Determination.** This business-to-business workflow involves a non-Covered Entity with an exchange purpose of Coverage Determination.  

(1)  <a href="https://www.justassociates.com/application/files/1414/9134/1517/PIIWhitePaper.pdf">Patient Identity Integrity White Paper</a>  HIMSS, December 2009  
(2)  <a href="https://www.gao.gov/assets/gao-19-197.pdf">Approaches and Challenges to Electronically Matching Patients’ Records across Providers</a>  GAO, January 2019  
(3)  <a href="https://sequoiaproject.org/resources/patient-matching/">The Sequoia Project</a>    
(4) <a href="https://www.rand.org/content/dam/rand/pubs/research_reports/RR2200/RR2275/RAND_RR2275.pdf">Defining and Evaluating Patient-Empowered Approaches to Improving Record Matching</a>  RAND, 2018

&emsp;&emsp;  

### Credits  
<style>
table, th, td 
{
  border: 1px solid White; 
  padding: 2px
}
</style>
|  |    |    |
| <u><b>Primary Authors:</b></u>&emsp; |Julie Maas  | EMR Direct        |
|   |Carmen Smiley  | ONC        |
|   |Jeff Brown  | MITRE Corporation        |
|   |         |  |
| <u><b>Contributors:</b></u>&emsp;  |Paul Vaughan  | Optum        |
|   | Vijey Kris Sridharan | United Healthcare |
|   | Jim St Clair | Linux Foundation |
|   | Catherine Schulten | Walmart |
|   | Ryan Howells | Leavitt Partners |
|   | Rita Torkzadeh | Independent Consultant |

&emsp;&emsp;  
This implementation guide was made possible by the thoughtful contributions and feedback of the following additional people and organizations:

The members of the ONC FHIR at Scale Taskforce (FAST) Identity Tiger Team

The members of the HL7 Patient Administration Work Group



