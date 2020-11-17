# Annotations of privacy practices re cross-border transfers (transfer of personal data to countries outside the EEA)

## Selection of privacy policies

The corpus consists of 100 privacy policies derived from two sources: a subset of 44 policies from 
the [APP-350 corpus](https://usableprivacy.org/data) and a subset of 56 policies of popular Android applications. These policies were downloaded on March 2, 2020.
- Policies from the APP-350 Corpus: the APP-350v1.1 consists of privacy policies of Android applications with annotations of the personal data types and the party accessing 
them (first or third-party). The APP350's annotation scheme and a subset of annotated privacy policies 
have been leveraged in our study, focusing our efforts to extend the annotations towards
policy practices relative to international transfers. Only a subset of 44 policies has been included, as the remaining were either not available in an EU country or the package name was not released.  
- Policies from other apps: A subset of 56 policies from popular Android applications were downloaded. We sought apps whose providers belong to a variety of countries by looking for the Country field in the digital certificate used to sign the app. Thus, 56 additional apps from 25 different countries were added to our corpus, most of them from the US, China, Spain, France and Australia.
     
## File Format

The HTML of each privacy policy is saved in the `original_policies` subdirectory. 
Individual annotated policies are saved in the `annotations` subdirectory. 
Each YAML file follows the format indicated below. The `policy_id` and the `policy_name` (package name) identifies 
the app's privacy policy. 

Each file breaks down a privacy policy into segments (i.e., paragraphs).
Each segment can be tagged (e.g. see `segment_id: 3 and segment_id: 52`)
 or not (e.g. see `segment_id: 2`). If a segment is annotated, 
 the specific annotated sentences are also defined.
```yaml
policy_id: '38'
policy_name: com.ea.gp.fifaultimate
segments:
- segment_id: 2
  segment_text: 'Privacy and Cookie Policy Last Updated: December 9; 2019 Effective
    Date: December 9; 2019 Your privacy is important to us; and we take our responsibility
    of caring for it seriously. This policy describes what information EA collects
    when you use the mobile; online and downloadable products and services offered
    by EA and its subsidiaries and when you attend live events hosted by or in connection
    with EA (collectively; ''Services''). For a list of our subsidiaries; visit https://www.sec.gov/Archives/edgar/data/712515/000071251519000019/ex-211subsidiariesofthereg.htm. '
  annotations: []
  sentences:
  - sentence_text: []
    annotations: []
- segment_id: 3
  segment_text: 'Personal information to be collected During linkage process to the
    membership; the company collects personal information such as names; sex; profile
    images; locations; email addresses; nationality and language settings of mobile
    devices for registration purposes; convenient customer service and other various
    services. Friends list also can be collected optionally. Contact information;
    shipping information; and/or payment information can be collected in the process
    of customer service and giveaway events. Automatically generated IP address; usage
    record; illegal usage record; device information can be collected. '
  annotations:
  - practice: Contact_Name_1stParty
    modality: PERFORMED
  - practice: Contact_E_Mail_Address_1stParty
    modality: PERFORMED
  - practice: Location_1stParty
    modality: PERFORMED
  - practice: Demographic_Gender_1stParty
    modality: PERFORMED
  - practice: Contact_Address_Book_1stParty
    modality: PERFORMED
  - practice: Contact_1stParty
    modality: PERFORMED
  - practice: Identifier_IP_Address_1stParty
    modality: PERFORMED
  sentences:
  - sentence_text: During linkage process to the membership; the company collects
      personal information such as names; sex; profile images; locations; email addresses;
      nationality and language settings of mobile devices for registration purposes;
      convenient customer service and other various services
    annotations:
    - practice: Contact_Name_1stParty
      modality: PERFORMED
    - practice: Contact_E_Mail_Address_1stParty
      modality: PERFORMED
    - practice: Location_1stParty
      modality: PERFORMED
    - practice: Demographic_Gender_1stParty
      modality: PERFORMED
  - sentence_text: Friends list also can be collected optionally.
    annotations:
    - practice: Contact_Address_Book_1stParty
      modality: PERFORMED
  - sentence_text: Contact information; shipping information; and/or payment information
      can be collected in the process of customer service and giveaway events.
    annotations:
    - practice: Contact_1stParty
      modality: PERFORMED
  - sentence_text: Automatically generated IP address; usage record; illegal usage
      record; device information can be collected.
    annotations:
    - practice: Identifier_IP_Address_1stParty
      modality: PERFORMED
  
  ...
  
- segment_id: 52
  segment_text: 'Information is collected by our parent company; Electronic Arts;
    Inc. For information regarding the European Economic Area (EEA); United Kingdom
    and Switzerland; Electronic Arts; Inc. holds certifications under the EU-US and
    Swiss-US Privacy Shield (which are available at www.privacyshield.gov/participant?id=a2zt0000000GwjBAAS&status=Active).
    When Electronic Arts; Inc. transfers information from the EEA; United Kingdom
    and Switzerland to other affiliates; agents or service providers that are outside
    the EEA; United Kingdom and Switzerland; it will do so in compliance with the
    ''Accountability for Onward Transfer'' principle of the Privacy Shield. '
  annotations:
  - practice: TRANSFER_USA_Adequacy_Decison
    modality: PERFORMED
  sentences:
  - sentence_text: Information is collected by our parent company; Electronic Arts;
      Inc. For information regarding the European Economic Area (EEA); United Kingdom
      and Switzerland; Electronic Arts; Inc. holds certifications under the EU-US
      and Swiss-US Privacy Shield
    annotations:
    - practice: TRANSFER_USA_Adequacy_Decison
      modality: PERFORMED
```

## Annotation Scheme

The annotation scheme relies on the legal analysis of GDPR (General Data Protection Regulation),
focusing on privacy practices relative to transfers of personal data to third countries.
We annotated two types of practices: TRANSFERS and COLLECTIONS. Each practice has one of 
two possible modalities: PERFORMED (i.e., a practice is explicitly described as being performed) 
and NOT_PERFORMED (i.e., a practice is explicitly described as not being performed). 

As for TRANSFERS, three key elements are annotated: the mechanism enabling transfers of personal 
data to third countries, the targeted third countries, and the reference to the
means to abtain a copy of the safeguards.

| Mechanism enabling transfers     | Description |
| --------------------------------- | ----------- |
|Adequacy_Decision |	The privacy policy describes adequacy decision as mechanism enabling a transfer of personal data to third countries|
|Binding_Corporate_Rules |	The privacy policy describes Binding corporate rules as mechanism enabling a transfer of personal data to third countries|
|Standard_Data_Protection_Clauses	| The privacy policy describes Standard data protection clauses as mechanism enabling a transfer of personal data to third countries|
|Approved_Code_Conduct 	| The privacy policy describes Approved code of conduct  as mechanism enabling a transfer of personal data to third countries|
|Approved_Certification_Mechanism	| The privacy policy describes Approved certification mechanism as mechanism enabling a transfer of personal data to third countries|
|Explicit_Consent	| The privacy policy describes Consent as mechanism enabling a transfer of personal data to third countries|
|Unspecified_Mechanism |	The privacy policy does not describe any of the aforementioned mechanisms.|
 
| Targeted third country    |   Description       |
| --------------------------------- | ----------- |
|Unspecified_Country | 	The privacy policy describes a transfer of personal data to an unspecified destination country.|
|USA	|The privacy policy describes a transfer of personal data to USA. It could be either explicitly defined or implicitly (e.g.  inferred from the EU-US Privacy Shield). UPDATE: It was invalidated in July, 1, 2020|
|Australia	|The privacy policy describes a transfer of personal data to Australia. It could be either explicitly defined or implicitly (e.g.  inferred from an adequacy decision among the involved country and the EU).|
| ...  |   ... |

| Reference to obtain a copy of safeguards   |   Description       |
| --------------------------------- | ----------- |
|       Copy                            |     The privacy policy provides a reference to the means by which to obtain a copy of the safeguards or where it has been made available.|
| Without_Copy   |  The privacy policy does not provide a reference to the means by which to obtain a copy of the safeguards.  |

We rely on the types of personal data collected from mobile devices defined in the [APP-350 corpus](https://usableprivacy.org/data).
Three key elements are annotated: the personal data type, the party who accessing them, and the 
 type of third party.

| Data Type                         | Description |
| --------------------------------- | ----------- |
| Contact                           | The policy describes collection of unspecified contact data. |
| Contact_Address_Book              | The policy describes collection of contact data from a user's address book on the phone. |
| Contact_Name                      | The policy describes collection of the user's name. |
| Contact_City                      | The policy describes collection of the user's city. |
| Contact_E_Mail_Address            | The policy describes collection of the user's e-mail. |
| Contact_Password                  | The policy describes collection of the user's password. |
| Contact_Phone_Number              | The policy describes collection of the user's phone number. |
| Contact_Postal_Address            | The policy describes collection of the user's postal address. |
| Contact_ZIP                       | The policy describes collection of the user's ZIP code. |
| Demographic                       | The policy describes collection of the user's unspecified demographic data. |
| Demographic_Age                   | The policy describes collection of the user's age (including birth date and age range). |
| Demographic_Gender                | The policy describes collection of the user's gender. |
| Identifier                        | The policy describes collection of the user's unspecified identifiers. |
| Identifier_Ad_ID                  | The policy describes collection of the user's ad ID (such as the Google Ad ID). |
| Identifier_Cookie_or_similar_Tech | The policy describes collection of the user's HTTP cookies, flash cookies, pixel tags, or similar identifiers. |
| Identifier_Device_ID              | The policy describes collection of the user's device ID (such as the Android ID). |
| Identifier_IMEI                   | The policy describes collection of the user's IMEI (International Mobile Equipment Identity). |
| Identifier_IMSI                   | The policy describes collection of the user's IMSI (International Mobile Subscriber Identity). |
| Identifier_IP_Address             | The policy describes collection of the user's IP address. |
| Identifier_MAC                    | The policy describes collection of the user's MAC address. |
| Identifier_Mobile_Carrier         | The policy describes collection of the user's mobile carrier name or other mobile carrier identifier. |
| Identifier_SIM_Serial             | The policy describes collection of the user's SIM serial number. |
| Identifier_SSID_BSSID             | The policy describes collection of the user's SSID or BSSID. |
| Location                          | The policy describes collection of the user's unspecified location data. |
| Location_Bluetooth                | The policy describes collection of the user's Bluetooth location data. |
| Location_Cell_Tower               | The policy describes collection of the user's cell tower location data. |
| Location_GPS                      | The policy describes collection of the user's GPS location data. |
| Location_IP_Address               | The policy describes collection of the user's IP location data. |
| Location_WiFi                     | The policy describes collection of the user's WiFi location data. |
| SSO                               | The policy describes receiving data from an unspecified single sign on service. |
| Facebook_SSO                      | The policy describes receiving data from the Facebook single sign on service. |

| Party    | Description |
| -------- | ----------- |
| 1stParty | The policy describes collection of data from the user by the app publisher. |
| 3rdParty | The policy describes collection of data from the user by ad networks, analytics services, or other third parties. |

| Third Party Type    | Description |
| -------- | ----------- |
|Advertisement_Marketing |	The privacy policy describes that the destination is a third party service for advertising purposes.| 
Analytics_Design_optimization |	The privacy policy describes that the destination is a third party for analytics purposes.|
Social_media	| The privacy policy describes that the destination is a third party for social media purposes.|
Support_Development|	The privacy policy describes that the destination is third party service for development or support purpose (e.g., email, storage, security, location, video, hosting, etc.)|



