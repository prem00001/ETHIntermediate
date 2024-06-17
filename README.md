# Collage Finder 

This Solidity smart contract, `collageFinder`, allows the owner to set and check eligibility for different types of colleges based on marks. 
The contract also includes error handling and validation using `require()`, `assert()`, and `revert()` statements.

## Features

- Set and check eligibility for IIT, NIT, and Private colleges based on marks.
- Check for minimum passing marks.
- Restrict access to the owner using a modifier.
- Use events to log changes in marks.
- Handle errors and validations with `require()`, `assert()`, and `revert()`.

## Contract Overview

### State Variables

- `uint256 public marks`: Stores the marks of a student (initialized to 30).
- `address public owner`: Stores the address of the contract owner.

### Events

- `event marksChanged(uint256 currentMarks)`: Logs the new marks whenever they are updated.

### Modifiers

- `modifier onlyOwner()`: Restricts function access to the contract owner.

### Constructor

- `constructor()`: Sets the deployer of the contract as the owner.

### Functions

1. **checkforIIT(uint256 currentMarks)**
   - Checks if the marks are greater than 90 to be eligible for IIT.
   - Updates the `marks` variable and emits the `marksChanged` event.
   - Restricted to the owner.

2. **checkforNIT(uint256 currentMarks)**
   - Checks if the marks are greater than 80 to be eligible for NIT.
   - Updates the `marks` variable and emits the `marksChanged` event.
   - Restricted to the owner.

3. **checkforPVT(uint256 currentMarks)**
   - Checks if the marks are greater than 60 to be eligible for a private college.
   - Updates the `marks` variable and emits the `marksChanged` event.
   - Restricted to the owner.

4. **checkMinimumPassingMarks()**
   - Uses `assert` to ensure the marks are at least 33.
   - This is a view function and does not modify the state.

5. **checkforAny(uint256 currentMarks)**
   - Reverts if the marks are 45 or less, indicating the student is not eligible for any college.
   - Updates the `marks` variable and emits the `marksChanged` event.
   - Restricted to the owner.
