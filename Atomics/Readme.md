# Cisco Secure Endpoint List Computer
Update from Atomic "Secure Endpoint - Search Computers" This atomic workflow use to list of computers and continuing update offset with check on total results (computers) you have. The default value set to 100 but you update it to 500 if needed.
However, even it set to 100 it will use while loop to continue send request until total results < offset.

## Requirements
  - Integrate Secure Endpoint with Cisco XDR (SecureX)
  - Register Cisco XDR API Client
    - Click the Admnistration tab and choose API Clients in the navigation pane.
    - Click Generate API Client button, Enter a client name and select scope. (Note: The Secure Endpoint API will work with any of the selected Scopes.)
    - The Client ID and Client Password are generated (Noted: The Client Password cannot be recovered, Please store securely.
  - AMP_Target should be default target.
  - However, as atomic workflow it will use workflow target group as Target. Kindly check 
