Errors
======

If an error occured the result of the API call will be a JSON with the following format
```[<error_code>, <error_message>]```

Code Reference
--------------
<table>
    <th>
        <td>Code</td>
        <td>Message</td>
        <td>Meaning</td>
    </th>
    <tr>
        <td>200</td>
        <td>*API specific messages*</td>
        <td>Success</td>
    </tr>
    <tr>
        <td>400</td>
        <td>Required data missing / Input missing</td>
        <td>This is a badly formed request with one or more fields of required data is missing.</td>
    </tr>
    <tr>
        <td>401</td>
        <td>Unauthorised</td>
        <td>The username/password/key_id/key_secret does not match the one on records</td>
    </tr>
    <tr>
        <td>500</td>
        <td>Some Error Occured</td>
        <td>In rare cases when this error is thrown, it means that something went wrong at our end and will be rectified soon.</td>
    </tr>
</table>