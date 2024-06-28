[![published](https://static.production.devnetcloud.com/codeexchange/assets/images/devnet-published.svg)](https://developer.cisco.com/codeexchange/github/repo/ciscotee/CiscoSecureEndpoint-FindDuplicateGUID)
# CiscoSecureEndpoint-FindDuplicateGUID
The Workflow will list computer with GUID and find duplicate GUID. The list of computer API in Cisco Secure Endpoint available on API [V1](https://developer.cisco.com/docs/secure-endpoint/v1-api-reference-computer/)

The Workflow work together with sub workflow (Atomics) "Secure Endpoint - List Computers" that you need ti import after import the workflow.
The Output of workflow will keep under variable "Duplicate_Output" then you can use this to send out update such as Cisco Webex or Email if needed.

## Requirements
  > [!IMPORTANT]
  >  -  Integrate Cisco Secure Endpoint with Cisco XDR.
  >  -  After Integration you will automatic create out of box target call ["Secure Endpoint.."](https://docs.xdr.security.cisco.com/Content/Automate/targets-integration-module.htm), The workflow already use condition to select the target start with "Secure Endpoint*".
  >  -  However, if your migrate SecureX to Cisco XDR. You able to use the "AMP_Target" for the target group. Then you need to update target group in the workflow.
  >  -  Output variable is under workflow.

## Installation
  1. Browse to your Cisco XDR, click the **Automate** and choose **Workflows**.
  2. Click on **Import Workflow**.
  3. Navigate **Import From**, click on **Browse**
  4. Copy [CiscoSecureEndpoint_Find_duplication_GUID.json](https://github.com/ciscotee/CiscoSecureEndpoint-FindDuplicateGUID/blob/main/CiscoSecureEndpoint_Find_duplication_GUID.json) and paste the content inside of the text window.
  5. Click on **Import**. You will get a warning about *missing sub work-flows*, however please click **Continue**. (Sub work-flow will import later).
  6. You will see workflow impored and show *Import completed*.
  7. Click **View Workflow** you will see "1 Invalid Actions".
  8. Select activity **"Secure Endpoint - List Computers"**, click **"Import Sub-Workflow"**.
  9. Navigate **Import From**, click on **Browse**.
  10. Copy [CiscoSecureEndpoint_List_Computers.json](https://github.com/ciscotee/CiscoSecureEndpoint-FindDuplicateGUID/blob/main/Atomics/CiscoSecureEndpoint_List_Computers.json) and paste the content inside of the text window.
  11. Click on **Import**. You will get a warning, however please click on **Update** to get everything sorted.
  12. The workflow ready to validate, click "Validate" button.

## Usage
  - Open workflow then click **"Run"**
  - After running completed, You will see the output in workflow variable "Duplicate_Output".
  - You can update your workflow with data in variable to send out the details or copy it out.

## Workflow Steps
  - List of all computers in your Cisco Secure Endpoint tenant.
  - Transform the data and find duplicate GUID from the respond output.
  - Update hosts that have duplicate GUID in variable.
    **Example Output

            'GUID': guid,
            'Hosts with duplicate GUIDs found': amount of hosts that use the GUID,
            'Details':
              Hostname: Last Seen: Policy Name:

## Notes
You can update triggers for daily run the workflow on [Schedule Rule](https://docs.xdr.security.cisco.com/Content/Automate/rules-schedule.htm).

