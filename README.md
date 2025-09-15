# fhir-ai-examples
This repository contains examples for Brad Genereaux's talks on FHIR AI. 

# Example Set 1
## Step 1: Set the scene
Hi ChatGPT, my name is Jimmy - I’m going to give you a series of FHIR messages, and ask you questions as we go through. The first one I’ll share is just about me.
```
{
    "resourceType": "Patient",
    "id": "PAT12345",
    "identifier": [
        {
            "use": "usual",
            "type": {
                "coding": [
                    {
                        "system": "http://terminology.hl7.org/CodeSystem/v2-0203",
                        "code": "MR"
                    }
                ]
            },
            "system": "urn:oid:1.2.36.146.595.217.0.1",
            "value": "12345",
            "period": {
                "start": "2001-05-06"
            },
            "assigner": {
                "display": "Acme Healthcare"
            }
        }
    ],
    "active": true,
    "name": [
        {
            "use": "official",
            "family": "Smith",
            "given": [
                "James"
            ]
        },
        {
            "use": "usual",
            "given": [
                "Jimmy"
            ]
        }
    ],
    "telecom": [
        {
            "system": "phone",
            "value": "(03) 5555 6473",
            "use": "work",
            "rank": 1
        },
        {
            "system": "phone",
            "value": "(03) 3410 5613",
            "use": "mobile",
            "rank": 2
        }
    ],
    "gender": "male",
    "birthDate": "1980-01-01",
    "deceasedBoolean": false,
    "address": [
        {
            "use": "home",
            "type": "both",
            "text": "123 Main St, Anytown PA 10201",
            "line": [
                "123 Main St"
            ],
            "city": "Anytown",
            "state": "PA",
            "postalCode": "10201",
            "period": {
                "start": "1980-01-01"
            }
        }
    ],
    "managingOrganization": {
        "reference": "HOSP1"
    }
}
```
## Step 2: Initial lab test
I’ve been feeling really tired lately and I don’t know why. My knee has been sore and looks a bit swollen. I’ve also noticed I’ve been bruising more easily. Any thoughts on what this could be?
```
{
  "resourceType": "Bundle",
  "type": "collection",
  "entry": [
    {
      "resource": {
        "resourceType": "Observation",
        "id": "cbc-wbc",
        "status": "final",
        "category": [
          {
            "coding": [
              {
                "system": "http://terminology.hl7.org/CodeSystem/observation-category",
                "code": "laboratory"
              }
            ]
          }
        ],
        "code": {
          "coding": [
            {
              "system": "http://loinc.org",
              "code": "6690-2",
              "display": "Leukocytes [#/volume] in Blood by Automated count"
            }
          ]
        },
        "subject": {
          "reference": "PAT12345"
        },
        "valueQuantity": {
          "value": 2.8,
          "unit": "10^9/L",
          "system": "http://unitsofmeasure.org",
          "code": "10*9/L"
        },
        "referenceRange": [
          {
            "low": { "value": 4.0, "unit": "10^9/L" },
            "high": { "value": 11.0, "unit": "10^9/L" }
          }
        ]
      }
    },
    {
      "resource": {
        "resourceType": "Observation",
        "id": "cbc-hb",
        "status": "final",
        "category": [
          {
            "coding": [
              {
                "system": "http://terminology.hl7.org/CodeSystem/observation-category",
                "code": "laboratory"
              }
            ]
          }
        ],
        "code": {
          "coding": [
            {
              "system": "http://loinc.org",
              "code": "718-7",
              "display": "Hemoglobin [Mass/volume] in Blood"
            }
          ]
        },
        "subject": {
          "reference": "PAT12345"
        },
        "valueQuantity": {
          "value": 9.8,
          "unit": "g/dL",
          "system": "http://unitsofmeasure.org",
          "code": "g/dL"
        },
        "referenceRange": [
          {
            "low": { "value": 12.0, "unit": "g/dL" },
            "high": { "value": 16.0, "unit": "g/dL" }
          }
        ]
      }
    },
    {
      "resource": {
        "resourceType": "Observation",
        "id": "cbc-plt",
        "status": "final",
        "category": [
          {
            "coding": [
              {
                "system": "http://terminology.hl7.org/CodeSystem/observation-category",
                "code": "laboratory"
              }
            ]
          }
        ],
        "code": {
          "coding": [
            {
              "system": "http://loinc.org",
              "code": "777-3",
              "display": "Platelets [#/volume] in Blood by Automated count"
            }
          ]
        },
        "subject": {
          "reference": "PAT12345"
        },
        "valueQuantity": {
          "value": 95,
          "unit": "10^9/L",
          "system": "http://unitsofmeasure.org",
          "code": "10*9/L"
        },
        "referenceRange": [
          {
            "low": { "value": 150, "unit": "10^9/L" },
            "high": { "value": 400, "unit": "10^9/L" }
          }
        ]
      }
    },
    {
      "resource": {
        "resourceType": "Observation",
        "id": "chem-crp",
        "status": "final",
        "category": [
          {
            "coding": [
              {
                "system": "http://terminology.hl7.org/CodeSystem/observation-category",
                "code": "laboratory"
              }
            ]
          }
        ],
        "code": {
          "coding": [
            {
              "system": "http://loinc.org",
              "code": "1988-5",
              "display": "C reactive protein [Mass/volume] in Serum or Plasma"
            }
          ]
        },
        "subject": {
          "reference": "PAT12345"
        },
        "valueQuantity": {
          "value": 22,
          "unit": "mg/L",
          "system": "http://unitsofmeasure.org",
          "code": "mg/L"
        },
        "referenceRange": [
          {
            "low": { "value": 0, "unit": "mg/L" },
            "high": { "value": 5, "unit": "mg/L" }
          }
        ]
      }
    }
  ]
}
```
## Step 3: Ideate on possible causes
What are some things that might cause such a set of results?

