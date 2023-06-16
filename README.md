# REST-API-HTTP-Verbs-Status-Codes
Core components of REST APIs - HTTP verbs and status codes
API Issues:
1. Lack of proper documentation.
2. API parameters and results are vaguely defined.


Good designed API looks as below:

Get /account/12345

Response:
<account>
<account_number>12345</account_number>
    <balance currency="usd">100.00</balance>

    <link rel="deposit" href="/account/12345/deposit" >

    <link rel="deposit" href="/account/12345/withdraw" >

    <link rel="deposit" href="/account/12345/transfer" >

    <link rel="deposit" href="/account/12345/close" >
<account>

Well designed APIs are self-descriptive, improving their usability and discoverability. When a client interacts with a resource, the API provides information not just about the resource itself, but also about related resources and possible actions, all represented through hypermedia links.

In the example above, when we request to query account 12345, not only do we receive the account balance ($100), but the response also guides us on the next steps and how to execute them via URIs. For instance, we could deposit more money into account 12345 by navigating to /account/12345/deposit.

It is essential to understand that there isn’t always a direct one-to-one mapping between HTTP verbs and service methods. For example, the GET verb can be used to retrieve a single resource or an entire list of resources. Similarly, both PUT and PATCH verbs can be used to modify a resource. However, the PATCH verb is specifically used when we want to make partial modifications to a resource. 

![Alt text](image.png)