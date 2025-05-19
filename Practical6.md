# Create a contract that splits incoming Ether between 3 fixed addresses.

 ### *STEP 1: Write the Smart Contract*
 
![image](https://github.com/user-attachments/assets/a63bb0f7-5521-4fbb-a27a-03fdb35dae22)


->Create a file named EtherSplitter.sol in Remix and write this code:

 // SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

contract EtherSplitter {
    address payable public addr1;
    address payable public addr2;
    address payable public addr3;

    constructor(address payable _addr1, address payable _addr2, address payable _addr3) {
        addr1 = _addr1;
        addr2 = _addr2;
        addr3 = _addr3;
    }

    // Function to receive Ether and split it
    receive() external payable {
        uint share = msg.value / 3;
        uint remainder = msg.value - (share * 3);

        addr1.transfer(share);
        addr2.transfer(share);
        addr3.transfer(share + remainder); // send any remainder to last address
    }
}
![image](https://github.com/user-attachments/assets/1e3b13ae-f358-4c67-bd83-b0949ef8d309)

### *STEP 2: Compile the Contract*
![image](https://github.com/user-attachments/assets/eb34eba0-c7f8-4969-adba-1cde7fdd6e20)


->Click on the  "Solidity Compiler" icon in Remix (left panel)

->Select the appropriate compiler version (0.8.x)

->Click "Compile EtherSplitter.sol"

### *STEP 3: Deploy the Contract*

Click thec"Deploy & Run Transactions" tab
![image](https://github.com/user-attachments/assets/933ac5d3-1c8b-49ad-811a-724a11cdeee2)


Set Environment to Remix VM (London)
(or Injected Provider for MetaMask, if you want to deploy on a testnet)

You’ll see three input fields for constructor:

-address _addr1

-address _addr2

-address _addr3

Then click on Deploy...

![image](https://github.com/user-attachments/assets/9557d997-1c39-4557-b9f7-9d423d06c6d8)


### *STEP 4: Send Ether to the Contract*

-Expand the deployed contract in Remix

-At the top-right corner of Remix, choose an account from the dropdown

-Enter an amount of ETH in the Value field (e.g., 3 ether)

-Click the low-level fallback button — this triggers the receive() function

![image](https://github.com/user-attachments/assets/b3e414fa-15f1-4b05-bfc7-6a9a5df7211d)



### *STEP 5: Check the Balances*

Use the account dropdown to select the recipient addresses and view their balances increasing.

![image](https://github.com/user-attachments/assets/9667f6b2-2ae6-4b51-9ed7-26507726f1c6)






