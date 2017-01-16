# CVE JSON File Format 4.0

This describes the CVE JSON format version 4.0, this file format primarily covers CVE but also CVE Mentors and CNAs

CVE_* is a reserved keyword. Essentially every CVE file is a JSON Object that contains more top level objects which in turn contain objects/arrays/booleans/etc. We have some required top level objects: CVE_data_type (what is this file?), CVE_data_format (who’s format is it in?) and CVE_data_version (what version of the data format is this?) for all types.

CVE_* keywords are officially documented (this document), if you see one that isn’t here then it’s not an official keyword, and you can ignore it. To add/modify/suggest changes to CVE_* keywords and their data structures please do X (issue in GitHub? TBD) so that we can consider it. 

# The CVE top level objects

CVE_data_type: CVE/CNA/MENTOR must be present in root level, can be present in root level only [single]

CVE_data_format: MITRE/other must be present in root level, can be present in root level or can be a child of anything [single]

CVE_data_version must be present in root level, can be present in root level or can be a child of anything [single]

CVE_data_meta must be present in root level, can be present in root level or can be a child of anything [single] [CVEID]

CVE_affects must be present in root level, can be in root level only [multiple]

CVE_vendor child of CVE_affects only, must be at least 1 present [multiple]

CVE_product child of CVE_vendor only, must be at least 1 present [multiple] [PRODUCT]

CVE_version child of CVE_product only, must be at least 1 present [multiple] [VERSION]

CVE_description root level object and child of anything, 1 must be present in root level [single] [DESCRIPTION]

CVE_configuration root level object and child of anything, optional, [multiple]

CVE_references root level object and child of anything, 1 must be present, [multiple] [REFERENCES]

CVE_workaround  root level object and child of anything, optional, generally under root, CVE_affects, CVE_vendor, CVE_product, CVE_version, CVE_configuration, [multiple]

CVE_exploit root level object and child of anything, optional, generally under root, CVE_affects, CVE_vendor, CVE_product, CVE_version, CVE_configuration, [multiple]

CVE_timeline root level object and child of anything, optional, generally under root, CVE_affects, CVE_vendor, CVE_product, CVE_version, CVE_configuration, [multiple]

CVE_credit root level object and child of anything, optional, generally under root, CVE_affects, CVE_vendor, CVE_product, CVE_version, CVE_configuration, [multiple]

CVE_problemtype root level object and child of anything, 1 must be present in root level [PROBLEMTYPE], generally under root only, [multiple]

CVE_impact root level object and child of anything, 1 must be present in root level, generally under root, CVE_affects, CVE_vendor, CVE_product, CVE_version, CVE_configuration, [multiple]

# Examples

## Minimal structure needed for CVE

```
{
  "CVE_data_type": "CVE",
  "CVE_data_format": "MITRE",
  "CVE_data_version": "4.0",
  "CVE_data_meta": {
    "CVE_ID": "CVE-2017-900000",
    "date_requested": "2017-01-01",
    "date_assigned": "2017-01-02",
    "requestor": "kurt@seifried.org",
    "assigner": "kurt@seifried.org"
  },
  "CVE_affects": {
    "CVE_vendor": {
      "CVE_product": {
        "products_affected": [
          {
            "product_name": "Example product",
            "product_version": "1.0",
            "product_affected": "="
          }
        ]
      }
    }
  },
  "CVE_description": {
    "lang": "eng",
    "value": "String description of issue"
  },
  "CVE_references": {
    "references": [
      {
        "url": "string for url location",
        "name": "string Name of reference i.e. if advisory has name",
        "publish_date": "DATE-TIMESTAMP of reference release to public"
      }
    ]
  },
  "CVE_problemtype": {
    "problems": [
      {
        "description": [
          {
            "lang": "string ISO 639-2",
            "value": "string description of problem_type"
          }
        ],
        "cwe": [
          "strings of cwes",
          "strings separated by commas"
        ],
        "owasp": [
          "string of OWASP information",
          "strings separated by commas"
        ]
      }
    ]
  }
}
```

## More complicated example with product with configuration and specific description

The following example has a product with its own description, and a configuration for that product with it's own description in turn. 

```
{
  "CVE_data_type": "CVE",
  "CVE_data_format": "MITRE",
  "CVE_data_version": "4.0",
  "CVE_data_meta": {
    "CVE_ID": "CVE-2017-900000",
    "date_requested": "2017-01-01",
    "date_assigned": "2017-01-02",
    "requestor": "kurt@seifried.org",
    "assigner": "kurt@seifried.org"
  },
  "CVE_affects": {
    "CVE_vendor": {
      "CVE_product": {
        "products_affected": [
          {
            "product_name": "Example product",
            "product_version": "1.0",
            "product_affected": "=",
            "CVE_description": {
              "lang": "eng",
              "value": "String description of issue"
            },
            "CVE_impact": {
              "CVE_impact_metrics": {
                "cvss2": {},
                "cvss3": {}
              }
            },
            "CVE_configuration": {
              "XCCDF": "string value",
              "CVE_description": {
                "lang": "eng",
                "value": "String description of issue"
              }
            }
          },
          {
            "product_name": "Example product",
            "product_version": "1.1",
            "product_affected": "=<"
          }
        ]
      }
    }
  },
  "CVE_description": {
    "lang": "eng",
    "value": "String description of issue"
  },
  "CVE_references": {
    "references": [
      {
        "url": "string for url location",
        "name": "string Name of reference i.e. if advisory has name",
        "publish_date": "DATE-TIMESTAMP of reference release to public"
      }
    ]
  },
  "CVE_problemtype": {
    "problems": [
      {
        "description": [
          {
            "lang": "string ISO 639-2",
            "value": "string description of problem_type"
          }
        ],
        "cwe": [
          "strings of cwes",
          "strings separated by commas"
        ],
        "owasp": [
          "string of OWASP information",
          "strings separated by commas"
        ]
      }
    ]
  }
}
```

