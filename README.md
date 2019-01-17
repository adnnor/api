This API allows to process credit request from consumers via Magento.

## Credit Decision [/credit]
Process credit request of the customer.
### Request for credit [POST]
Request for credit line or loan account.
+ `JSON Request (POST)` consist of complete customer data.
+ `JSON Response (201)` returns acceptance of the credit/loan request.
+ `JSON Response (403)` returns rejection of the credit/loan request.

#### Request Attributes`(application/json)`

+ name (object, required) - `Customer name`
    + prefix: (string, optional) `Prefix of customer name`
    + first: (string, required) `Customer first Name`
    + middle: (string, optional) `Customer middle name`
    + last: (string, required) `Customer last Name`
    + suffix: (string, optional) `Initial of customer name`
+ email: (string, required) `Customer email address`
+ gender: (number, required) `Customer gender id 1: Male, 2: Female, 3: Not specified`
+ dob: (string, required) `Customer date of birth e.g. 12/15/2000`
+ address (object, required) - Customer addresses
    + name (object, required) `Customer name`
        + prefix: (string, optional) `Prefix of customer name`
        + first: (string, required) `Customer first Name`
        + middle: (string, optional) `Customer middle name`
        + last: (string, required) `Customer last Name`
        + suffix: (string, optional) `Initial of customer name`
    + company: (string, required) `Company name`
    + street (array, required) - Street address
        - `first line`
        - `second line`
    + city: (string, required) `City name`
    + country: (string, required) `Country code`
    + state: (string, required) `State/Province`
    + zip: (string, required) `Zip/Postal code`
    + phone: (string, required) `Phone number`

**JSON representation**
```json
{
    "name": {
        "prefix": "",
        "first": "John",
        "middle": "",
        "last": "Doe",
        "suffix": ""
    },
    "email": "example@domain.com",
    "gender": 1,
    "dob": "12/15/2000",
    "address": {
        "name": {
            "prefix": "",
            "first": "John",
            "middle": "",
            "last": "Doe",
            "suffix": ""
        },
        "company": "Good Company LLC",
        "street": [
            "Office xxx, 1st Floor",
            "xxx xxx xxx"
        ],
        "city": "Good City",
        "country": "GC",
        "state": "Good State",
        "zip": "111111",
        "phone": "+11111111"
    }
}
```