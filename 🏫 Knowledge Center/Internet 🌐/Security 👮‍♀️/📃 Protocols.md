# 1 ⚔ **challenge–response authentication**
## 1.1 Definition
- A **protocol family** where authentication is based on a question-answer authentication
- E.g. TLS/3-way handshake

## 1.2 Example

> [!EXAMPLE]
> 1. Server sends a unique challenge value _**sc**_ to the client
> 2. Client sends a unique challenge value _**cc**_ to the server
> 3. Server computes _**sr**_ = hash(cc + secret) and sends to the client
> 4. Client computes _**cr**_ = hash(sc + secret) and sends to the server
> 5. Server calculates the expected value of _**cr**_ and ensures the client responded correctly
> 6. Client calculates the expected value of _**sr**_ and ensures the server responded correctly
> 
> WHERE
> 
> - _**sc**_ is the server-generated challenge
> - _**cc**_ is the client-generated challenge
> - _**cr**_ is the client response
> - _**sr**_ is the server response


