# DegenToken
DegenToken is an ERC20 token written in solidity. it has functionalities like minting, burning, and you can obtain items by playing the gatcha game.

## Token Details
- **Name: Degen**

- **Symbol: DGN**

- **Total Supply: Minted by owner**

## Operations of the Token
**`mint`: The contract owner can mint new tokens.**

**`burn`: Users can burn tokens.**
## Gatcha
- **Users can participate in a gacha game to randomly obtain items: MIR, NC, or MIR4.**
## Requirements to play Gatcha
- **Users balance must have at least 100 tokens.**

- **Users should previously burned tokens.**

- **It cost 100 tokens each gacha attempt.**

## Inventory 
- **User's can see acquired items from the gacha game.**

- **Provides a getInventory() method to view a user's inventory counts for each item type.**

## Dependencies Applied

- OpenZeppelin Contracts v4.9:
  - ERC20.sol
  - Ownable.sol
  - SafeMath.sol

## Installation
- **OpenZeppelin Contracts v4.9 is installed.**

## Usage
- **Open the project in Remix IDE then Compile the project**
- **Click on run and deploy to Interact with the project**
- **Interact with Contract `DegenToken.sol`**:
   1. Mint tokens 
   2. Burn tokens 
   3. Gacha game using `gacha()`.
   4. Check inventory using `getInventory()`. 


## Sample Code

```solidity
  constructor() ERC20("Degen", "DGN") {
    }

    function mint(address to, uint256 amount) public onlyOwner {
        _mint(to, amount);
    }

    function burn(uint256 amount) public {
        _burn(msg.sender, amount);
        burnedTokens[msg.sender] = burnedTokens[msg.sender].add(amount);
    }

    function gacha() public payable {
        require(balanceOf(msg.sender) >= 100, "Insufficient balance to play gacha");
        require(burnedTokens[msg.sender] >= 1, "You must have burned tokens to play gacha");

```


## License



This project is licensed under the MIT License. See the LICENSE file for details.



















