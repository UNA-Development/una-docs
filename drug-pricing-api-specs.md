## Drug Pricing API Specs

### Type:
  - RESTful
  - JSON return
-------------------------------
### Pricing request contents:
  - authentication (examples: api-key, basic auth)*
  - drug NDC (preferably multiple NDC's)*
  - quantity*
  - radius (required if not supplied a NPI)
  - zip code (required if not supplied a NPI)
  - NPI (not required but highly recommended)
  
    \*\*\*notes:
    - _Pagination of results is acceptable, and recommended. Would require fields for number of results per page and page number._

    \* required
-------------------------------
### Pricing response contents:
  - list of pharmacies (containing specific pharmacy location details, address, NPI, etc.)
  - drug NDC
  - drug label
  - quantity

  \* all fields are required

### Possible Return 1
```
  {
      [
        {
          NDC: 11111111111,
          drug_label: xxxxxxx,
          pricing: [
            {
              pharmacy:
              .......
            },
            {
              pharmacy:
              .......
            }
          ]
        },
        {
          NDC: 22222222222,
          drug_label: xxxxxxx
          pricing: [
            {
              pharmacy: ,
              .......
            },
            {
              pharmacy: ,
              .......
            }
          ]
        }
      ]
    }
```
### Example fields for each pharmacy returned
```
{
  npi: "1033124292",
  name: "WALGREENS 3085",
  pharmacy: "WALGREENS",
  phoneNumber: "2257531499",
  street1: "14444 COURSEY BLVD",
  street2: "",
  city: "BATON ROUGE",
  state: "LA",
  zipCode: "70817",
  price: "238.52"
}
```

### Possible Return 2
```
{
    "DrugPricing": [
      {
        ndc: 11111111111,
        drug_label: ,
        pharmacy: ,
        ...
      },
      {
        ndc: 22222222222,
        drug_label: ,
        pharmacy: ,
        ...
      }
    ]
  }
```
