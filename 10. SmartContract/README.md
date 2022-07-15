## A. Blockchain Basics
  * Book = Blockchain
  * Page = Block
  * Page Entry = Blockchain transaction
  * Let's think of blockchain as a book that can be written to but not erased
  * Blockchains can be **private** or **public**
  * Blockchains are a revolutionary way of implementing "trust" into a platform
  * A blockchain is a **globally shared data structure**, transactional backend database 
    * In Bitcoin it's generally called a **ledger**
    * This means that everyone can read entries in the database just by participating in the network
    * If you want to change something in the databse, you have to create a so-called "**transaction**" 
      * which has to be accepted by all others
  * Blockchain Digital Idendity
    * Combining a **private key** and **public key** creates a strong digital idendity reference based on **possession**
## B. Smart Contract
  * computer program code
  * capable of facilitating, executing and enforcing the negotiation or performance of an agreement
  * using **Blockchain technology**
  * the entire process is automated 
  * can act as a complement, or subtitute, for legal contracts
  * terms of S.C are recorded in a computer langusge as a **set of instructions**
  * define the **rules** and **penalties** around an agreement in the same way that a traditional contract does
  * smart contracts provide :
    * autonomy
    * trust
    * backup
    * safety
    * speed
    * savings
    * accuracy
  * several smart contracts can make up a DApp
  * smart contracts on Ethereum network run on something called **Ethereum Virtual Machine (EVM)**
  * DApps running on the Ethereum network are basically complex smart contracts
## C. DApp
  * decentralized application
  * run on a P2P network of computers, instead of a single computer
  * one or more smart contracts
  * open source
  * data and the records of operation of application to be cryptographically stored on ledger
  * use cryptographic token
## D. Solidity
* object-oriented language
* high-level language 
* for implementing smart contracts
* curly-bracket language
* is influenced by C++, Python and JavaScript
* target the Ethereum Virtual Machine (EVM)
* recently released the 0.8.x version
* typed language
  * the type of each variable (state and local) needs to be specified
## E. Installing the Solidity Compiler
### 1. [Remix](https://remix.ethereum.org/)
  * Advantages
    * for small contracts
    * for quickly learning Solidity
    * do not need to install anything
  * Limitations
    * can not integrate other parts of a project
    * limited support for tests or custom developments
    * can not save files locally without a plugin
    * needs an internet connection
    * doesn't have python
