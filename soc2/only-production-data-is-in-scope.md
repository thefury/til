# Only Production Data is In Scope for SOC2

I had always thought that more of the system would be in scope for a SOC2 assessment,
as even staging and development environments could give information and increase the
attack surface. 

However, this certification only describes how we handle live production **data**.
So, if we are able to remove the chances of production PII in pre-production
environments, we can exclude them from scope.
