# Create a Token

This Solidity program is a simple "Create a Token" program that demonstrates the basic syntax and functionality of the Solidity programming language. The purpose of this program is to serve as a starting point for those who are new to Solidity and want to get a feel for how it works.

## Description

This program is a simple contract written in Solidity, a programming language used for developing smart contracts on the Ethereum blockchain. The contract has a multiple functions which will help in creating token.

## Getting Started

### Executing program

## Getting Started

### Executing program

To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., token.sol). Copy and paste the following code into the file:

// SPDX-License-Identifier: MIT
pragma solidity 0.8.18;
contract MyToken {

    // public variables here
    string public Token_Name ="crpto";
    string public Token_Abb ="CR";
    uint Total_Supply = 0;


    // mapping variable here

    mapping (address => uint) public balance;

    // mint function

    function mint (address _add, uint _value) public {
        Total_Supply += _value;
        balance [_add] += _value;
    }

    // burn function
    
    function burn(address _add, uint _value) public {
        if (balance[_add]>=_value){
        Total_Supply -= _value;
        balance [_add] -= _value;
    }

}
}

contract HelloWorld {
    function sayHello() public pure returns (string memory) {
        return "Hello World!";
    }
}

```

To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.18" (or another compatible version), and then click on the "Compile token.sol" button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "token" contract from the dropdown menu, and then click on the "Deploy" button.

Once the contract is deployed, you can interact with it by calling the public variable with token name= "crpto", token abbr = "CR", and total_supply=0. after that mapping of balance variable with adress will be done. Then copy one adress and Click on the "mint fuction" contract in the left-hand sidebar to add number of token, and then click on the "burn" function to burn the number of token you have burnt on the same adress Finally, click on the "balance" button to the balance available at the smae adress.

## Authors

Metacrafter Chris  
[@metacraftersio](https://twitter.com/metacraftersio)


## License

This project is licensed under the MIT License - see the LICENSE.md file for details
