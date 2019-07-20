[oauth2-tips-token-validation](https://dzone.com/articles/oauth2-tips-token-validation)
````
Bearer Token Types

There are two types of OAuth2 bearer tokens:

    General Token that represents a string that has no meaning for the client (e.g., 2YotnFZFEjr1zCsicMWpAA). That type of bearer token cannot be validated by the Resource Server without direct communication with an Authorization Server.
    JWT Token represents the JSON object with statements (claims) about the user and token. The JWT token contains three separate parts: header, payload, and signature — each of them are base64-encoded for transferring. JWT tokens are not a part of core OAuth2 specification but mandatory for use with OpenID Connect. JWT token is the most popular way to exchange information about current authentication between microservices. More details can be found here.

Token Validation Methods

OAuth2 tokens can be validated using the following methods:

    Introspection. This is a method to get actual token information via special endpoint directly from the Authorization Server. Token information usually includes token type, status (active or not), user, client identifier, available OAuth2 scopes, and expiration time. A detailed description can be found in the specification https://tools.ietf.org/html/rfc7662 .The method requires direct interaction with Authorization Server for every token validation. It has high safety but low performance.
    Token validation by signature (JWT tokens only). This is a method when the token is validated according to its cryptographic signature and all required token information is received from token itself. It means that token validity is verified without interaction with an Authorization server, and if the token was revoked before its expiration, we’ll never know about it. So, this method is fast but less secure than introspection.
````
## Validating token at the gateway level
<img src="https://lh4.googleusercontent.com/2gIpJrIee-2UxyIFR_f-29RN8NT21wqqZhJ9Q2UUy5XLpaSyd4e1_dLsg3lLH3ZqWWMHGKDPfbsvDXNxoaWtAuKYE-7ZenLoFde37niMa9LSsxUyT5CJnU0FKxac6FWipXjnW9OH" alt="Validating token at the gateway level"/>

## JWT Bearer Client Authentication flow
```plantuml
@startuml

title JWT Beare Client Authentication


participantgroup#azure Client can be issuer
participant Client
participant Issuer
end 
participant Authorization Server
activecolor #lightyellow
autonumber 
activate Client
activate Issuer
activate Authorization Server

Client->Issuer:Request JWT
note left of Issuer:--POST /iam/access_token HTTP/1.1\n\nContent-Type: application/x-www-form-urlencoded\n\ngrant_type=authorization_code&\ncode=362ad374-735c-4f69-aa8e-bf384f8602de&\nclient_assertion_type=urn%3Aietf%3Aparams%3Aoauth%3A\n client-assertion-type%3Ajwt-bearer&\nclient_assertion=eyAiYWxnIjogIlJTMjU2IiB9.eyAic3ViIjogImp3...
Client<--Issuer: JWT(signed)
Client->Authorization Server: POST with client_assetion=the jwt,\n client_assertion_type=  urn:ietf:params:oauth:client-assertion-type:jwt-bearer
Authorization Server->Authorization Server: Validate  JWT
Client<--Authorization Server: Response( with access token)




note over Authorization Server:Reference https://backstage.forgerock.com/docs/am/5.5/oauth2-guide/
@enduml
```
