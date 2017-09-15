Authentication
==============

Authentication is the process of actually confirming the truth of an attribute, most likely the identity claimed by an user.

It might involve confirming the identity of a person by validating their identity documents, verifying the authenticity
of a website with a digital certificate, determining the age of an artifact by carbon dating, or ensuring that a product
is what its packaging and labeling claim to be. In other words, authentication often involves verifying the validity of at
least one form of identification.

OAuth
:::::

* `The OAuth Bible <http://oauthbible.com/>`_

Specific implementations
::::::::::::::::::::::::

* :wiki:`Python/Django/Authentication`

Identity management and authentication
::::::::::::::::::::::::::::::::::::::

Keywords : Enterprise Identity Management, OpenID Connect, Oauth2

* `DEX (project by CoreOS) <https://github.com/coreos/dex>`_: OpenID Connect Identity (OIDC) and OAuth 2.0 Provider with Pluggable Connectors. Written in Go, backend + frontend.
* `Hydra <https://github.com/ory/hydra>`_: OAuth2 server with OpenID Connect - cloud native, security-first, open source API security for your infrastructure. Written in Go, backend only.
* `Ladon <https://github.com/ory/ladon>`_: A SDK for access control policies: authorization for the microservice and IoT age. Inspired by AWS IAM policies. Written for Go.
* Maybe https://github.com/cloudfoundry/uaa ?

HTTP Middlewares that can be considered in front of APIs: `Kong <https://getkong.org/>`_ (written in Lua), `Istio <https://istio.io/>`_ (a bit out of topic, but maybe not). 
