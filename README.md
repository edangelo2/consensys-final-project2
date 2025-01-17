# Final Project Functional Description
## Decentralized Audits

A distributed system for auditing things that require human interaction and manual procedures in the process of auditing.

### Main Entities of the system:

#### - Audit Items
Product, Process, Tasks, Activities that require to be audited by the community.
####  - Producers
  The person responsible for producing the audit item
#### - Auditors
  Members of the community with the ability to audit the items submitted by the producers
#### - Community Member
  The general public interested on controlling the items audit processes 

### How does it work

#### 1. Audits are required for Producers
The producers are required to perform an audit to the things they produce in order to comply with the rules of the community. (e.g.: audit the tax statement from a politician, enviromental impact reports, etc.)
A portion of the producing cost is allocated to getting audits done on the processes and things they produce.
#### 2. Auditors are qualified and get paid for their work
The auditors are members of the community qualified to perform audit reports and submitting the results on a given auditable item. 
The auditors get paid for producing auditing reports and informing the results.
#### 3. The Audit Request
The producer submit an Request for Audit to the system indicating the following:
- Audit Item
	- Audit Name/Description  - Description of the audit request for a given Item
	- Audit Item - Elements of the auditable things that will be provided for the audit
	- Audit Fee - Amount that all the auditors will receive for performing the audit 
	- Number of Auditors Required
#### 4. The Auditors apply for auditing items
The auditors will review the current available items submitted for auditing by the producers and will enroll to the ones that they wish to participate performing the audit.
#### 5. The System randomly assigns the auditors  
When the period for assigning the auditors ends and there are enough auditors enrolled the System will randomly select and assign the auditors for performing the audit.
#### 6. The producers submit the auditable assets
The Producers will submit and sign the documents associated to the audit item.
#### 7. The producers deposit the audit fees
The producers will deposit the Audit Fee at the beginning of the audit. The system will lock the funds. 
#### 8. The Auditors submit the audit results 
Auditors will submit and sign the Audit Results to the system.
The Audit Results will contain the documents with evidence of the audit process and an overall outcome: Passed or Failed.
#### 9. The System pays the auditors
The system will distribute the fees evenly between the participants and release the funds to the auditors wallets.
#### 10. Community Members will review the Audit Progress
The community members will be able to review evolution of the process and evidence at anytime in the system.
#### Anonymity 
The auditors and producers information is kept hidden through all the process they don't know each other, any piece of information submitted and revealed to the system must maintain the anonymity of the producers and the auditors.

### Example 1 - Tax Statements

**Auditable Item:** Tax Statement

**Producers:** Politically Expossed Person

**Auditors:** Citizens that can review tax statements

**Audit Results:** Documents with the results of evaluating the tax statement is correct and the observations

**Community Members** People in general

### Example 2 - Puchase Process

**Auditable Item:** Purchase Order

**Producers:** Goverment Entity Purchase Department

**Auditors:** Citizens that can review purchase orders processes

**Audit Results:** Documents with the results of evaluating that the steps of processing the purchase orders was correct

**Community Members** People in general

# Project Technical Details and Sumbmission requirements

## Directory Structure
    .
    ├── contracts				# Smart Contracts source code
    ├── dapp-site				# Dapp site pages and configuration files
    ├── migrations				# Truffle deployment scripts
    ├── test				# Truffle test scripts
    ├── README.md				# Final project description (this file)
    ├── deployed_address.txt		# Addresses of the smart contracts deployed in the public network
    ├── design_pattern_decisions.md		# Description of design patterns
    └── avoiding_common_attacks.md		# Description of security measures  
    
## Running the Tests

### Dependencies 
Bellow are the dependencies that need to be installed before running the tests.
#### Truffle + Ganache
##### - Truffle installation
`sudo npm install -g truffle`
##### - Ganache installation
`sudo npm install -g ganache-cli`
#### Open Zeppeling Contracts
`npm install @openzeppelin/contracts`

### Steps for running the tests

cd into the directory you've just cloned the repo.

The truffe config file is set with this parameters for the development environment:
```
develop: {
      host: "127.0.0.1",     // Localhost (default: none)
      port: 8545,            // Standard Ethereum port (default: none)
     network_id: "1337",       // Any network (default: none)
     }
```

Run the following command:

`truffle test`

<details>
  <summary>Test Results - Click to expand!</summary>

