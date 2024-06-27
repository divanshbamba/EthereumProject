# Project Title

MyToken is a basic ERC-20 like token implemented in Solidity. This contract allows minting and burning of tokens, keeping track of the total supply and individual balances.

## Description

MyToken is a straightforward implementation of an ERC-20 like token using Solidity. It features public variables for token details such as name, abbreviation, and total supply. The contract maintains a mapping of addresses to their respective token balances. It includes a mint function to create new tokens, increasing both the total supply and the balance of a specified address. Additionally, it provides a burn function to destroy tokens, decreasing both the total supply and the balance of a specified address, with necessary checks to ensure the address has sufficient balance to burn.

## Getting Started
## Executing Program
To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.
Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., HelloWorld7.sol). Copy and paste the following code into the file:


    // SPDX-License-Identifier: MIT
    pragma solidity 0.8.18;
    contract MyToken {
    // Public variables to store token details
    string public tokenName = "Canada";
    string public tokenAbbrv = "Australia";
    uint public totalSupply = 0;

    // Mapping to store balances
    mapping(address => uint) public balances;

    // Mint function to create new tokens
    function mint(address _address, uint _value) public {
        totalSupply += _value;
        balances[_address] += _value;
    }

    // Burn function to destroy tokens
    function burn(address _address, uint _value) public {
        if (balances[_address] >= _value) {
            totalSupply -= _value;
            balances[_address] -= _value;
        }
    }
    }

To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.18" (or another compatible version), and then click on the "Compile HelloWorld7.sol" button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. 

Once the contract is deployed we will now mint the token and also burn the token and we will also check condition that we are not able to burn more tokens than we have.

## Authors
DivanshBamba


## License
This project is licensed under the MIT License - see the LICENSE.md file for details