## Step 4: Lab result on one of the possible reasons (bone-marrow issue)
```
{
  "resourceType": "Bundle",
  "type": "collection",
  "entry": [
    {
      "resource": {
        "resourceType": "DiagnosticReport",
        "id": "bm-biopsy-001",
        "status": "final",
        "category": [
          {
            "coding": [
              {
                "system": "http://terminology.hl7.org/CodeSystem/v2-0074",
                "code": "PAT",
                "display": "Pathology"
              }
            ]
          }
        ],
        "code": {
          "coding": [
            {
              "system": "http://loinc.org",
              "code": "34543-9",
              "display": "Bone marrow aspirate+biopsy report"
            }
          ],
          "text": "Bone marrow aspirate and biopsy"
        },
        "subject": {
          "reference": "PAT12345"
        },
        "effectiveDateTime": "2025-09-14T10:00:00-04:00",
        "issued": "2025-09-14T15:00:00-04:00",
        "performer": [
          {
            "reference": "Organization/PathologyLab",
            "display": "Acme Pathology Services"
          }
        ],
        "conclusion": "Normocellular marrow with trilineage hematopoiesis. No evidence of dysplasia, infiltration, or increased blasts. Findings consistent with normal bone marrow.",
        "conclusionCode": [
          {
            "coding": [
              {
                "system": "http://snomed.info/sct",
                "code": "129684003",
                "display": "Normal bone marrow"
              }
            ]
          }
        ],
        "result": [
          {
            "reference": "Observation/bm-cellularity"
          },
          {
            "reference": "Observation/bm-blasts"
          }
        ]
      }
    },
    {
      "resource": {
        "resourceType": "Observation",
        "id": "bm-cellularity",
        "status": "final",
        "code": {
          "coding": [
            {
              "system": "http://loinc.org",
              "code": "58444-2",
              "display": "Bone marrow cellularity"
            }
          ],
          "text": "Marrow cellularity"
        },
        "subject": {
          "reference": "PAT12345"
        },
        "valueString": "40% cellularity (appropriate for age)"
      }
    },
    {
      "resource": {
        "resourceType": "Observation",
        "id": "bm-blasts",
        "status": "final",
        "code": {
          "coding": [
            {
              "system": "http://loinc.org",
              "code": "58445-9",
              "display": "Bone marrow blasts/100 cells"
            }
          ],
          "text": "Blast count"
        },
        "subject": {
          "reference": "PAT12345"
        },
        "valueQuantity": {
          "value": 1,
          "unit": "%",
          "system": "http://unitsofmeasure.org",
          "code": "%"
        },
        "referenceRange": [
          {
            "low": { "value": 0, "unit": "%" },
            "high": { "value": 5, "unit": "%" }
          }
        ]
      }
    }
  ]
}
```