```
Compiling your contracts...
===========================
> Compiling ./contracts/AuditAssignments.sol
> Compiling ./contracts/AuditEnrollments.sol
> Compiling ./contracts/AuditItem.sol
> Compiling ./contracts/AuditResult.sol
> Compiling ./contracts/DAudit.sol
> Compiling ./contracts/IAuditorAssignments.sol
> Compiling ./contracts/IAuditorEnrollments.sol
> Compiling ./contracts/Migrations.sol
> Compiling @openzeppelin/contracts/security/ReentrancyGuard.sol
> Compiling @openzeppelin/contracts/token/ERC721/ERC721.sol
> Compiling @openzeppelin/contracts/token/ERC721/IERC721.sol
> Compiling @openzeppelin/contracts/token/ERC721/IERC721Receiver.sol
> Compiling @openzeppelin/contracts/token/ERC721/extensions/ERC721URIStorage.sol
> Compiling @openzeppelin/contracts/token/ERC721/extensions/IERC721Metadata.sol
> Compiling @openzeppelin/contracts/utils/Address.sol
> Compiling @openzeppelin/contracts/utils/Context.sol
> Compiling @openzeppelin/contracts/utils/Counters.sol
> Compiling @openzeppelin/contracts/utils/Strings.sol
> Compiling @openzeppelin/contracts/utils/introspection/ERC165.sol
> Compiling @openzeppelin/contracts/utils/introspection/IERC165.sol
> Compiling @openzeppelin/contracts/utils/math/SafeMath.sol
> Artifacts written to /var/folders/gw/9kzzf_t16gn1815x05jd1_tm0000gn/T/test--19492-zwfx8Jt4JVZQ
> Compiled successfully using:
   - solc: 0.8.3+commit.8d00100c.Emscripten.clang

export const auditAssignments = "0x345cA3e014Aaf5dcA488057592ee47305D9B3e10"
export const auditEnrollments = "0x8f0483125FCb9aaAEFA9209D8E9d7b9C8B9Fb90F"
export const DAuditaddress = "0x2C2B9C9a4a25e24B174f26114e8926a9f2128FE4"
export const auditItemAddress = "0xFB88dE099e13c3ED21F80a7a1E49f8CAEcF10df6"
export const auditResultAddress = "0xf204a4Ef082f5c04bB89F7D5E6568B796096735a"


  Contract: DAudit
Listing Fee= 
0.002
Listing AuditFee= 
0.01
Pay Fee= 
0.012
    ✓ Should get Listing Fee 
    ✓ Should Mint two Audit Items  (110ms)
    ✓ Should Create Two Audit items with minted NFTs (711ms)
List of pending Audit Items
items:  [
  {
    price: '10000000000000000',
    tokenId: '1',
    seller: '0x627306090abaB3A6e1400e9345bC60c78a8BEf57',
    owner: '0x0000000000000000000000000000000000000000',
    tokenUri: 'https://www.mytokenlocation.com'
  },
  {
    price: '10000000000000000',
    tokenId: '2',
    seller: '0x627306090abaB3A6e1400e9345bC60c78a8BEf57',
    owner: '0x0000000000000000000000000000000000000000',
    tokenUri: 'https://www.mytokenlocation2.com'
  }
]
    ✓ Should retrive pending items (632ms)
List of auditors enrolled for Audit Item 1: 
{
  index: '0',
  auditId: '1',
  auditors: [
    '0xC5fdf4076b8F3A5357c5E395ab970B5B54098Fef',
    '0x821aEa9a577a9b44299B9c15c88cf3087F3b5544',
    '0x0d1d4e623D10F9FBA5Db95830F7d3839406C6AF2'
  ]
}
List of Auditors enrolled for Audit Item 2: 
{
  index: '1',
  auditId: '2',
  auditors: [
    '0xf17f52151EbEF6C7334FAD080c5704D77216b732',
    '0xC5fdf4076b8F3A5357c5E395ab970B5B54098Fef'
  ]
}
    ✓ Should enroll Auditors (736ms)
Auditors assigned for Audit Item 1 
{
  index: '0',
  auditId: '1',
  auditors: [
    '0xC5fdf4076b8F3A5357c5E395ab970B5B54098Fef',
    '0x821aEa9a577a9b44299B9c15c88cf3087F3b5544'
  ]
}
    ✓ Should assign Auditors (1268ms)
    ✓ Should not assign Auditors if it is not the owner (1060ms)

  Contract: DAudit Results
Pay fee: 12000000000000000
{
  index: '0',
  auditId: '1',
  auditors: [
    '0xf17f52151EbEF6C7334FAD080c5704D77216b732',
    '0xC5fdf4076b8F3A5357c5E395ab970B5B54098Fef'
  ]
}
/* Create two Audit Results */
idTokenResult1:  1
idTokenResult2:  2
/* Submit Audit Results - Auditor 1 */
/* Submit Audit Results - Auditor 2 */
Previous Balances:
Account 0x2932b7A2355D6fecc4b5c0B6BD44cC31df247a2e - Balance: 99.987254382
Account 0x2191eF87E392377ec08E7c08Eb105Ef5448eCED5 - Balance: 99.987304188
Account 0xf17f52151EbEF6C7334FAD080c5704D77216b732 - Balance: 99.999124364
Account 0xC5fdf4076b8F3A5357c5E395ab970B5B54098Fef - Balance: 99.99911515
Account 0xeec918d74c746167564401103096D45BbD494B74 - Balance: 0.024
/* Pay auditors with the smart contract owner */
Account 0x2932b7A2355D6fecc4b5c0B6BD44cC31df247a2e - Balance: 99.987254382
Account 0x2191eF87E392377ec08E7c08Eb105Ef5448eCED5 - Balance: 99.987304188
Account 0xf17f52151EbEF6C7334FAD080c5704D77216b732 - Balance: 100.004124364
Account 0xC5fdf4076b8F3A5357c5E395ab970B5B54098Fef - Balance: 100.00411515
Account 0xeec918d74c746167564401103096D45BbD494B74 - Balance: 0.014
Previous Balance Eth 99.950138964
Current Balance Eth 99.94970397
    ✓ Create two Audit Items Results and Pay auditors (2675ms)


  8 passing (9s)

```
</details>

