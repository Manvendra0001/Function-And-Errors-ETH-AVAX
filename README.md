
# Function-And-Errors-ETH-AVAX

## Solidity Error Handling Examples

This Solidity program demonstrates different error handling methods using `require`, `revert`, and `assert` statements. It showcases how to manage errors effectively within smart contracts on the Ethereum blockchain.

## Description

This contract defines several functions that illustrate error handling techniques in Solidity. Each function demonstrates a different method of handling errors to ensure contract security and reliability.

## Getting Started

### Executing program

To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at [Remix IDE](https://remix.ethereum.org/).

1. **Create a New File:**
   - Click on the "+" icon in the left-hand sidebar.
   - Save the file with a .sol extension (e.g., Errors.sol).
   
2. **Copy and Paste the Following Code:**

    ```solidity
   // SPDX-License-Identifier: MIT
    pragma solidity ^0.8.17;

   contract Errors {
    uint public stateVar = 1;

    function requireExample(address _address, uint _amount) public {
        require(_address == msg.sender, "Unauthorized address");
        require(_amount > 100, "Insufficient balance");
        stateVar++;
    }

    function revertExample(address _address) public {
        if (_address != msg.sender) {
            revert("Unauthorized address");
        }
        stateVar++;
    }

    function assertExample(address _address) public {
        assert(_address == msg.sender);
        stateVar++;
      }
     }
   ```
   
4. **Compile the Code:**
   - Click on the "Solidity Compiler" tab in the left-hand sidebar.
   - Make sure the "Compiler" option is set to "0.8.26" (or another compatible version).
   - Click on the "Compile Errors.sol" button.

5. **Deploy and Interact:**
   - Navigate to the "Deploy & Run Transactions" tab.
   - Deploy the contract and interact with it using the provided functions.

## Usage of Error Handling Methods

- **_Require(address _add, uint _amount)**
  - Ensures `_add` matches `msg.sender` for authorization.
  - Checks if `_amount` is greater than 100.
  - Increments `stateVar` upon successful execution.

- **_Revert(address _add)**
  - Checks if `_add` matches `msg.sender`.
  - Uses `revert` to revert the transaction with a custom error message if conditions are not met.
  - Increments `stateVar` upon successful execution.

- **_Assert(address _add)**
  - Checks if `_add` matches `msg.sender`.
  - Uses `assert` to assert that the condition must always be true.
  - Increments `stateVar` upon successful execution.

## Authors

Manvendra Singh

## License

This project is licensed under the MIT License - see the License.md file for details.
