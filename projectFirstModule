// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

contract collageFinder 
{
    uint256 public marks=30;
    address public owner;

    // Event to modify old marks by current marks
    event marksChanged(uint256 currentMarks);

    // Modifier to restrict access to the owner
    modifier onlyOwner() 
    {
        require(msg.sender == owner, "Caller is not the owner");
        _;
    }

    constructor() 
    {
        // Set the contract deployer as the owner
        owner = msg.sender;
    }

    // Function to check eligiblity for this collage
    function checkforIIT(uint256 currentMarks) external onlyOwner 
    {
        require(currentMarks > 90, "You are not eligible for this.");

        marks = currentMarks;
        emit marksChanged(currentMarks);
    }
    // Function to check eligiblity for this collage
    function checkforNIT(uint256 currentMarks) external onlyOwner 
    {
        require(currentMarks > 80, "You are not eligible for this.");

        marks = currentMarks;
        emit marksChanged(currentMarks);
    }
    // Function to check eligiblity for this collage
    function checkforPVT(uint256 currentMarks) external onlyOwner
    {
        require(currentMarks > 60, "You are not eligible for this.");

        marks = currentMarks;
        emit marksChanged(currentMarks);
    }

    // Function that uses assert statement for getting minimul passing marks.
    function checkMinimumPassingMarks() external view 
    {
        assert(marks >= 33); // This should always be true
    }

    // Function to demonstrate revert statement to check eligiblity for any collage.
    function checkforAny(uint256 currentMarks)  external onlyOwner {
        if (currentMarks <= 45) {
            revert("you are not having minimum marks for any collage.");
        }
        marks = currentMarks;
        emit marksChanged(currentMarks);
    }

}
