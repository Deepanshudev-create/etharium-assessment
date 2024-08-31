# Creating a Token.

An Ethereum blockchain token smart contract is implemented by the ImprovedToken contract. It provides the essential functions for tracking token holders' balances and minting and burning tokens.

##  Details
Token Name: "Available Tokens" 

Token Abbreviation: "AT."

initially the available tokens is taken as zero, and all variables are public.

## Applications
### Create Tokens
Tokens can be generated and linked to addresses in a smart contract using the mint function. When the mint function is called, new tokens are generated and assigned to specific blockchain addresses (wallets). This process increases the total number of available tokens by adding newly minted tokens to the existing pool.




### Mint Tokens
Tokens can be added to the current token balance once they have been produced.



### Burn Tokens
If required, we can reduce the total amount of tokens accessible by using the burn function. As a result, tokens are taken from certain addresses, reducing their supply.




## Functions used.


### Mint function


function mint (address _address,uint amount) public {

function mint(address to, uint256 amount) public {
        // Increase the total supply
        totalSupply += amount;
        
        // Increase the balance of the recipient
        balances[to] += amount;

}

### Burn function

    function burn(uint256 amount) public {


## Code 


contract SimpleToken {

    // Public variables to store the details about the token
    string public tokenName = "Sample Token";
    string public tokenSymbol = "STK";
    uint256 public totalSupply = 0;

    // Mapping to store balances of addresses
    mapping(address => uint256) public balances;

    // Mint function to create new tokens and assign them to an address
    function mint(address to, uint256 amount) public {
        // Increase the total supply
        totalSupply += amount;
        
        // Increase the balance of the recipient
        balances[to] += amount;
    }

    // Burn function to destroy tokens from the sender's balance
    function burn(uint256 amount) public {
        // Ensure the sender has enough tokens to burn
        require(balances[msg.sender] >= amount, "Insufficient balance to burn");
        
        // Decrease the total supply
        totalSupply -= amount;
        
        // Decrease the balance of the sender
        balances[msg.sender] -= amount;
    }
}

## Where to execute this code?

By working with this code on "https://remix.ethereum.org/," an easy-to-use web platform designed specifically for developing and testing Ethereum smart contracts, we may efficiently compile, deploy, and administer the ImprovedToken contract.

 THANK YOU!
