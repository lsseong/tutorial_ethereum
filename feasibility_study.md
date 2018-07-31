## Feasibility Study- Rho Platform
This paper identifies key technologies and challenges in building the Rho platform, areas that require technical deep dive.

## Business Requirements
- Build a marketplace to support online trading of services and digital assets.
- Any users, designers, developer, manufacturers, supply chain can join the platform after KYC due diligence check.
- A digital wallet is provided to each user to hold fiat currencies and Rho token.
- The system facilitates fast cross-border transaction at low cost with utmost security without intermediaries.
- Service payment is made in Rho token. 
- Transfer of critical and confidential engineering data in a transparent auditable way is supported.
- An internal exchange is available for buying and selling tokens among users. 

### How it works
 - User create a company or personal account online, set a password. 2FA is optional for added security.
 - User is subject to initial KYC check. Upon passing, a wallet is activated.
 - User can deposit fiat currency in the wallet and use that to buy tokens on the exchange.
 - Seller list any item or service they wish to sell on the web marketplace. 
 - Seller can set a price up front or allow private negotiation at agreement stage.
 - Buyer can find the items or services they want through browsing or search function.
 - Buyer can contact and discuss product details with seller through a messaging channel before finalising a deal.
 - Upon agreeing a sale (including the final price), a smart contract is created to represent the transaction.
 - The smart contract includes payment schedule, expiry term and at what stage the proceed is released to the seller.
 - Typically, the contract will hold the full payment and only release the fund to seller when buyer confirms the receipt of good. 
 - A digital vault is available for seller to send their digital asset to buyer in a secured and auditable way. 
 - The terms of exchange are controlled by the smart contract in the form of steps to complete a transaction. 
 - Seller and buyer follow these steps and the smart contract will coordinate the release of asset and token in a pre-agreed manner.
 

https://www.w3.org/2015/03/wpay-usecases.html


## MircroServices to Implement Rho Ecosystem
At a very high level, microservices can be conceptualized as a way to create corporate applications, where applications are broken down into smaller, independent services, that are not dependent upon a specific coding language. Development teams are able to use the language tools they are most comfortable with and still achieve synergy in the application development process. Using the ideology of microservices, large complex applications can be divvied up into smaller building blocks of executables, that when recomposed offer all of the functionality of a large scale, highly complex application.


| Modules       | Function      | 
| ------------- |---------------| 
| Webservice module    | To host a web-based marketplace where marketing, sales and services take place  | 
| Workflow module      | To streamline and standardize business process and use cases as workflows      | 
| KYC module           | To perform client due diligence check before onboarding to the platform |
| Account module       | To hold account information and entitlement  |
| Wallet module        | To store fiat and tokens |
| Contract module      | Ethereum blockchain technology to manage the exchange of digital assets using smart contract | 
| Exchange module      | To facilitate buying and selling of Rho tokens |
| HSM module           | To safeguard digital keys and signing of transaction | 
| Vault module       | To store digital asset that seller is selling to buyer |

## Webservice Module
The webservice module provides an online platform to support the following activities:
 - Online marketplace
 - Account management
 - Transaction management
 - Token trading
 - Inbox and messaging

## Workflow Module
Workflow module implements business workflow by coordinating execution stages with other service modules. Some core business workflows include:
 - Account, cashflow and tokens management
 - Creation, execution and tracking of smart contract
 - Payments and transfer of digital assets

Key challenges in implementing a workflow module are:
 - Ability to interface with other service modules that are implemented in different languages
 - Ability to support quick turnaround of workflow changes
 - Ability to provide real time update on an order status
 - Ability to maintain user session states
 - Ability to recover session from failures/restart

### Messaging flow
A message flow is a sequence of processing steps that run between workflow and other modules. We will use the business workflows to design the messaging APIs between modules.

## KYC Module
Know-Your-Client module aims to provide an efficient, time and cost saving way of checking client background to prevent those participation with criminal intent. This module provides the tools our auditor needs to help meet due diligence obligations, including meeting regulatory requirements under Know Your Customer anti-money laundering and counter-terrorist financing legislation; and anti-bribery and corruption customer and counterparty due diligence and screening.