## Smart Contracts Deployments

The smart contracts are deployed in the Ropsten Network in the following addresses:
```
auditAssignments = "0x98E23D71eE4BC11b3eEa5feD1E428A335c0270A8"
auditEnrollments = "0x6b27bFEF338102D0c36CB414bf2B26C7f477041E"
DAuditaddress = "0xfbfEF368f5Ce319935D8F5429C90B380E9F9d041"
auditItemAddress = "0x58485c810ccD54B9994aABD8e5b0c37796bb2BC5"
auditResultAddress = "0x17E440C6c4206A089983bAcBd9cB886A053E0939"
```

## Dapp Site URL
The Dapp is hosted in Netifly in the following URL: https://edangelo2-consensys-project.netlify.app/

## Screen Cast of the Dapp showing its functionality 
Loom link: https://www.loom.com/share/914f7999d1d546f38dbec67f00513afc?sharedAppSource=personal_library 

## Ethereum account to receive the certification as an NFT
0x745E9390F6Fdcc932AB5b41850aB94C87f224974

## Dapp Description and instrucctions to install it and run it locally

The Dapp is a React/Next Web3 application. Although the Dapp is hosted in Netifly as required for the project, if you want to install it and run it locally below are the steps to perform the installation:
### Installing the Dapp

`cd dapp` previous to install the dependencies in the dapp directory

`npm install ` will install the dependencies detailed in the package.json file.

<details>
  <summary>Dependencies for Dapp - Click to expand!</summary>

```
  "dependencies": {
    "axios": "^0.24.0",
    "ethers": "^5.5.1",
    "ipfs-http-client": "^50.1.2",
    "next": "12.0.4",
    "react": "17.0.2",
    "react-dom": "17.0.2",
    "web3modal": "^1.9.4"
  },
  "devDependencies": {
    "autoprefixer": "^10.4.0",
    "eslint": "7.32.0",
    "eslint-config-next": "12.0.4",
    "postcss": "^8.4.4",
    "tailwindcss": "^2.2.19"
  }
```
</details>

### Running the Dapp
#### Ensure that the Smart contracts are up-and-running
Open another terminal window and from the root directory of the repository run
`truffle develop`

Within the console you can run the command
`migrate`
#### Setup the config.js with the addresses of the smart contracts 
`config.js` file must point to the addresses of the smart contract on the network you want the dapp to work.
Should it be localhost then you can obtain these addresses from console when running `truffle migrate`. Just copy and paste the addresses in the file it in the file.
#### Start the Dapp 

From the directory you've installed the dapp run the following command:

`npm run dev` start the Dapp locally (usually http://localhost:3000/)
#### Access the Dapp from the browser
Access the browser URL and ensure you are in the correct network and port in Metamask. (host: "127.0.0.1", port: 8545)

