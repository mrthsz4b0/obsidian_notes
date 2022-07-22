# SecureSocketLayer/TransportLayerSecurity

-   Handshake protocol to establ trust & negotiate abo the secret key to encrypt & decrypt the conversation

1.  ClientHello msg w infos sa SSL/TLS version, Cryptographic algorithms & Data compression methods supported by the client
2.  ServerHello msg response that contains

-   A Cryptographic algorithm, choosen by the server from the algorithms list provided by the client
-   Servers digital certificate (contains the CA's private key encrypted signature)
-   Servers public key

4.  Client contacts the Certificate Authority to verify the server's digital certificate = confirms the authenticity of the web server
5.  ClientKeyExchange

-   Client shares secret key, encrypted w the server's public key (it is good, pq if a 3rd party aquires the public key he can't read the symmetric key as he can only read w the public key)

7.  Finished (from client) msg

-   Encrypted w the secret key, indicating that the handshake is complete

9.  Finished (from server) msg

-   Same as step 5.  
     

## Key Usage Extensions (for TLS)

-   Defines what actions are available 4 arbitrary certificate
-   Defined in terms of operation
-   Hexadec character defines the combo of extensions used

## Extended Key Usage extension or Enhanced Key Usage (for TLS)

-   Similar to KUE, but this is defined in terms of purpose & be easily extended upon

# Bearer token

- The Bearer Token is created for you by the Authentication server. When a user authenticates your application (client) the authentication server then goes and generates for you a Token. Bearer Tokens are the predominant type of access token used with [[OAuth 🍜]] 2.0. A Bearer token basically says "Give the bearer of this token access"
- In order to access an API for example you need to use an Access Token. Access tokens are short lived (around an hour). You **use the bearer token to get a new Access token**. To get an access token you send the Authentication server this bearer token along with your client id. This way the server knows that the application using the bearer token is the same application that the bearer token was created for. Example: I can't just take a bearer token created for your application and use it with my application it wont work because it wasn't generated for me.

POST /rsvp?eventId=123 HTTP/1.1  
Host: events-organizer.com  
Authorization: Bearer AbCdEf123456  
Content-Type: application/x-www-form-urlencoded  
User-Agent: Mozilla/5.0 (X11; Linux x86_64) AppleWebKit/1.0 (KHTML, like Gecko; Gmail Actions)

rsvpStatus=YES

-   A Bearer Token is set in the Authorization header of every Inline Action HTTP Request