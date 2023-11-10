# DegenToken

## Overview

The `DegenToken` is an ERC20-compliant token contract written in Solidity. It extends the OpenZeppelin `ERC20` and `Ownable` contracts, providing basic functionalities for creating, burning, and transferring tokens. Additionally, it includes a game system where users can redeem in-game items using their token balance.

### Functions

#### `constructor()`

- Description: Initializes the contract with a name ("Degen") and symbol ("DGN"). It also inserts three games into the game system: Tekken, PUBG, and CSGO.
- Modifiers:
  - None

#### `mint(address to, uint256 amount)`

- Description: Allows the owner to mint (create) new tokens and assign them to a specific address.
- Parameters:
  - `to` (address): The address to which the new tokens will be assigned.
  - `amount` (uint256): The amount of tokens to mint.
- Modifiers:
  - `onlyOwner`: Ensures that only the owner of the contract can call this function.

#### `burn(uint256 amount)`

- Description: Allows any user to burn (destroy) a specific amount of tokens.
- Parameters:
  - `amount` (uint256): The amount of tokens to burn.
- Modifiers:
  - None

#### `transfer(address to, uint256 amount)`

- Description: Overrides the standard `transfer` function to add flexibility and custom functionality.
- Parameters:
  - `to` (address): The address to which the tokens will be transferred.
  - `amount` (uint256): The amount of tokens to transfer.
- Returns:
  - `success` (bool): Indicating whether the transfer was successful.
- Modifiers:
  - None

#### `insertGame(string memory name, uint256 price)`

- Description: Allows the owner to insert new games into the game system.
- Parameters:
  - `name` (string): The name of the game.
  - `price` (uint256): The price of the game in tokens.
- Modifiers:
  - `onlyOwner`: Ensures that only the owner of the contract can call this function.

#### `getItem(uint256 itemId)`

- Description: Retrieves information about a specific game item.
- Parameters:
  - `itemId` (uint256): The ID of the game item.
- Returns:
  - `itemName` (string): The name of the game item.
  - `itemPrice` (uint256): The price of the game item.
- Modifiers:
  - None

#### `showGames()`

- Description: Retrieves a list of all available games in the system along with their prices.
- Returns:
  - `allGames` (string): A string representation of all available games.
- Modifiers:
  - None

#### `redeemGames(uint256 itemId)`

- Description: Allows users to redeem in-game items using their token balance.
- Parameters:
  - `itemId` (uint256): The ID of the game item to redeem.
- Revert Conditions:
  - Invalid item ID.
  - Insufficient balance for the purchase.
- Modifiers:
  - None

#### `uintToString(uint256 value)`

- Description: Converts a uint256 to its string representation.
- Parameters:
  - `value` (uint256): The uint256 value to convert.
- Returns:
  - `str` (string): The string representation of the uint256.
- Modifiers:
  - None
