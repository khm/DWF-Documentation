# Distributed Weakness Filing (DWF) Project

The Distributed Weakness Filing (DWF) Project is the first federated CVE Number Authority (CNA). The DWF will initially deal with assigning CVEs for Open Source software (as defined by OSI approved Open Source licenses https://opensource.org/licenses and similar licenses). The DWF will assign CVEs for valid security vulnerabilities using the same or very similar processes as Mitre and other CVE Numbering Authorities currently use. 

## Getting a CVE Identifier from the DWF for your security vulnerability(s)

We are currently deciding on process for this, in the mean time you can submit an issue via the form at https://iwantacve.org/

## Becoming a CVE Mentor

The first step is to contact us, email is good (see our contact info), or file an issue. To get involved with the DWF as a CVE Mentor you MUST accept the [Contributor Covenant](Contributor-Agreement.md). 

## Becoming an Open Source CNA (CVE Numbering Authority)

To become an Open Source CNA you must meet the following requirements:

1) Fill out a CNA application form (form to be created)

2) Agree to the CNA Rules at https://cve.mitre.org/cve/cna/CNA_Rules_v1.1.pdf

3) Find at least one or more CVE Mentors willing to work with you, they can be internal to your organization/project or an external person. 

## Assigning a CVE for the DWF

If you are assigning CVEs on behalf of the DWF please consult the [CVE Assignment HOWTO](CVE-Assignment-HOWTO.md).

# Primary Documents

# TermsOfUse.md

This is the MITRE Terms of Use for CVE data, if you want to submit data to CVE you must agree to these Terms of Use.

The primary source for this document is: https://cve.mitre.org/about/termsofuse.html

## Contributor-Agreement.md

This is the DWF Contributor Agreement, if you want to participate withint the DWF as a CVE mentor or CNA you must accept this agreement. 

The primary source for this document is: http://contributor-covenant.org/version/1/4/

## CNA_Rules_v1.1.pdf

This is the MITRE Common Vulnerabilities and Exposures (CVE) Numbering Authority (CNA) Rules , if you want to be a CNA you must read this and accept these guidelines.

The primary source for this document is: https://cve.mitre.org/cve/cna/CNA_Rules_v1.1.pdf

# Git Repo layout

## DWF-Documentation

This repo contains the documentation.

Location: https://github.com/distributedweaknessfiling/DWF-Documentation/

## DWF-Master-CVE-Database

This repo contains the Master CVE Database which consists of the CVE Year, start of range, end of range, length of range and where this block is stored (e.g. which Git repo). When you want to find a CVE you can look here to find the repo it exists within. 

Location: https://github.com/distributedweaknessfiling/DWF-Master-CVE-Database

## DWF-CVE-Mentor-Registry

This repo contains a list of CVE Mentors, mentors may be affiliated with none, one, or more CNAs. CVE Mentors are not required to assign CVEs, they may for example be involved for example primarily in training other CVE Mentors or providing supporting to other CVE Mentors. 

Location: https://github.com/distributedweaknessfiling/DWF-CVE-Mentor-Registry

## DWF-CNA-Registry

This is the DWF CNA registry, it is basically just a list of CNAs and their CVE Mentor(s) and the CVE ID blocks they use. Every CNA must have one or more CVE Mentors that work with them. 

Location: https://github.com/distributedweaknessfiling/DWF-CNA-Registry

## DWF-Legal-Acceptance

This repo contains legal acceptance from people who are not yet CVE Mentors or CNAs withint the DWF.

Location: https://github.com/distributedweaknessfiling/DWF-Legal-Acceptance

## DWF-Database

This is the original database used for 2016 and prior assignments, it is largely obsolete.

Location: https://github.com/distributedweaknessfiling/DWF-Database

