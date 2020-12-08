# F5 APM Forward Proxy Connection-based Kerberos Authentication

Creates a mechanism to deploy APM Kerberos with connection-based auth behavior. APM NTLM is the only WIA method that currently supports connection-based auth (ability to persist on the authenticated user). Kerberos and Basic persist on the source IP, which is probelematic in NAT environments. This solution uses a sideband access policy evaluation to validate Kerberos credentials against a directory service, and requires the client to pass a valid authorization header in every request. The solution is optimized to query the directory service once for an authenticated user (and within expiry time).

