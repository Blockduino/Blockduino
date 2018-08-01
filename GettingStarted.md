# Blockduino Getting Started

### Setup

Each Blockduino board has an Ethereum account and an associated private key to sign Ethereum transactions originated from its account. The private key is stored in a secure enclave and each operation involving its use is secured by the Trusted Execution Environment.

>The Blockduino account and private key are generated as part of the onboarding process using a dedicated browser extension currently in development.

Before using a Blockduino in a smart-contract and as part of the onboarding process, a board needs to be registered with the Blockduino core contract. In most cases, to control a Blockduino board a smart-contract uses only the functions provided by the [Blockduino SDK](https://github.com/Blockduino/Contracts/blob/master/BlockduinoSDK.sol).

### The Big Picture

The Blockduino core contract and SDK provide high-level functions to control a Blockduino hardware from a smart-contract. The Blockduino SDK is the base class of any smart-contract for Blockduino and the core contract is deployed in the public Ethereum blockchain.

![Big Picture](https://github.com/Blockduino/Blockduino//blob/master/img/BlockduinoBigPicture.jpg)

Under the hood, each function in the Blockduino SDK results in a Remote Procedure Call (RPC) to the Blockduino board run-time. The run-time parses the request and takes the corresponding action, which in most cases is to execute instructions that operate on the Blockduino hardware.

All RPC requests are dispatched to the Blockduino board from the core contract, not the SDK. This way is possible to centralize requests and responses, to enforce access privileges, keep track of all requests and have other device management functions.

Once an RPC has been executed by a board, the run-time prepares a transaction with the response, signs it and sends it back to the Blockduino core contract, including the request ID it was received with. 

The Blockduino core contract, using the request ID, dispatches the response calling the callback indicated by the smart-contract executing the SDK request in the first place.

The diagram below illustrates the process:



### Blockduino Interface

The Blockduino core contract interface is composed of two parts:

1. Device Management
2. RPC Dispatcher

Contracts using the Blockduino SDK normally will not have to use any of these functions directly, but they are documented below to explain how the process works.

#### Device Management


#### RPC Dispatcher




