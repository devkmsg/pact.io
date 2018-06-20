# What is Pact good for?

> When all you have is a hammer everything looks like a nail...

Like every tool, there are situations that Pact is great for, and situations where other tools would be better.
In the right situation, Pact should make testing your integrations _less painful_ than traditional integration tests.
In the wrong situation, it will probably be just as painful!

Pact is most valuable for designing and testing integrations where:

* You (or your team/organisation/partner organisation) control the development of both the consumer and the provider.
* The requirements of the consumer(s) are going to be used to drive the features of the provider.
* There is a small enough number of consumers for a given provider that the provider team can manage an individual relationship with each consumer team.

The primary advantages are:

* You can continuously evolve your codebase knowing that Pact will guarantee contracts are met.
* You can find out _before_ you deploy whether or not your applications will work together - there is no need to wait for slow e2e tests.
* The generation and verification of contracts is automatically managed by Pact.

Pact is fantastic tool for developing and testing intra-organisation microservices.

# What is it not good for?

* Testing APIs where the consumers cannot be individually identified (eg. public APIs).
* Testing new or existing providers where the functionality is not being driven or altered by the needs of particular consumers (eg. a public API or an OAuth provider)
* Testing providers where the consumer and provider teams do not have good communication channels.
* Performance and load testing.
* [Functional testing][functional-testing] of the provider - that is what the provider's own tests should do. Pact is about checking the contents and format of requests and responses.
* Situations where you cannot load data into the provider without using the API that you're actually testing (eg. public APIs). [Why?][pact-public-apis]
* Testing "pass through" APIs, where the provider merely passes on the request contents to a downstream service without validating them. [Why?][pass-through-apis]
* Use as a general purpose mocking or stubbing tool for browser driven tests. [Why?][isolated-tests]

[pact-public-apis]: https://github.com/pact-foundation/pact-ruby/wiki/Why-Pact-may-not-be-the-best-tool-for-testing-public-APIs
[pass-through-apis]: https://github.com/pact-foundation/pact-ruby/wiki/Why-Pact-may-not-be-the-best-tool-for-testing-pass-through-APIs
[functional-testing]: /best_practices/contract_tests_not_functional_tests.md
[isolated-tests]: /best_practices/consumer.md

# If you are unsure

If you're unsure whether Pact will be valuable for your team, see this [this page in the FAQ](/faq/convinceme.md).
