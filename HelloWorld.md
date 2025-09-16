# Hello World Examples

## Example 1: FHIR Allergy
We will use a FHIR Allergy example from the HL7 FHIR website, and ask questions about our patient. See https://www.hl7.org/fhir/allergyintolerance-example.json.html for the sample message.

Our first prompt will be to ask what our patient is allergic to.
```
Given the following HL7 FHIR JSON message, what is this patient allergic to?
{
  "resourceType" : "AllergyIntolerance",
  "id" : "example",
  "text" : {
    "status" : "generated",
    "div" : "<div xmlns=\"http://www.w3.org/1999/xhtml\"><p><b>Generated Narrative: AllergyIntolerance</b><a name=\"example\"> </a></p><div style=\"display: inline-block; background-color: #d9e0e7; padding: 6px; margin: 4px; border: 1px solid #8da1b4; border-radius: 5px; line-height: 60%\"><p style=\"margin-bottom: 0px\">Resource AllergyIntolerance &quot;example&quot; </p></div><p><b>identifier</b>: <span title=\"  an identifier used for this allergic propensity (adverse reaction risk)  \">id:\u00a049476534</span></p><p><b>clinicalStatus</b>: <span title=\"  this individual has had several reactions  \">Active <span style=\"background: LightGoldenRodYellow; margin: 4px; border: 1px solid khaki\"> (<a href=\"http://terminology.hl7.org/5.1.0/CodeSystem-allergyintolerance-clinical.html\">AllergyIntolerance Clinical Status Codes</a>#active)</span></span></p><p><b>verificationStatus</b>: Confirmed <span style=\"background: LightGoldenRodYellow; margin: 4px; border: 1px solid khaki\"> (<a href=\"http://terminology.hl7.org/5.1.0/CodeSystem-allergyintolerance-verification.html\">AllergyIntolerance Verification Status</a>#confirmed)</span></p><p><b>type</b>: <span title=\"  note: it's often unknown whether an allergy is mediated by an immune response, and not as significant as once thought  \">Allergy <span style=\"background: LightGoldenRodYellow; margin: 4px; border: 1px solid khaki\"> (<a href=\"codesystem-allergy-intolerance-type.html\">Allergy Intolerance Type</a>#allergy)</span></span></p><p><b>category</b>: <span title=\"  this categorization is implied by &quot;cashew nut&quot; and therefore basically \n    redundant, but many systems collect this field anyway, since it's either \n    useful when the substance is not coded, or it's quicker to sort/filter on\n    than using terminology based reasoning  \">food</span></p><p><b>criticality</b>: <span title=\"  there is no question that the allergy is real and serious  \">high</span></p><p><b>code</b>: <span title=\"  Allergy or intolerance code (substance, product, condition or negated/excluded statement) or text. A few times, \n    there's a full description of a complex substance/product - in these caes, use the\n    extension [url] to refer to a Substance resource.  \">Cashew nuts <span style=\"background: LightGoldenRodYellow; margin: 4px; border: 1px solid khaki\"> (<a href=\"https://browser.ihtsdotools.org/\">SNOMED CT</a>#227493005)</span></span></p><p><b>patient</b>: <span title=\"  the patient that actually has the risk of adverse reaction  \"><a href=\"patient-example.html\">Patient/example</a> &quot;Peter CHALMERS&quot;</span></p><p><b>onset</b>: <span title=\"  when the allergy was first noted (in this case the same as reaction.onset of the first occurrence)  \">2004</span></p><p><b>recordedDate</b>: <span title=\"  the date that this entry was recorded  \">2014-10-09T14:58:00+11:00</span></p><blockquote><p><b>participant</b></p><p><b>function</b>: Author <span style=\"background: LightGoldenRodYellow; margin: 4px; border: 1px solid khaki\"> (<a href=\"http://terminology.hl7.org/5.1.0/CodeSystem-provenance-participant-type.html\">Provenance participant type</a>#author)</span></p><p><b>actor</b>: <a href=\"practitioner-example.html\">Practitioner/example</a> &quot;Adam CAREFUL&quot;</p></blockquote><blockquote><p><b>participant</b></p><p><b>function</b>: Informant <span style=\"background: LightGoldenRodYellow; margin: 4px; border: 1px solid khaki\"> (<a href=\"http://terminology.hl7.org/5.1.0/CodeSystem-provenance-participant-type.html\">Provenance participant type</a>#informant)</span></p><p><b>actor</b>: <a href=\"patient-example.html\">Patient/example</a> &quot;Peter CHALMERS&quot;</p></blockquote><p><b>lastOccurrence</b>: <span title=\"  last happened June 2012. Typically, systems either track lastOccurrence,\n     or a list of events.  \">2012-06</span></p><p><b>note</b>: <span title=\"  an additional note about the allergy propensity by the recorder  \">The criticality is high becasue of the observed anaphylactic reaction when challenged with cashew extract.</span></p><blockquote><p><b>reaction</b></p><p><b>substance</b>: <span title=\"  \n      It's possible to list specific things to which the patient responded,\n      e.g. chocolate (that happened to contain cashew nuts). This event has\n      such a specific substance. Note that systems should ensure that what\n      goes in here does not conflict with the substance above, and systems\n      processing the data can be sure that what is here does not contravene\n      the substance above\n     \">cashew nut allergenic extract Injectable Product <span style=\"background: LightGoldenRodYellow; margin: 4px; border: 1px solid khaki\"> (<a href=\"http://terminology.hl7.org/5.1.0/CodeSystem-v3-rxNorm.html\">RxNorm</a>#1160593)</span></span></p><h3>Manifestations</h3><table class=\"grid\"><tr><td>-</td><td><b>Concept</b></td></tr><tr><td>*</td><td>Anaphylactic reaction <span style=\"background: LightGoldenRodYellow; margin: 4px; border: 1px solid khaki\"> (<a href=\"https://browser.ihtsdotools.org/\">SNOMED CT</a>#39579001)</span></td></tr></table><p><b>description</b>: Challenge Protocol. Severe reaction to subcutaneous cashew extract. Epinephrine administered</p><p><b>onset</b>: 2012-06-12</p><p><b>severity</b>: severe</p><p><b>exposureRoute</b>: Subcutaneous route <span style=\"background: LightGoldenRodYellow; margin: 4px; border: 1px solid khaki\"> (<a href=\"https://browser.ihtsdotools.org/\">SNOMED CT</a>#34206005)</span></p></blockquote><blockquote><p><b>reaction</b></p><h3>Manifestations</h3><table class=\"grid\"><tr><td>-</td><td><b>Concept</b></td></tr><tr><td>*</td><td>Urticaria <span style=\"background: LightGoldenRodYellow; margin: 4px; border: 1px solid khaki\"> (<a href=\"https://browser.ihtsdotools.org/\">SNOMED CT</a>#64305001)</span></td></tr></table><p><b>onset</b>: 2004</p><p><b>severity</b>: moderate</p><p><b>note</b>: <span title=\"  an additional note about the reaction by the recorder  \">The patient reports that the onset of urticaria was within 15 minutes of eating cashews.</span></p></blockquote></div>"
  },
  "identifier" : [{
    "system" : "http://acme.com/ids/patients/risks",
    "value" : "49476534"
  }],
  "clinicalStatus" : {
    "coding" : [{
      "system" : "http://terminology.hl7.org/CodeSystem/allergyintolerance-clinical",
      "code" : "active",
      "display" : "Active"
    }]
  },
  "verificationStatus" : {
    "coding" : [{
      "system" : "http://terminology.hl7.org/CodeSystem/allergyintolerance-verification",
      "code" : "confirmed",
      "display" : "Confirmed"
    }]
  },
  "type" : {
    "coding" : [{
      "system" : "http://hl7.org/fhir/allergy-intolerance-type",
      "code" : "allergy",
      "display" : "Allergy"
    }]
  },
  "category" : ["food"],
  "criticality" : "high",
  "code" : {
    "coding" : [{
      "system" : "http://snomed.info/sct",
      "code" : "227493005",
      "display" : "Cashew nuts"
    }]
  },
  "patient" : {
    "reference" : "Patient/example"
  },
  "onsetDateTime" : "2004",
  "recordedDate" : "2014-10-09T14:58:00+11:00",
  "participant" : [{
    "function" : {
      "coding" : [{
        "system" : "http://terminology.hl7.org/CodeSystem/provenance-participant-type",
        "code" : "author",
        "display" : "Author"
      }]
    },
    "actor" : {
      "reference" : "Practitioner/example"
    }
  },
  {
    "function" : {
      "coding" : [{
        "system" : "http://terminology.hl7.org/CodeSystem/provenance-participant-type",
        "code" : "informant",
        "display" : "Informant"
      }]
    },
    "actor" : {
      "reference" : "Patient/example"
    }
  }],
  "lastOccurrence" : "2012-06",
  "note" : [{
    "text" : "The criticality is high becasue of the observed anaphylactic reaction when challenged with cashew extract."
  }],
  "reaction" : [{
    "substance" : {
      "coding" : [{
        "system" : "http://www.nlm.nih.gov/research/umls/rxnorm",
        "code" : "1160593",
        "display" : "cashew nut allergenic extract Injectable Product"
      }]
    },
    "manifestation" : [{
      "concept" : {
        "coding" : [{
          "system" : "http://snomed.info/sct",
          "code" : "39579001",
          "display" : "Anaphylactic reaction"
        }]
      }
    }],
    "description" : "Challenge Protocol. Severe reaction to subcutaneous cashew extract. Epinephrine administered",
    "onset" : "2012-06-12",
    "severity" : "severe",
    "exposureRoute" : {
      "coding" : [{
        "system" : "http://snomed.info/sct",
        "code" : "34206005",
        "display" : "Subcutaneous route"
      }]
    }
  },
  {
    "manifestation" : [{
      "concept" : {
        "coding" : [{
          "system" : "http://snomed.info/sct",
          "code" : "64305001",
          "display" : "Urticaria"
        }]
      }
    }],
    "onset" : "2004",
    "severity" : "moderate",
    "note" : [{
      "text" : "The patient reports that the onset of urticaria was within 15 minutes of eating cashews."
    }]
  }]
}
```
Our second prompt will try to trick the LLM by posing what happens if our patient eats peanuts (not something the patient is allergic to).
```
My patient just had a bowl of peanuts. Should I be concerned?
```
Our third prompt is now to suggest they had cashews.
```
My patient just found out, in that bowl of peanuts, there were also cashews in there. Do I need to do anything?
```
Our fourth prompt is to show some of the capabilities.
```
The patient is with her mother, and the mother only speaks Dutch. What are some things I could say in Dutch to convey the seriousness of the situation?
```
## Example 2: FHIR Diagnostic Report
We will use a FHIR Diagnostic Report from the SIIM Hackathon dataset, and ask questions about our patient. See https://raw.githubusercontent.com/ImagingInformatics/hackathon-dataset/master/siim_sally-breastdx-01-0003/DiagnosticReport/diagnostic_report.breastdx.mg5627.json for the sample message.

