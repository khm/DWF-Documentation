# Distributed Weakness Filing (DWF) Project

The Distributed Weakness Filing (DWF) Project aims to provide identifying numbers for security vulnerabilities that is similar in concept to the Common Vulnerabilities and Exposures (CVE) project. The DWF Project was created to enable security researchers to register and receive their numbers faster, as well as enabling organizations to more easily track the latest vulnerabilities, enabling them to patch sooner. 

Format-wise, the DWF Project currently uses the same format as CVE (e.g., DWF-YEAR-NNNNN and DWF-YEAR-NNNNNNN).

Numerically DWF ids can generally be mapped directly to CVE with no conflict; if you spot a conflict between CVE and DWF identifier please notify the DWF project so it can be addressed.

## Getting a DWF Identifier

There are four primary ways to get a DWF identifier:

1) If you already have a CVE identifier you can map it directly to DWF IDs, e.g. CVE-2000-1234 maps directly to DWF-2000-1234.

2) If you are a DWF Numbering Authority (DNA) (https://github.com/distributedweaknessfiling/DNA-Registry) you can self assign a DWF ID to the issue(s).

3) You can request a DWF ID from a DNA; this is ideal if the DNA is associated with the flawed software (e.g. the vendor is a DNA), or the DNA will assist in the handling of the security vulnerability.

4) You can request a DWF id directly either via PULL request in GitHub to the DWF Database (https://github.com/distributedweaknessfiling/DWF-Database) or by emailing us at distributedweaknessfiling@gmail.com. You will need to submit some level of data (e.g. the CWE root cause, affected files/functions, etc.).

### Is it a Vulnerability?

DWF IDs are for security vulnerabilities in software. DWF ids are not for services (e.g. an XSS in an Open Source or commercially available software package would receive a DWF ID, but an XSS in a banking website running a custom web service would not receive a DWF ID).

A vulnerability is generally classified as a flaw that allows an attacker to gain access, elevate privilege, cause a denial of service, or have another security related impact (i.e., it must cross privilege boundaries in some manner). Please note that the impact may be relatively minor (e.g. disclosure of a small, uncontrolled piece of kernel memory), however as we have all learned, small attacks can be chained together to create big attacks. Further, some small attacks are examined by different researchers and found to be more severe.

### DWF ID Splitting and Merging 

Pragmatically, not every single vulnerability can have a DWF identifier. For example, if you audit a piece of software and find 500 XSS flaws we are not going to assign 500 DWF identifiers just as CVE would not. As such, DWF generally categorizes vulnerabilities in buckets that then receive a DWF Identifier with the following guidelines:

1. Take all your vulnerabilities and split them by code base
2. Take these vulnerabilities and split them by vulnerability type (e.g. XSS vs CSRF)
3. Take these vulnerabilities and split them by affected version (e.g. starting affected version R by the fixed versions if retroactively assigning them)

## Getting Your Entries into the DWF Database

To get your entries listed in the official DWF database (located at https://github.com/distributedweaknessfiling/DWF-Database/) you MUST submit the DWF identifier and valid artifacts. 

### Valid artifacts

* Security advisories
* Vendor security reports
* Bug reports
* Code examples
* Code patches

### Invalid artifacts

* Video or sound recordings of "proof of concept"; they're to big, low value, so use text instead
* Generally speaking any binary executable content is to be avoided

### Submitting artifacts with potentially dangerous content

By their nature some artifacts may have dangerous content (e.g. files that cause crashes when processed). We suggest such artifacts be compressed and password protected with a text file attached that contains the password (e.g. zip the file with password "DWF-1500-123456"). 

## How to Become a DNA

DNA policy is simple; Ask us. In general, to become a DNA you either need to be finding vulnerabilities that need DWF identifiers, or have people reporting vulnerabilities to you that need identifiers (e.g. as a vendor or vulnerability coordinator).

## DWF Project Management Board

The DWF Management board consists of 5 people and is largely designed to provide a tie-breaking mechanism for difficult decisions.

For more information please see the General Information file (https://github.com/distributedweaknessfiling/DWF-Documentation/blob/master/General-Information.md)

## Other Questions / Concerns / Problems / Ideas

Email us (distributedweaknessfiling@gmail.com), or poke us on twitter (@dwfaccount). 
