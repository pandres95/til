# OAuth2 Interaction Flow

1. Authentication, which can be
    1. by authorization: when you, given your client credentials (id and secret) delegate the authorization server (i.e. Facebook's login/authorize display) to ask your user for the credentials, then it returns you the `access_token`.
    2. by password: when you give your client credentials (both `client_id` and `client_secret`) and user's login information (`username` and `password`) to ask for access. The server returns your the `access_token` directly.
2. Consume: you give your `access_token` to get authorization for retrieve data.
