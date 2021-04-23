### Standard Charges File

| Field | Name | Type | Definition | Required |
| ----- | ---- | ---- | ---------- | -------- |
| **reporting_entity_name** | Entity Name | String | The name of the entity publishing the machine-readable file. | Yes |
| **reporting_entity_tin** | Tax Identification Number | String | The unique identification number issued either by the Social Security Administration or by the Internal Revenue Service (IRS). | Yes |
| **last_update_on** | Last Update On | String | The date in which the file was last updated. Date must be in an ISO 8601 format (e.g. YYYY-MM-DD) | Yes |
| **standardcharges** | Standard Charges Object | Array | An array of standardcharges object types | Yes |

#### Standard Charges Object

This type defines a standardcharges object.

| Field | Name | Type | Definition | Required |
| ----- | ---- | ---- | ---------- | -------- |
| **description** | Description | String | Brief description of the item/service | Yes |
| **billing_code_type** | Billing Code Type | String | Allowed values: "CPT", "HCPCS", "ICD", and "DRG". | No |
| **billing_code_type_version** | Billing Code Type Version | String | There might be versions associated with the `billing_code_type`. For example, Medicare is currently using ICD's version 10 | No |
| **billing_code** | Billing Code | String | The code used by a plan or issuer or its in-network providers to identify health care items or services for purposes of billing, adjudicating, and paying claims for a covered item or service. | No |
| **billing_class** | Billing Class | String | Allowed values: "facility", "professional" | Yes |
| **account_base_class** | Account Base Class | String | Allowed values: "inpatient", "outpatient", "emergency" | Yes |
| **revenue_code** | Revenue Code | Number | The hospital revenue code associated with the charge, if applicable. | No |
| **ndc** | NDC Code | String | NDC code, if applicable to service | No |
| **gross_charge** | Gross Charge | Number | The dollar amount of the service's gross charge | Yes |
| **cash_rate** | Discounted Cash Rate | Number | The dollar amount of the service's discounted cash price. If there is no discounted cash price, it can be the same value as the gross charge. | Yes |
| **minimum_negotiated_rate** | Minimum Negotiated Rate | Number | The dollar amount of the lowest negotiated price for the service. | Yes |
| **maximum_negotiated_rate** | Maximum Negotiated Rate | Number | The dollar amount of the highest negotiated price for the service. | Yes |
| **negotiated_rates** | Negotiated Rates | Array | This is an array of negotiated rate details object types. | Yes |


#### Negotiated Rate Details Object

This type defines a negotiated rate object.

| Field | Name | Type | Definition | Required |
| ----- | ---- | ---- | ---------- | -------- |
| **payer_name** | Payer Name | String | The name of the insurance company or other payer. | Yes |
| **plan_name** | Plan Name | String | The insurance plan name. | Yes |
| **negotiated_rate** | Negotiated Rate | Number | The dollar amount negotiated for the service | Yes |
| **expiration_date** | Expiration Date | String | The date in which the agreement for the `negotiated_price` ends. Date must be in an ISO 8601 format (e.g. YYYY-MM-DD) | No |

