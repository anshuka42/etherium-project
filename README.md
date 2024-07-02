# Etherium Project(creating a smart contract)
## Description
Here we have created a contract in which first we will defining different variables like tokenname,token abbreviation and token supply . Then we have a mapping from addresses to unsigned integers which is used to store the balance of each address. Then we will create two different functions to mint and burn tokens from the particular account.
## Getting Started
### Executing program
To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.
Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., etherium_project.sol). Copy and paste the following code into the file:


To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.18" (or another compatible version), and then click on the "Compile etherium_project.sol" button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "yourtoken" contract from the dropdown menu, and then click on the "Deploy" button.
Now you can check token balance on the by clicking on the balance(mapping).For adding tokens to your account click on mint and write the number of tokens you want to add or mint.For removing tokens from your account click on burn and write the number of tokens you want to burn.And then you can verify your balance by clicking on balance.

## Authors
Anshuka
github profile link:-https://github.com/anshuka42

## License

This project is licensed under the MIT License - see the LICENSE.md file for details



## Code Explaination
====>Contract Declaration and License
solidity
PART OF CODE
// SPDX-License-Identifier: MIT
pragma solidity 0.8.18;
SPDX License Identifier: // SPDX-License-Identifier: MIT specifies that the code is licensed under the MIT License, which is a permissive free software license.
Pragma Directive: pragma solidity 0.8.18; specifies that the code is written for Solidity version 0.8.18. This ensures that the contract will not compile with versions of the Solidity compiler outside this range.


====>Contract Definition
solidity
PART OF CODE
contract yourToken {
The contract is named yourToken. A contract in Solidity is similar to a class in other programming languages. It encapsulates data and functions that can be executed on the Ethereum blockchain.

====>Public Variables
solidity
PART OF CODE
    // public variables here
    string public tokenName = "alpha";
    string public tokenAbbre = "alp";
    uint public totalSupply = 0;
tokenName: This is a public variable of type string that stores the name of the token, which is "alpha".
tokenAbbre: This is a public variable of type string that stores the abbreviation of the token, which is "alp".
totalSupply: This is a public variable of type uint (unsigned integer) that keeps track of the total supply of the token. It is initialized to 0.
By declaring these variables as public, Solidity automatically creates getter functions for them. This allows other contracts or users to query these values.

====>Mapping for Balances
solidity
PART OF CODE
    // mapping variable here
    mapping(address => uint) public balances;
balances: This is a mapping from addresses to unsigned integers. It is used to store the balance of each address. The key is an Ethereum address, and the value is the number of tokens that address holds. This mapping is also public, so a getter function is automatically created by Solidity.


====>Mint Function
solidity
PART OF CODE
    // mint function
    function mint(address _address, uint _value) public {
        totalSupply += _value;
        balances[_address] += _value;
    }
Function Definition: function mint(address _address, uint _value) public defines a public function named mint.
Parameters:
_address: The address to which the new tokens will be credited.
_value: The number of tokens to be created and added to the total supply and the balance of the specified address.

Function Body:
totalSupply += _value; increases the totalSupply by the _value amount.
balances[_address] += _value; increases the balance of the specified _address by the _value amount.
This function effectively creates new tokens and assigns them to a specific address, thereby increasing the overall token supply.


====>Burn Function
solidity
PART OF CODE
    // burn function
    function burn(address _address, uint _value) public {
        if (balances[_address] >= _value) {
            totalSupply -= _value;
            balances[_address] -= _value;
        }
    }
Function Definition: function burn(address _address, uint _value) public defines a public function named burn.
Parameters:
_address: The address from which the tokens will be deducted.
_value: The number of tokens to be destroyed and removed from the total supply and the balance of the specified address.
Function Body:
if (balances[_address] >= _value) { ... } checks if the balance of the specified _address is greater than or equal to the _value amount.
If the condition is true:
totalSupply -= _value; decreases the totalSupply by the _value amount.
balances[_address] -= _value; decreases the balance of the specified _address by the _value amount.
This function effectively destroys the specified number of tokens from a given address, provided that the address has enough tokens. It reduces both the overall token supply and the balance of the address.

====>

SUMMARY:-
The yourToken contract is a basic implementation of a cryptocurrency token with minting and burning functionality. It includes:

Public variables to store the token name, abbreviation, and total supply.
A mapping to keep track of each address's balance.
A mint function to create new tokens and assign them to an address.
A burn function to destroy tokens from an address, with a check to ensure the address has enough tokens to burn.
This contract provides the fundamental operations needed to manage a simple token on the Ethereum blockchain.
