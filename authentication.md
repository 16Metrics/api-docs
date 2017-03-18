Authentication
==============

All server side requests like pushing of payment event, refund event etc. must be authenticated with a key_id and a key_secret. This can be generated from your dashboard. You can have multiple API keys active at given point in time. Any client side api calls involving the key_secret is not recommended and explicitly discouraged. If you believe your key is compromised please disable the key from your dashboard or contact support@16metrics.com

Every api call expects the key_id to be sent as a part of the body as detailed in the endpoint definitions. However, the key_secret is expected to be sent in the header with the name ```x-auth-token```