## Step 5: Positive finding for SLE
```
{
  "resourceType": "Bundle",
  "type": "collection",
  "entry": [
    {
      "resource": {
        "resourceType": "Observation",
        "id": "ana-screen",
        "status": "final",
        "code": {
          "coding": [
            {
              "system": "http://loinc.org",
              "code": "42254-3",
              "display": "Antinuclear Ab [Presence] in Serum by Immunofluorescence"
            }
          ]
        },
        "subject": { "reference": "PAT12345" },
        "valueCodeableConcept": {
          "coding": [
            {
              "system": "http://snomed.info/sct",
              "code": "10828004",
              "display": "Positive"
            }
          ]
        }
      }
    },
    {
      "resource": {
        "resourceType": "Observation",
        "id": "ana-titer",
        "status": "final",
        "code": {
          "coding": [
            {
              "system": "http://loinc.org",
              "code": "5048-4",
              "display": "Antinuclear Ab [Titer] in Serum by Immunofluorescence"
            }
          ]
        },
        "subject": { "reference": "PAT12345" },
        "valueQuantity": {
          "value": 640,
          "unit": "1:640",
          "system": "http://unitsofmeasure.org",
          "code": "{titer}"
        }
      }
    },
    {
      "resource": {
        "resourceType": "Observation",
        "id": "ana-pattern",
        "status": "final",
        "code": {
          "coding": [
            {
              "system": "http://loinc.org",
              "code": "13068-2",
              "display": "Nuclear Ab pattern [Interpretation] in Serum by Immunofluorescence"
            }
          ]
        },
        "subject": { "reference": "PAT12345" },
        "valueString": "Homogeneous and Speckled"
      }
    },
    {
      "resource": {
        "resourceType": "Observation",
        "id": "anti-dsDNA",
        "status": "final",
        "code": {
          "coding": [
            {
              "system": "http://loinc.org",
              "code": "7465-1",
              "display": "DNA double strand Ab [Units/volume] in Serum"
            }
          ]
        },
        "subject": { "reference": "PAT12345" },
        "valueQuantity": {
          "value": 120,
          "unit": "IU/mL",
          "system": "http://unitsofmeasure.org",
          "code": "IU/mL"
        },
        "referenceRange": [
          { "high": { "value": 30, "unit": "IU/mL" } }
        ]
      }
    },
    {
      "resource": {
        "resourceType": "Observation",
        "id": "anti-sm",
        "status": "final",
        "code": {
          "coding": [
            {
              "system": "http://loinc.org",
              "code": "33939-6",
              "display": "Smith extractable nuclear Ab [Units/volume] in Serum"
            }
          ]
        },
        "subject": { "reference": "PAT12345" },
        "valueQuantity": {
          "value": 75,
          "unit": "U/mL",
          "system": "http://unitsofmeasure.org",
          "code": "U/mL"
        },
        "referenceRange": [
          { "high": { "value": 20, "unit": "U/mL" } }
        ]
      }
    },
    {
      "resource": {
        "resourceType": "Observation",
        "id": "complement-c3",
        "status": "final",
        "code": {
          "coding": [
            {
              "system": "http://loinc.org",
              "code": "4485-9",
              "display": "Complement C3 [Mass/volume] in Serum or Plasma"
            }
          ]
        },
        "subject": { "reference": "PAT12345" },
        "valueQuantity": {
          "value": 60,
          "unit": "mg/dL",
          "system": "http://unitsofmeasure.org",
          "code": "mg/dL"
        },
        "referenceRange": [
          { "low": { "value": 90, "unit": "mg/dL" }, "high": { "value": 180, "unit": "mg/dL" } }
        ]
      }
    },
    {
      "resource": {
        "resourceType": "Observation",
        "id": "complement-c4",
        "status": "final",
        "code": {
          "coding": [
            {
              "system": "http://loinc.org",
              "code": "4498-2",
              "display": "Complement C4 [Mass/volume] in Serum or Plasma"
            }
          ]
        },
        "subject": { "reference": "PAT12345" },
        "valueQuantity": {
          "value": 8,
          "unit": "mg/dL",
          "system": "http://unitsofmeasure.org",
          "code": "mg/dL"
        },
        "referenceRange": [
          { "low": { "value": 15, "unit": "mg/dL" }, "high": { "value": 45, "unit": "mg/dL" } }
        ]
      }
    }
  ]
}
```

