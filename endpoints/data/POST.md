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
        <th>Description</th>
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
</table>
