Authentication
==============

Authentication is the process of actually confirming the truth of an attribute, most likely the identity claimed by an user.

It might involve confirming the identity of a person by validating their identity documents, verifying the authenticity
of a website with a digital certificate, determining the age of an artifact by carbon dating, or ensuring that a product
is what its packaging and labeling claim to be. In other words, authentication often involves verifying the validity of at
least one form of identification.

OAuth
:::::

* http://oauthbible.com/

Specific implementations
::::::::::::::::::::::::

* :wiki:`Python/Django/Authentication`

Identity management and authentication
::::::::::::::::::::::::::::::::::::::

Keywords : Enterprise Identity Management, OpenID Connect, Oauth2

* https://github.com/coreos/dex : OpenID Connect Identity (OIDC) and OAuth 2.0 Provider with Pluggable Connectors. Written in Go, backend + frontend.
* https://github.com/ory/hydra : OAuth2 server with OpenID Connect - cloud native, security-first, open source API security for your infrastructure. Written in Go, backend only.
* https://github.com/ory/ladon : A SDK for access control policies: authorization for the microservice and IoT age. Inspired by AWS IAM policies. Written for Go.
