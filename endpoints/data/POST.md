data - POST
===========

This endpoint is used to push custom data to the event store for your account on app.16Metrics.com. Authentication required. Recommended to be used only on server side.   

Authentication
--------------

Authentication is required. The following parameters are required.
<table>
    <tr>
        <th>Name</th>
        <th>Part of</th>
        <th>Description</th>
    </tr>
    <tr>
        <td>key_id</td>
        <td>Request Body</td>
        <td>Your key_id</td>
    </tr>
    <tr>
        <td>x-auth-token</td>
        <td>Request Header</td>
        <td>Your key_secret</td>
    </tr>
</table>

Entity Reference - Payment Event
--------------------------------

The fields marked with * are compulsory. Additional custom fields can be pushed. Please ensure that there is no conflict with the field names mentioned below and that every custom field name has the prefix ```CS_```
<table>
    <tr>
        <th>Name</th>
        <th>Type</th>
        <th>Description/Value</th>
    </tr>
    <tr>
        <td>customer.city</td>
        <td>string</td>
        <td>City of your customer</td>
    </tr>
    <tr>
        <td>customer.email *</td>
        <td>email</td>
        <td>Email address of your customer. All grouping is based on this field</td>
    </tr>
    <tr>
        <td>customer.id</td>
        <td>string</td>
        <td>Your unique id for this customer</td>
    </tr>
    <tr>
        <td>event</td>
        <td>string</td>
        <td>payment</td>
    </tr>
    <tr>
        <td>event_id</td>
        <td>string</td>
        <td>Your unique id for this event</td>
    </tr>
    <tr>
        <td>payment_mode.bank</td>
        <td>string</td>
        <td>Name of the bank processing this charge</td>
    </tr>
    <tr>
        <td>payment_mode.brand</td>
        <td>string</td>
        <td>Visa/Master Card/Maestro etc.</td>
    </tr>
    <tr>
        <td>payment_mode.method</td>
        <td>string</td>
        <td>card/cash/net banking etc.</td>
    </tr>
    <tr>
        <td>payment_mode.type</td>
        <td>string</td>
        <td>Type of card. Mostly for card method. credit/debit</td>
    </tr>
    <tr>
        <td>product.name</td>
        <td>string</td>
        <td>Name of the product or subscription plan</td>
    </tr>
    <tr>
        <td>product.validity</td>
        <td>integer</td>
        <td>SaaS only field. The number of months that this plan is valid for</td>
    </tr>
    <tr>
        <td>status</td>
        <td>string</td>
        <td>success/failed</td>
    </tr>
    <tr>
        <td>transaction.amount</td>
        <td>integer</td>
        <td>Total amount paid in the smallest unit of the currency you are using. Ex. 2500 for 25 USD.</td>
    </tr>
    <tr>
        <td>transaction.currency</td>
        <td>integer</td>
        <td>Currency that this transaction is completed in. This field is currently not used as currency is derived from your account information</td>
    </tr>
    <tr>
        <td>transaction.fee</td>
        <td>integer</td>
        <td>Fees paid to payment gateways or banks for processing this charge in the smallest unit of the currency you are using</td>
    </tr>
    <tr>
        <td>transaction.mul_factor</td>
        <td>integer</td>
        <td>This is the factor for converting between storage unit and display unit for the amount. Ex. 1 USD = 100 Cents, therefore the value is 100</td>
    </tr>
    <tr>
        <td>transaction.tax</td>
        <td>integer</td>
        <td>Tax paid on the processing charge/fee in the smallest unit of currency you are using</td>
    </tr>
    <tr>
        <td>when.UTC *</td>
        <td>timestamp/integer</td>
        <td>Time of transaction. Seconds since epoch in UTC</td>
    </tr>
</table>

Sample Event - Payment
----------------------
```
    {
        "status" : "success",
        "customer" : {
            "city" : "",
            "id" : "cus_9ZGeoiitQjaKZs",
            "email" : "test@example.org"
        },
        "product" : {
            "name" : "Silver - Yearly",
            "validity" : 12
        },
        "transaction" : {
            "currency" : "usd",
            "amount" : 30000,
            "fee" : 900,
            "tax" : 0,
            "mul_factor" : 100
        },
        "event_id" : "ch_19QDoVECK8l3Nmz3u0fhXXPA",
        "when" : {
            "UTC" : 1489876755
        },
        "payment_mode" : {
            "brand" : "Visa",
            "type" : "credit",
            "method" : "card",
            "bank" : ""
        },
        "event" : "payment"
    }
```