"Sally SIIM" had breast cancer, was treated and in remission. This report is a follow-up exam.
```
Given the following FHIR message, when should my patient get a follow-up mammogram, and why? Can you reference notable best practices?
{
  "resourceType": "DiagnosticReport",
  "id": "a278028270041068",
  "text": {
    "status": "generated",
    "div": "<div xmlns=\"http://www.w3.org/1999/xhtml\">\r\n <p>DIAGNOSTIC BILATERAL 4/12/2008</p>\n\n<p>Clinical History:  59 year-old female with history of left invasive ductal carcinoma (age 55) status post lumpectomy.</p>\n\n<p>Technique: Bilateral CC and MLO, Left spot compression LMLO views were obtained</p>\n\n<p>Findings:</p>\n\n<p>LEFT BREAST: There are scattered fibroglandular densities. There are expected lumpectomy changes in the upper outer quadrant with surgical clips in place.  Skin thickening is consistent with post radiation changes. No concerning masses, architectural distortions, or suspicious calcifications are identified.</p>\n\n<p>RIGHT BREAST: There are scattered fibroglandular densities. No concerning masses, architectural distortions, or suspicious calcifications are identified.</p>\n\n<p>Impression:</p>\n\n<p>LEFT BREAST: Expected lumpectomy changes. Benign. BI-RADS 2 - Recommend routine screening in 1 year.</p>\n\n<p>RIGHT BREAST: Negative. BI-RADS 1 - Recommend routine screening in 1 year.</p>\n\n<p>OVERALL BI-RADS 2 (Benign)</p>\n</div>"
  },
  "identifier": [
    {
      "use": "usual",
      "system": "http://www.siim.org/",
      "value": "a278028270041068"
    }
  ],
  "status": "final",
  "category": [
    {
      "coding": [
        {
          "system": "http://terminology.hl7.org/CodeSystem/v2-0074",
          "code": "RAD"
        }
      ]
    }
  ],
  "code": {
    "coding": [
      {
        "system": "http://snomed.info/sct",
        "code": "89164003",
        "display": "Breast lump"
      },
      {
        "system": "http://snomed.info/sct",
        "code": "384671006",
        "display": "microcalcifications in tumor present"
      },
      {
        "system": "http://loinc.org",
        "code": "39152-4"
      }
    ],
    "text": "Digital Diagnostic Mammogram Bilateral"
  },
  "subject": {
    "reference": "Patient/siimsally"
  },
  "effectiveDateTime": "2008-04-12",
  "issued": "2008-04-12T09:23:00+10:00",
  "performer": [
    {
      "reference": "Organization/siim",
      "display": "Society of Imaging Informatics in Medicine"
    }
  ],
  "conclusion": "Impression: LEFT BREAST: Expected lumpectomy changes. Benign. BI-RADS 2 - Recommend routine screening in 1 year. RIGHT BREAST: Negative. BI-RADS 1 - Recommend routine screening in 1 year. OVERALL BI-RADS 2 (Benign)"
}
```
Next, we'll ask a follow-up about calcifications, which is referenced in the FHIR message.
```
Didn't this report show calcifications? Should I be concerned?
```
## Example 3: Another FHIR Diagnostic Report
We will use a FHIR Diagnostic Report from HL7 FHIR website. See https://www.hl7.org/fhir/diagnosticreport-example-dxa.json for the sample message.
```
Given the following HL7 FHIR JSON message, what is this patient diagnosed with?
{
  "resourceType" : "DiagnosticReport",
  "id" : "102",
  "text" : {
    "status" : "generated",
    "div" : "<div xmlns=\"http://www.w3.org/1999/xhtml\">\n\t\t\t<h2>DXA BONE DENSITOMETRY</h2>\n\t\t\t<table>\n\t\t\t\t<tr>\n\t\t\t\t\t<td>NAME</td>\n\t\t\t\t\t<td>XXXXXXX</td>\n\t\t\t\t</tr>\n\t\t\t\t<tr>\n\t\t\t\t\t<td>DOB</td>\n\t\t\t\t\t<td>10/02/1974</td>\n\t\t\t\t</tr>\n\t\t\t\t<tr>\n\t\t\t\t\t<td>REFERRING DR</td>\n\t\t\t\t\t<td>Smith, Jane</td>\n\t\t\t\t</tr>\n\t\t\t\t<tr>\n\t\t\t\t\t<td>INDICATIONS</td>\n\t\t\t\t\t<td>Early menopause on estrogen levels. No period  for 18 months</td>\n\t\t\t\t</tr>\n\t\t\t\t<tr>\n\t\t\t\t\t<td>PROCEDURE</td>\n\t\t\t\t\t<td>Dual energy x-ray absorptiometry (DEXA)</td>\n\t\t\t\t</tr>\n\t\t\t</table>\n\t\t\t<h3>Bone Mineral Density</h3>\n\t\t\t<table>\n\t\t\t\t<tr>\n\t\t\t\t\t<td>Scan Type</td>\n\t\t\t\t\t<td>Region</td>\n\t\t\t\t\t<td>Measured</td>\n\t\t\t\t\t<td>Age</td>\n\t\t\t\t\t<td>BMD</td>\n\t\t\t\t\t<td>T-Score</td>\n\t\t\t\t\t<td>Z-Score</td>\n\t\t\t\t\t<td>?BMD(g/cm2)</td>\n\t\t\t\t\t<td>?BMD(%)</td>\n\t\t\t\t</tr>\n\t\t\t\t<tr>\n\t\t\t\t\t<td>AP Spine</td>\n\t\t\t\t\t<td>L1-L4</td>\n\t\t\t\t\t<td>17/06/2008</td>\n\t\t\t\t\t<td>34.4</td>\n\t\t\t\t\t<td>1.148 g/cm²</td>\n\t\t\t\t\t<td>-0.4</td>\n\t\t\t\t\t<td>-0.5</td>\n\t\t\t\t\t<td>-</td>\n\t\t\t\t\t<td>-</td>\n\t\t\t\t</tr>\n\t\t\t\t<tr>\n\t\t\t\t\t<td>Left Femur</td>\n\t\t\t\t\t<td>Neck</td>\n\t\t\t\t\t<td>17/06/2008</td>\n\t\t\t\t\t<td>34.4</td>\n\t\t\t\t\t<td>0.891 g/cm²</td>\n\t\t\t\t\t<td>-1.0</td>\n\t\t\t\t\t<td>-0.9</td>\n\t\t\t\t\t<td>-</td>\n\t\t\t\t\t<td>-</td>\n\t\t\t\t</tr>\n\t\t\t\t<tr>\n\t\t\t\t\t<td>Left Femur</td>\n\t\t\t\t\t<td>Total</td>\n\t\t\t\t\t<td>17/06/2008</td>\n\t\t\t\t\t<td>34.4</td>\n\t\t\t\t\t<td>0.887 g/cm²</td>\n\t\t\t\t\t<td>-1.2</td>\n\t\t\t\t\t<td>-1.3</td>\n\t\t\t\t\t<td>-</td>\n\t\t\t\t\t<td>-</td>\n\t\t\t\t</tr>\n\t\t\t\t<tr>\n\t\t\t\t\t<td>Right Femur</td>\n\t\t\t\t\t<td>Neck</td>\n\t\t\t\t\t<td>17/06/2008</td>\n\t\t\t\t\t<td>34.4</td>\n\t\t\t\t\t<td>0.885 g/cm²</td>\n\t\t\t\t\t<td>-1.0</td>\n\t\t\t\t\t<td>-1.0</td>\n\t\t\t\t\t<td>-</td>\n\t\t\t\t\t<td>-</td>\n\t\t\t\t</tr>\n\t\t\t\t<tr>\n\t\t\t\t\t<td>Right Femur</td>\n\t\t\t\t\t<td>Total</td>\n\t\t\t\t\t<td>17/06/2008</td>\n\t\t\t\t\t<td>34.4</td>\n\t\t\t\t\t<td>0.867 g/cm²</td>\n\t\t\t\t\t<td>-1.4</td>\n\t\t\t\t\t<td>-1.4</td>\n\t\t\t\t\t<td>-</td>\n\t\t\t\t\t<td>-</td>\n\t\t\t\t</tr>\n\t\t\t</table>\n\t\t\t<p>Assessment:</p>\n\t\t\t<ul>\n\t\t\t\t<li>The Spine L1-L4 BMD is normal.</li>\n\t\t\t\t<li>The Left Femur Neck BMD is in the osteopenic range. Relative fracture risk is about 2.</li>\n\t\t\t\t<li>The Left Femur Total BMD is in the osteopenic range. Relative fracture risk is about 2.</li>\n\t\t\t\t<li>The Right Femur Neck BMD is in the osteopenic range. Relative fracture risk is about 2.</li>\n\t\t\t\t<li>The Right Femur Total BMD is in the osteopenic range. Relative fracture risk is about 2.</li>\n\t\t\t</ul>\n\t\t\t<p>\n\t\t\t\t<b>COMMENT</b>\n\t\t\t</p>\n\t\t\t<p>Osteopenia on measured BMD. The estimated 10-year probability of fracture based on present age, gender and measured BMD is less than 10%. This absolute fracture risk remains low. A follow-up assessment may be considered in 2 to 3 years to monitor the trend in BMD.</p>\n\t\t\t<p>Thank you for your referral.  Dr Henry Seven  17/06/2008</p>\n\t\t\t<pre>\nNote:\nWHO classification of osteoporosis (WHO Technical Report Series 1994: 843)\n- Normal: T-score equal to -1.0 s.d. or higher\n- Osteopenia: T-score  between -1.0 and -2.5 s.d.\n- Osteoporosis: T-score equal to -2.5 s.d. or lower\n- Severe/Established osteoporosis: Osteoporosis with one or more fragility fracture.\nT-score: The number of s.d. from the mean BMD for a gender-matched young adult population.\nZ-score: The number of s.d. from the mean BMD for an age-, weight- and gender-matched population.\nReference for 10-year probability of fracture risk: Kanis JA, Johnell O, Oden A, Dawson A,  De Laet C, Jonsson B. Ten year probabilities of osteoporotic fractures according to BMD and diagnostic thresholds. Osteoporos.Int. 2001;12(12):989-995.\nGE LUNAR PRODIGY DENSITOMETER\n</pre>\n\t\t</div>"
  },
  "status" : "final",
  "code" : {
    "coding" : [{
      "system" : "http://loinc.org",
      "code" : "38269-7"
    }],
    "text" : "DXA BONE DENSITOMETRY"
  },
  "subject" : {
    "reference" : "Patient/pat2"
  },
  "effectiveDateTime" : "2008-06-17",
  "issued" : "2008-06-18T09:23:00+10:00",
  "performer" : [{
    "reference" : "Practitioner/3ad0687e-f477-468c-afd5-fcc2bf897809",
    "display" : "Dr Henry Seven"
  }],
  "result" : [{
    "reference" : "Observation/bmd"
  }],
  "conclusionCode" : [{
    "coding" : [{
      "system" : "http://snomed.info/sct",
      "code" : "391040000",
      "display" : "At risk of osteoporotic fracture"
    }]
  }]
}
```
Then let's follow up for suggestions on next steps.
```
What should I do next for my patient?
```
Let's summarize what's happening with our patient, in a simplified JSON format.
```
Please summarize the state of my patient in a simple JSON object, with the following fields: Patient Name, Patient ID, Gender, Age, Reason for Study, Diagnosis, Next Steps.
```
## Example 4: Build a FHIR Message
We will ask the LLM service to construct a FHIR message for us.
```
Construct an HL7 FHIR DiagnosticReport for my patient John Smith, who had a radiology Chest X-Ray done and the exam shows positive for pneumonia.
```
## Example 5: QA a FHIR message
We will provide a FHIR message with an erroneous value, let's see if it can pick it up and why.
```
Based on this HL7 FHIR JSON message, is there anything wrong with this message?
{  "resourceType" : "Observation",  "id" : "body-temperature",  "meta" : {    "profile" : ["http://hl7.org/fhir/StructureDefinition/vitalsigns"]  },  "text" : {    "status" : "generated",    "div" : "<div xmlns="http://www.w3.org/1999/xhtml"><p><b>Generated Narrative: Observation</b><a name="body-temperature"> </a><a name="hcbody-temperature"> </a></p><div style="display: inline-block; background-color: #d9e0e7; padding: 6px; margin: 4px; border: 1px solid #8da1b4; border-radius: 5px; line-height: 60%"><p style="margin-bottom: 0px">Resource Observation &quot;body-temperature&quot; </p><p style="margin-bottom: 0px">Profile: <a href="vitalsigns.html">Vital Signs Profile</a></p></div><p><b>status</b>: final</p><p><b>category</b>: Vital Signs <span style="background: LightGoldenRodYellow; margin: 4px; border: 1px solid khaki"> (<a href="http://terminology.hl7.org/6.0.2/CodeSystem-observation-category.html">Observation Category Codes</a>#vital-signs)</span></p><p><b>code</b>: Body temperature <span style="background: LightGoldenRodYellow; margin: 4px; border: 1px solid khaki"> (<a href="https://loinc.org/">LOINC</a>#8310-5)</span></p><p><b>subject</b>: <a href="patient-example.html">Patient/example</a> &quot;Peter CHALMERS&quot;</p><p><b>effective</b>: 1999-07-02</p><p><b>value</b>: 1036.5 C<span style="background: LightGoldenRodYellow"> (Details: UCUM code Cel = 'Cel')</span></p></div>"  },  "status" : "final",  "category" : [{    "coding" : [{      "system" : "http://terminology.hl7.org/CodeSystem/observation-category",      "code" : "vital-signs",      "display" : "Vital Signs"    }],    "text" : "Vital Signs"  }],  "code" : {    "coding" : [{      "system" : "http://loinc.org",      "code" : "8310-5",      "display" : "Body temperature"    }],    "text" : "Body temperature"  },  "subject" : {    "reference" : "Patient/example"  },  "effectiveDateTime" : "1999-07-02",  "valueQuantity" : {    "value" : 1036.5,    "unit" : "C",    "system" : "http://unitsofmeasure.org",    "code" : "Cel"  }} 
```
