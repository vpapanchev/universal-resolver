![DIF Logo](https://raw.githubusercontent.com/decentralized-identity/universal-resolver/master/docs/logo-dif.png)

# DIF Universal Resolver

This repository was forked from [DIF Universal Resolver](https://github.com/decentralized-identity/universal-resolver) to be used locally by our Interoperable SSI Access Control System. All credits go to [DIF Identifiers&Discovery Working Group](https://github.com/decentralized-identity/identifiers-discovery/).

# DID Resolver

This is driver-architecture resolver for Decentralized Identifiers (DIDs) - Each DID Method Resolution is handled by the appropriate driver for this DID Method. Currently supported DID Methods:

| Driver Name | Driver Version | DID Method Spec Version | Docker Image or URL | Description |
| ----------- | -------------- | ----------------------- | ------------------- | ----------- |
| [did-kilt](https://github.com/KILTprotocol/kilt-did-driver) | 2.3.0 | [1.1](https://github.com/KILTprotocol/kilt-did-driver/blob/master/docs/did-spec/spec.md) | [kiltprotocol/kilt-did-driver](https://hub.docker.com/r/kiltprotocol/kilt-did-driver)| KILT Protocol |

## Setup

TODO: Explain how to configure drivers: docker-compose and  config.json

## How to use

TODO: Define API endpoint with an example

Send HTTP GET requests to this service to resolve DIDs. See examples:
	
	curl -X GET http://localhost:8080/1.0/identifiers/did:kilt:light:014t2hLQ3vmCoNf7jDZnQqzFF9JWaYP9qrFW6VTr3ayHtW2MyK:z1Ac9CMtYCTRWjetJfJqJoV7FcNH49Aqrz4yFeVRQKtH8EvsjjsYzirQ2bB8jRJdRTxr5pJVwP9MiCf78JpaS6U
	
You can also use an "Accept" header to request the DID document in a specific representation, e.g.:

	curl -H "Accept: application/did+ld+json" https://dev.uniresolver.io/1.0/identifiers/did:sov:WRfXPg8dantKVubE3HX8pw
	curl -H "Accept: application/did+json" https://dev.uniresolver.io/1.0/identifiers/did:sov:WRfXPg8dantKVubE3HX8pw
	curl -H "Accept: application/did+cbor" https://dev.uniresolver.io/1.0/identifiers/did:sov:WRfXPg8dantKVubE3HX8pw
