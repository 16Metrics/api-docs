Errors
======

If an error occurs the result of the API call will be a JSON array with the following format...   
```[<error_code>, <error_message>]```

Code Reference
--------------
<table>
    <tr>
        <th>Code</th>
        <th>Message</th>
        <th>Meaning</th>
    </tr>
    <tr>
        <td>200</td>
        <td>*API specific messages*</td>
        <td>Success</td>
    </tr>
    <tr>
        <td>400</td>
        <td>Required data missing / Input missing</td>
        <td>This is a badly formed request with one or more fields of required data missing.</td>
    </tr>
    <tr>
        <td>401</td>
        <td>Unauthorised</td>
        <td>The username/password/key_id/x-auth-token does not match the one on records or you do not have the permission to perform this action</td>
    </tr>
    <tr>
        <td>500</td>
        <td>Some Error Occured</td>
        <td>Something went wrong at our end and will be rectified soon.</td>
    </tr>
</table>