## Account and Wallet Module
User information is stored in an account database. Traditionally, account details are stored in a SQL database including user login password in a representation form. By representation that means we hash the password using a salt (which should be different for every user) and a secure 1-way algorithm and store that, throwing away the original password. Then, when you want to verify a password, you hash the value (using the same hashing algorithm and salt) and compare it to the hashed value in the database.

In a crytocurrency wallet, a user passphrase is typically used to secure private key. Is login password the same as wallet passphrase? 

### Cash management model
We need a clear understanding of cash management model and how it is supported in the framework:
 - Cash management - funding and withdrawal
 - Cash transfer when buying/selling tokens on internal exchange
 - Credit facility
 - e-statement

## Contract Module
A smart contract is a computer program that directly controls the transfer of digital currencies and/or assets between parties under certain conditions. A smart contract not only defines the rules and penalties related to an agreement in the same way that a traditional contract does, but it can also automatically enforce those obligations.

Smart contract runs in a virtual machine installed on distributed nodes. The Ethereum Virtual Machine (EVM) is one popular offering by the open-source community. 

We are going to list down a few transaction models, and study how the logics are implemented in smart contract codes using the available tools.

### Ethereum nodes
Two main options available: Geth (Go-Ethereum) or Parity.

### Writing a Smart Contract in Solidity
We will code a few smart contracts to implement some common use cases.

### Contract, transacton and blockchain
### ERC20 token API
The ERC20 is a technical specification that a new token on the platform implements. The implication here is wallets that support Ether (ETH) are also able to support all the ICO tokens that are ERC20-compliant. This explains why it is possible to create a system for a token exchange involving as many tokens as possible.

### EVM Memory and storage model
Merkle-Patricia trie

### web3.js - An Ethereum compatible JavaScript API
This is the main interface between workflow and contract modules. 

### Testing strategy
Testing is one of the most important yet overlooked aspect of the development of smart contract. We need extensive testing to ensure that the contract is working properly under any circumstances.

## Exchange Module
Exchange module provides a trading platform for users to buy and sell tokens via a central limit order book. 

## HSM Module
A hardware security module (HSM) is must in lifecycle management of cryptographic keys, which includes:
 - Public/private key generation
 - storage of keys
 - signing of transaction

Ethereum framework also has a built-in mechanism to manage these tasks. When one create an Ethereum account, user provides a passphrase to encrypt the private key. The encrypted private key is stored in a keystore file. Then to sign a transaction, user has to provide the correct passphrase to restore the private key from cipher text. 

Our HSM module is an integration of HSM and Ethereum framework such that storage and software signing functions are moved to hardware. The key never leaves the HSM and it is impossible to extract for maximum security.  

### Two factor authentication (2FA)
Two-factor authentication is an extra layer of security.

## Vault Module 
Private Design System (PDS) as central repository for storing and transfer of digital assets. We study the feasibility to interface between PDS and smart contract via the workflow module to suppor the following use cases:
 - PDS to notify smart contract that a digital asset is submitted by seller ready for collection
 - Smart contract to notify PDS that a digital asset is ready for release to buyer (typically after confirming payment)
 

## Private network
All the modules are hosted on private network with redundancy support.

### Servers
We look at security, redundancy and load balancing requirements of each module to work out the server architecture:
 - Operating system build (Win, Unix, or Linux)
 - Compute, memory and storage provisioning
 - Hot-hot vs hot-cold configuration
 - Capacity required by proof-of-work mining
 
### Network security
Network security layer implements policies and controls. We need to review the following aspects:
 - access control - who has access to our network
 - antivirus and antimalware software
 - data loss prevention
 - behavioral analytics - to detect abnormal network behavior
 - firewalls
 - intrusion prevention systems
 - network segmentation - especially around wallet module
 
### Private keys security
We need to study Ethereum keystore file and integration with a HSM (hardware security module) solution. So far only found two potential solutions:
 - Accenture (software plugin) and Thales (HSM provider)
 - Vault by HashiCorp

## Appendix - Development Tools
Truffle - a development environment, testing framework and asset pipeline for Ethereum
MetaMask - an Ethereum Browser