### 2. [npm / Node.js](https://nodejs.org/en/)
#### Linux
```
# First install epel-release
$sudo yum install epel-release

# Now install nodejs
$sudo yum install nodejs

# Next install npm (Nodejs Package Manager )
$sudo yum install npm

# Finally verify installation
$npm --version

# Install Solidity compiler (solcjs program)
$sudo npm install -g solc

# Test your Solidity compiler
$solcjs --version
```
#### Windows 
  * [Download the Windows installer](https://nodejs.org/en/download/)  
  * Run the installer (the **.msi** file you downloaded in the previous step.)
  * Accept the license agreement, click the **NEXT** button a bunch of times and accept the default installation settings.
  * **Restart** your computer. You won’t be able to run Node.js until you restart your computer.
  * Test Node.
```
C:\Users\rahmati>node -v
v13.14.0
```
   * **Test** NPM. To see if NPM is installed, type:
```
C:\Users\rahmati>npm -v
6.14.4
```
   * Create a test file and run it.
```
D:\>node hello.js
Node is installed!

D:\>dir
 Volume in drive D is New Volume
 Volume Serial Number is 4A1D-B8AE

 Directory of D:\

09/11/2021  11:59 AM                34 hello.js

D:\>
```
* Ganache
  * a personal blockchain
  * for rapid **Ethereum** and **Corda** distributed application development
  * can be used across the entire development cycle; 
    * develop 
    * deploy
    * and test dApps
  * comes in two flavors: 
    * UI 
      * [desktop application](https://www.trufflesuite.com/ganache)
      * supporting both Ethereum and Corda
    * CLI
      * command-line tool
       * [ganache-cli](https://github.com/trufflesuite/ganache-cli-archive) 
       * formerly known as the TestRPC
      * is available for Ethereum development 
  * All versions of Ganache are available for **Windows**, **Mac**, and **Linux**.
### 3. [Visual Studio Code](https://code.visualstudio.com/)
  * Extensions
    * Python
    * Solidity 
    * Bracket Pair Colorizer
  * [Download the latest version of python](https://www.python.org/downloads/)



```
PS C:\> cd project
PS C:\project> mkdir web3_py_simple_storage
PS C:\project> cd web3_py_simple_storage
PS C:\project\web3_py_simple_storage> pip install black
PS C:\project\web3_py_simple_storage> pip install py-solc-x
PS C:\project\web3_py_simple_storage> pip install web3
```
## F. Solidity Tutorial
### F0. Pragma
* [LAB : hello_world.sol](https://github.com/yaser-rahmati/smartcontract/blob/79bd9ab4786366d92b47a11e7fda022ea2d015a1/Solidity%20by%20Example/hello_world.sol) 
* It tells that the source code is written for Solidity version 0.4.0 or anything newer that does not break functionality up to, but not including, version 0.6.0.
```
pragma solidity >=0.4.0 <0.6.0;
```
* Such a source file will not compile with a compiler earlier than version 0.4.0 and it will also not work on a compiler starting from version 0.5.0 (this second condition is added by using ^).
```
pragma solidity ^0.4.0;
```
### F1. Comments
* Any text between a // and the end of a line is treated as a comment and is ignored by Solidity Compiler.
```
// This is a comment. It is similar to comments in C++
```
* Any text between the characters /* and */ is treated as a comment. This may span multiple lines.
```
   /*
      - This is a multi-line comment in solidity
      - It is very similar to comments in C Programming
   */
```
### F2. Declaration of Variables
* [LAB : primitive_data_types.sol](https://github.com/yaser-rahmati/smartcontract/blob/cc9055993aa6df5f064cb4033ea620d75c3ad38c/Solidity%20by%20Example/primitive_data_types.sol) 
```
<type> <access modifier> <variable name> ; 
```
### F3. Value Types
#### F3.1. Booleans
* It can be either *true* or *false*
```
bool isPaid = true;
```
#### F3.2. Integer
* There are two main Solidity types of integers of differing sizes:
  * **int** - signed integers.
  * **uint** - unsigned integers.
* Speaking of size, to specify it, you have keywords such as **uint8** up to **uint256**, that is, of **8** to **256** bits.
```
uint public storedData = 10;
int32 public int_var = -60313;
```
#### F3.3. Fixed Point Numbers
* There are two types of fixed point numbers:
  * **fixed** - signed fixed point number.
  * **ufixed** - unsigned fixed point number.
* This value type also can be declared keywords such as **ufixedMxN** and **fixedMxN**.
  * M 
    * the amount of bits that the type takes
    * has to be divisible by 8, and a number from 8 to 256
  * N
    * the number of decimal points
    * has to be a value between 0 and 80
#### F3.4. Address
* **address** holds a 20-byte value (size of an Ethereum address).
```
address nameReg = 0x72ba7d8e73fe8eb666ea66babc8116a41bfb10e2;
```
### F4. {State, Local, Global} Variable
* [LAB : variables.sol](https://github.com/yaser-rahmati/smartcontract/blob/86896b45889cd258089c10fdd531d270d2d615d5/Solidity%20by%20Example/variables.sol)
* There are 3 types of variables in Solidity:
  * **local**
    * declared inside a function
    * not stored on the blockchain
  * **state**
    * declared outside a function
    * stored on the blockchain
  * **global** 
    * provides information about the blockchain
### F5. Operators
Assume variable A holds 10 and variable B holds 20, then:
* *Arithmetic Operators*
  * **Addition**
    * Ex: A + B will give 30
  * **Subtraction**
    * Ex: A - B will give -10
  * **Multiplication**
    * Ex: A * B will give 200
  * **Division**
    * Ex: B / A will give 2
  * **Modulus**
    * Ex: B % A will give 0
  * **Increment**
    * Ex: A++ will give 11
  * **Decrement**
    * Ex: A-- will give 9

* *Logical Operators*
  * **Logical AND**
    * Ex: (A && B) is true
  * **Logical OR**
    * Ex: (A || B) is true
  * **Logical NOT**
    * Ex: ! (A && B) is false

* *Comparison Operators*
  * **Equal**
    * Ex: (A == B) is not true
  * **Not Equal**
    * Ex: (A != B) is true
  * **Greater than**
    * Ex: (A > B) is not true
  * **Less than**
    * Ex: (A < B) is true
  * **Greater than or Equal to**
    * Ex: B % A will give 0
  * **Ex: (A >= B) is not true**
    * Ex: A++ will give 11
  * **Less than or Equal to**
    * Ex: (A <= B) is true
### F6. Array
* Array is a data structure
* Stores a **fixed-size sequential** collection of elements of the **same type**
* Single-dimension array
  * The **arraySize** must be an **integer** constant **greater than zero**
  * **type** can be any valid Solidity data type
```
type arrayName [ arraySize ];
```
* Array of dynamic size
```
type[] arrayName;
```
* Initializing Arrays
  * one by one
  * a single statement
```
// one by one
balance[2] = 5;

// a single statement
uint balance[3] = [1, 2, 3];
```
## G. Create project using truffle
* **Prerequisites**
  * NodeJS
  * Node Package Manager (NPM)
* **Installation**
  * Download the appropriate version for your OS: [https://truffleframework.com/ganache](https://truffleframework.com/ganache)
  * Next, double-click on the downloaded file, follow the prompts, and you're up and running.
  * When you open Ganache for the first time, you'll see the home screen. On this screen, you're prompted to load an existing workspace (if any exist), create a **new custom workspace**, or **quickstart** a one-click blockchain with default options.
 
![alt text](https://yaser-rahmati.gitbook.io/~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-M2g31CUvdCruJm660Ot%2F-MjJJ0dCUV6vu9HEF3AE%2F-MjJJE6wLGucj89hGLZ0%2F894.png?alt=media&token=8f143291-4b07-4ed3-ab16-15430d6c77f2)

  * **Create a project directory**
```
D:\>mkdir project
D:\>cd project
D:\project>
```
  * **Setup to initialize a default truffle project**
```
C:\project>truffle init

Starting init...
================
> Copying project files to C:\project
Init successful, sweet!
Try our scaffold commands to get started:
  $ truffle create contract YourContractName # scaffold a contract
  $ truffle create test YourTestName         # scaffold a test
http://trufflesuite.com/docs
 
D:\project>dir
 Volume in drive D is New Volume
 Volume Serial Number is 4A1D-B8AE
 Directory of D:\project
09/11/2021  02:14 PM    <DIR>          .
09/11/2021  02:14 PM    <DIR>          ..
09/11/2021  02:14 PM    <DIR>          contracts
09/11/2021  02:14 PM    <DIR>          migrations
09/11/2021  02:14 PM    <DIR>          test
10/26/1985  12:45 PM             4,903 truffle-config.js
               1 File(s)          4,903 bytes
               5 Dir(s)  93,537,128,448 bytes free
```
  * **To configure truffle to use our testRPC client, populate truffle.js with:**
```
module.exports = {
  networks: {
    development: {
      host: "127.0.0.1",
      port: 7545,
      network_id: "*" // Match any network id
    }
  }
};
```
  * **Create a contract file inside the contracts folder**
    * [hello_world.sol](https://github.com/yaser-rahmati/smartcontract/blob/76b67019cd629c6e5d020e89b7858611b8855055/Solidity%20by%20Example/hello_world.sol)
```
C:\Project>truffle create contract hello_world
C:\Project\contracts>dir
 
 Directory of C:\Project\contracts

11/21/2021  07:24 PM    <DIR>          .
11/21/2021  07:24 PM    <DIR>          ..
11/21/2021  07:24 PM               120 hello_world.sol
               1 File(s)            120 bytes
               2 Dir(s)  32,364,699,648 bytes free
```
  * **Run the truffle migrations**
    * Run the truffle migrations using **truffle migrate** or **truffle migrate --reset** .
```
D:\project>truffle migrate --reset
Compiling your contracts...
===========================
> Compiling .\contracts\hello_world.sol
> Compiling .\contracts\hello_world.sol
> Artifacts written to D:\project\build\contracts
> Compiled successfully using:
   - solc: 0.5.16+commit.9c3226ce.Emscripten.clang
Starting migrations...
======================
> Network name:    'development'
> Network id:      5777
> Block gas limit: 6721975 (0x6691b7)
1_initial_migration.js
======================
   Deploying 'Migrations'
   ----------------------
   > transaction hash:    0x2334b1d6da3b00a5a99d0618166037265074822f97321377fca5e04498a
   > Blocks: 0            Seconds: 0
   > contract address:    0x8a9dc11E35604ed9F35ffDeDe7722B4430b7231e
   > block number:        1
   > block timestamp:     1631368671
   > account:             0x6137ccc6D83fb0118ED7c39De9AF3275F1e535A6
   > balance:             99.99616114
   > gas used:            191943 (0x2edc7)
   > gas price:           20 gwei
   > value sent:          0 ETH
   > total cost:          0.00383886 ETH
   > Saving migration to chain.
   > Saving artifacts
   -------------------------------------
   > Total cost:          0.00383886 ETH
Summary
=======
> Total deployments:   1
> Final cost:          0.00383886 ETH
D:\project>
```
  * This will read the **truffle-config.js** file and compile the contracts present in the contracts folder create json files in the build folder. For completing this process it uses some **gas** from account 1 of ganache.
![alt text](https://yaser-rahmati.gitbook.io/~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-M2g31CUvdCruJm660Ot%2F-MjKB3MMByFaqGUoMg01%2F-MjKB90gUNONaVseqhFm%2F895.jpg?alt=media&token=b4e6bef5-86de-4e72-9176-4fef22c366f0)

## Vulnerability
### Vul 01 : Arithmetic
```
pragma solidity ^0.8.7;
contract TokenSM{
    mapping(address=>uint) balances;
    uint public totalSupply;
    function Token(uint _initialSupply) public{
        balances[msg.sender]=totalSupply=_initialSupply;
    }
    function transfer(address _to, uint _value) public returns(bool){
        require(balances[msg.sender] - _value >=0);
        balances[msg.sender] -= _value;
        balances[_to] += _value;
        return true;
    }
}
```
* As a common high-risk vulnerability, arithmetic referred to **integer overflow** and **integer underflow**, which caused the BEC attack with a huge loss.
* Line 9 of this attack scenario requires that the Token of their caller must be greater than the value that he wants to transfer to others.
* Suppose that **balances[msg.sender]=0** and **_value=1**, we can get that **balances[msg.sender] < _valu**e. But in fact **balances[msg.sender] − _valuevalue = 1**. We can bypass the rules of Line 9 easily.
## Conclusion. Dependencies on Smart Contract Vulnerabilities
### 1. Blockchain Vulnerabilities
1. Immutability
2. Transparency
3. Sequencial Execution
4. Complexity
5. Transaction cost
6. Human Errors
### 2. Software Security Issues
1. Buffer overflows
2. Command Injection
3. Cross-site scripting
4. Format string problems
5. Integer range errors
6. SQL injection
7. Trusting network address information
8. Failing to protect network traffic
9. Failing to store and protect data
10. Failing to use cryptographically strong random numbers
11. Improper file access
12. Improper use of SQL
13. Use of weak password-based systems
14. Unauthenticated key exchange
15. Signal race conditions
16. Use of ?magic?URLs and hidden forms
17. Failure to handle errors
18. Poor usability
19. Information leakage
### 3. Ethereum and Solidity Vulnerabilities
1. Re-entrancy problem
2. Transaction ordering
3. Block timestamp dependency
4. Exception handling
5. Call stack depth limitation
6. Integer overflow/underflow
7. Unchecked and Failed send
8. Destroyable / Suicidal contract
9. Unsecurred balance
10. Use of origin
11. No restricted write
12. No restricted transfer
13. Non-validated arguments
14. Greedy contracts
15. Prodegal contracts
16. Gas costly patterns exist
### 4. Security Analysis Tools
1. Oyente
2. ZEUS
3. Vandal
4. Ethir
5. Securify
6. MAIAN
7. GASPER
8. F* framework
9. Isabelle/HOL
10. FEther using Coq
11. KEVM framework

