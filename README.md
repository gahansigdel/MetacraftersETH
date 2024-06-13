<h1>MyToken</h1>
"MyToken" is a smart contract that shows the basic functionality of creation, minting and burning token on Ethereum blockchain. The sole aim of this Solidity program is to mark a starting point for beginners in Solidity with interest in the working of token contracts.  

<h1>Description</h1>
This program is a contract coded in Solidity, a language designed for creating smart contracts on the Ethereum blockchain. The contract specifies a token with a name, abbreviation, and total supply. It features functions for minting new tokens and burning existing ones. This program acts as a hands-on introduction to Solidity and can be utilized as a base for developing more sophisticated token projects in the future.

<h1>Requirements</h1>
The contract has public variables to store details about the token (Token Name, Token Abbreviation, Total Supply). The contract includes a mapping of addresses to balances (address => uint). A mint function takes an address and a value, increasing the total supply and the balance of the specified address. A burn function takes an address and a value, decreasing the total supply and the balance of the specified address, with conditions to ensure sufficient balance.

<h1>Code</h1>

``````
// SPDX-License-Identifier: MIT pragma solidity 0.8.18;

/* REQUIREMENTS</br>
1. Your contract will have public variables that store the details about your coin (Token Name, Token Abbrv., Total Supply)
2. Your contract will have a mapping of addresses to balances (address => uint)
3. You will have a mint function that takes two parameters: an address and a value. The function then increases the total supply by that number and increases the balance of the “sender” address by that amount.
4. Your contract will have a burn function, which works the opposite of the mint function, as it will destroy tokens. It will take an address and value just like the mint function. It will then deduct the value from the total supply and from the balance of the “sender”.
5. Lastly, your burn function should have conditionals to make sure the balance of "sender" is greater than or equal to the amount that is supposed to be burned. */

contract MyToken {

// Public variables here
string public tokenName = "META";
string public tokenAbbrv = "MTA";
uint public totalSupply = 0;

// Mapping variable here
mapping(address => uint) public balances;

// Mint function
function mint(address _address, uint _value) public {
    totalSupply += _value;
    balances[_address] += _value;
}

// Burn function
function burn(address _address, uint _value) public {
    if(balances[_address] >= _value) {
        totalSupply -= _value;
        balances[_address] -= _value;
    }
}
}
``````

<h1>Getting Started</h1>

Executing the Program:

To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/. Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., MyToken.sol).

To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.18" (or another compatible version), and then click on the "Compile MyToken.sol" button.

Once the program is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "MyToken" contract from the dropdown menu, and then click on the "Deploy" button.

Once the contract is deployed, you can interact with it by calling the mint and burn functions. To mint or burn tokens, provide an address and a value to the respective functions. 

<h1>Author</h1>
Gahan@crafter


<h1>License</h1>
This project is licensed under the MIT License - see the LICENSE file for details.

Feel free to customize this README file according to your preferences or additional details about your project.
