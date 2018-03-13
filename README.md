# Dockerized Hyperledger Explorer
___
A dockerized version of Hyperledger Blockchain Explorer.

![](https://cdn.rawgit.com/eluft84/docker-hlf-explorer/master/example/explorer_overview.gif)

## About Hyperledger Blockchain Explorer
___
Hyperledger Explorer is a simple, powerful, easy-to-use, highly maintainable, open source browser for viewing activity on the underlying blockchain network. [Source on GitHub](https://github.com/hyperledger/blockchain-explorer)

## Requiments
___
Install
* [Docker](https://www.docker.com/)
* [Docker-Compose](https://docs.docker.com/compose/)
* [Node.js](https://nodejs.org/en/)


## Preperation
___
1. Update the `config.json` based on your network setup.
    * Peer config (`name, mspid, hostname`)
    * Admin Certificate Path (`admin`)
    * `channel-name`

2. Replace the crypto-config folder with your network crypto configuration

3. Add the **services** from the `docker-composer.yaml` to your project `docker-composer.yaml` file

4. Start you network and open in the browser `http://localhost:8080`

If you are connecting to a **TLS** fabric peer, please modify the protocol (grpc->grpcs) and port (9050-> 9051) in the peer url and add the tls_cacerts in the config.json `org1.peer1`. Depending on this key, the application decides whether to go TLS or non TLS route.

## End-2-End Example

Start `start-example-network.sh`. This will setup a End-2-End Blockchain Network with:
* Fabric-Ca
* 1 Peer with CouchDB as State Database
* 1 Solo Orderer
* Fabcar-Chaincode
* Blockchain Explorer


