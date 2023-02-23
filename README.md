# SASEF

One big problem we have when evaluating an authentication stack is the ability to compare them. To help you to understand and assess your security requirement coverage, we created the "Service Authentication Stack Evaluation Framework" (SASEF).

This framework assumes service client authentication to authenticate your access request. It is not covering the human authentication mechanism potentially required to retrieve the authentication proof.

Let's start by defining some knowledge before jumping into the diagram;
"Authentication" qualifies as the intention to prove the authenticity of something. And authenticity can be, in our context, a synonym of "genuine", "known", and "provable".
"Authorization" entitles the purpose of determining your access permissions.
By fulfilling the access constraints, an endpoint will authorize you to access the underlying function or resource call. 
The "bearer value" will generally produce an identity by authentication, and then this identity will be authorized.
In other words, if you don't present the arbitrary value to the first authorization system, the system will reject your request. For that reason, we call this step the "Bearer Authorization". 

You will increase your security score according to the bearer authorization value type.

For example, using an "API Key" as bearer authorization will not provide additional authentication. You are authorized to call the endpoint by your ability to present the API Key to this endpoint. And your permissions will be derived from the API Key associated ones.
Using a "Standalone Signed Assertion" as a bearer authorization will add a provenance authentication provided by the digital signature and additional information that could be bound to the assertion. But being able to authenticate a token via digital signature doesn't prove that the legit private key owner has generated it.
Using "Managed Signed Assertion" as a bearer authorization will permit to ensure that the assertion is generated and valid from an authorization server point of view. But will expose the token to inspection and potential misuse inducted by cryptographic verification.

I will not run the complete exercise; the idea is to let you understand how it works. You can calculate the SASEF score by accumulating your authentication stack fact evaluations. You will have a global score which could be distributed over a scale to evaluate your security level.

We know that SASEF is not a perfect system. Still, in favour of "progress over perfection," this framework is versioned and open to contributions.

<a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by-sa/4.0/88x31.png" /></a><br />This work is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/">Creative Commons Attribution-ShareAlike 4.0 International License</a>.