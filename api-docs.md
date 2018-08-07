```
Drug Pricing API Specs
-------------------------------
Type:
  - RESTful
  - JSON return
-------------------------------
Pricing request contents:
  - authentication (examples: api-key, basic auth)*
  - drug NDC (preferably multiple NDC's)*
  - quantity*
  - radius (required if not supplied a NPI)
  - zip code (required if not supplied a NPI)
  - NPI (not required but highly recommended)
  notes:
  Pagination of results is acceptable, and recommended. Would require fields for number of results per page and page number.
  * required
-------------------------------
Pricing response contents:
  - list of pharmacies (containing specific pharmacy location details, address, NPI, etc.)
  - drug NDC
  - drug label
  - quantity

  * all fields are required

```
