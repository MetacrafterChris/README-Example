# Create a token-ETH proof Beginner 

The challenge involves creating a token, and I'll be going over the specific requirements, such as the necessary public variables, mapping of addresses to balances, and the mint and burn functions.

## Description

Requirements:
1. Your contract will have public variables that store the details about your coin (Token Name, Token Abbrv., Total Supply)
2. Your contract will have a mapping of addresses to balances (address => uint)
3. You will have a mint function that takes two parameters: an address and a value. The function then increases the total supply by that number and increases the balance of the address by that amount.
4. Your contract will have a burn function, which works the opposite of the mint function, as it will destroy tokens. It will take an address and value just like the mint functions. It will then deduct the value from the total supply and from the balance of the address.
5. Lastly, your burn function should have conditionals to make sure the balance of account is greater than or equal to the amount that is supposed to be burned.

## Getting Started

### Installing

The code will be under Creating a token in the JS Beginner repository on my github.

### Executing program

To run the code, we use the Remix IDE. After compilation of the code, we can deploy the code by entering the Name, Abbreviation and Supply of the token we need to create and click deploy. Under the deployed contracts window, we can view out contract with the name Challenge. The contract will display the burn function, mint function, ta variable, tn variable and ts variable. Calling the ta, tn and ts variables we can view the entered name, abbreviation and supply of the token we entered while deploying the contract. Furthermore, we can either mint by entering the address and a value or burn by entering an address and a value. The updated transaction can be viewed by calling the ts variable to check the final balance.

// SPDX-License-Identifier: MIT
pragma solidity >=0.8.9;

contract challenge{
        string public tn;
        string public ta;
        uint public ts;

        mapping (address=>uint) balances;

        constructor(string memory name, string memory abbreviation, uint supply){
            tn=name;
            ta=abbreviation;
            ts=supply;
            balances[msg.sender]=supply;
        }

        function mint(address addTemp, uint v) public {
            balances[addTemp] += v;
            ts += v;
        }

        function burn(address addBurn, uint b)public {
            require(balances[addBurn] >= b, "Insufficient balance");
            balances[addBurn] -= b;
            ts -= b;
        }
}

## Help

You need to be careful of the amount that you burn in a transaction. The condition set in the burn function checs for the amount of totl supply the address holds and compares to the amount to be burnt. So if the value of total supply<burn value, the code will show an error.  

## Authors

Contributors names and contact info

Vansh Abbott
vansh.abbott10@gmail.com


## License

This project is licensed under the [NAME HERE] License - see the LICENSE.md file for details
