# Response Decision Tree

IF detection severity == High
AND user is privileged
THEN
  - Isolate endpoint
  - Disable user account
  - Create incident record
ELSE
  - Alert analyst
  - Monitor activity
