# eRoamingChargingNotifications Error Service

## Description

The CPO can transmit 'Error' ChargingNotifications which provide details when
an error occurred before charging starts, during the charging process, or an
abrupt charging end. The EMP relies on receiving this notification to
understand exactly when an error occurs, which they can then relay to their EV
customers.

Explore the specific details of the
[eRoamingChargingNotifications](https://hubject.github.io/oicp-cpo-2.3-api-doc/#tag/eRoamingChargingNotifications/operation/eRoamingChargingNotifications_V1.1)
using the linked OpenAPI.

## Process Diagram
![image](https://github.com/FirasHubject/OICP23_Integration_Guide/assets/135227574/c1a50b2e-0b95-4afa-8be6-cbd2a16e3e1f)


## Request

You can use this example to send a notification when an error happens during
the charging session. Adapt the example to include your OperatorID (in the
field placeholder `OperatorID`) and your EVSEID (in field placeholder
`EvseID`). In the `SessionID` field, use a sessionID obtained in the response
from a successful AuthoirzeStart request.

    
    
    curl --location 'https://service-qa.hubject.com/api/oicp/notificationmgmt/v11/charging-notifications' \
    --header 'Content-Type: application/json' \
    --data '{
        "CPOPartnerSessionID": "1234XYZ",
        "EMPPartnerSessionID": "2345ABC",
        "EvseID": "{{evseID}}",
        "ErrorType": "ConnectorError",
        "ErrorAdditionalInfo": "Plug was not connected, EVSEID timed out reached",
        "Identification": {
            "RFIDMifareFamilyIdentification": {
                "UID": "044A2DAA856280"
            }
        },
        "OperatorID": "{{operatorID}}",
        "SessionID": "3fe7378a-238f-4cf3-bca6-de657881f8c2",
        "Type": "Error"
    }'

## Response

    
    
    {
      "CPOPartnerSessionID": "1234XYZ",
      "EMPPartnerSessionID": "2345ABC",
      "Result": true,
      "SessionID": "3fe7378a-238f-4cf3-bca6-de657881f8c2",
      "StatusCode": {
        "AdditionalInfo": "Success",
        "Code": "000",
        "Description": "Success"
      }
    }

## Status Code

| OICP Status Codes | Description | Additional information |
| ----------------- | ----------- | ----------------------
| 000               | Success     |                        |
| Any other status code | Error   |  **[Status Code Page URL](https://github.com/hubject/OICP23_Integration_Guide/blob/main/04_Definitions/OICP-status-code.md)** |

  
## Best Practice

Having a clear understanding of the charging process is of crucial importance
for both the drivers and EMP. This notification serves as a valuable means for
EMPs to stay well-informed about any issues that may arise while authorizing
at a charging station and also, during the charging process. This information
can be readily shared with drivers, enabling them to take necessary steps in
response.

