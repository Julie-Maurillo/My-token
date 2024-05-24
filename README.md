# MyToken

This code are designed to create and manage a simple token on the Ethereum blockchain. This code can do burning, minting, and check balances.

## Description

This is a demonstration of fundamental concepts of token creation and management on the Ethereum blockchain.

## Getting Started

### Executing program

To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the website, create a new file by clicking the "+" icon on the left side of the screen. Save the file with ".sol" (ex. title.sol). Copy and paste the code below into your file

```
// SPDX-License-Identifier: MIT
pragma solidity 0.8.18;


contract MyToken {

    // public variables here
    string public tokenName = "BETLUG";
    string public tokenAbbrv = "BTG";
    uint public totalSupply = 0;

    // mapping variable here
    mapping(address => uint) public balances;

    // mint function
    function mint(address _address, uint _value) public {
        totalSupply += _value;
        balances[_address] += _value;
    }

    // burn function
    function burn(address _address, uint _value) public {
        require(balances[_address] >= _value, "Insufficient balance to burn");
        totalSupply -= _value;
        balances[_address] -= _value;
    }
}
```

To compile the code, go to solidity compiler tab in the left sidebar. Make sure the "Compile" option is set to 0.8.18 (or other compatible version), and then click the "Compile" button the one with a ".sol" text.

After you compile, go to the "Deploy & run transactions" tab below the solidity compiler tab and then click the "Deploy" button. Once the contract is deployed, you can interact with it using the Remix interface. 
Here are the steps to execute the main functions:

### Minting Tokens
1. In the deployed contract section, locate the 'mint' function.
2. Enter the address to which you want to mint tokens and the number of tokens to mint.
3. Click the "transact" button to execute the mint function.

### Burning Tokens
1. In the deployed contract section, locate the burn function.
2. Enter the address from which you want to burn tokens and the number of tokens to burn.
3. Click the "transact" button to execute the burn function.

### Checking Balances
1. In the deployed contract section, locate the balances mapping.
2. Enter the address you want to check the balance for.
3. Click the "call" button to query the balance of the specified address.


## Authors

Contributors names and contact info

Julie Maurillo
[@Maurillo, Julie](https://github.com/Julie-Maurillo)



## License

This project is licensed under the MIT License - see the LICENSE.md file for details
