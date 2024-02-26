// SPDX-License-Identifier: MIT
pragma solidity ^0.8.18;

contract ErrorHandling {
    function ValidateInput(uint256 _num1, uint256 _num2, uint256 _result) public pure {
        _result = _num1 - _num2;
        require(_result > 5, "First number should be greater than the second");
    }

    uint256 public total;

    function CheckSum(uint256 num1, uint256 num2) public {
        total = num1 + num2;
        if (total < 15) {
            revert("Input must be higher so that the sum is greater than 15");
        }
    }

    uint256 divisor;
    uint256 dividend;

    function CalculateQuotient(uint256 quotient) public view returns (uint256) {
        assert(divisor > 0);
        quotient = dividend / divisor;
        return quotient;
    }
}
