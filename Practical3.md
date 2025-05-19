# Develop a contract that only allows the deployer (owner) to call a specific function (use modifiers).

### *Step 1: Open Remix* ###
Go to: https://remix.ethereum.org

### *Step 2: Create a New File*

Click New File

![WhatsApp Image 2025-05-19 at 16 07 45](https://github.com/user-attachments/assets/013a4841-b0d0-49df-bef5-43e8f648d05c)


Name it: OwnerRestricted.sol

![WhatsApp Image 2025-05-19 at 16 08 29](https://github.com/user-attachments/assets/48d8729b-17c9-427a-9cfe-109b5332e57e)


### *Step 3: Execute the code:*

// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

contract OwnerRestricted {
    address public owner;
    string public secretData;

    // Constructor sets the deployer as the owner
    constructor() {
        owner = msg.sender;
    }

    // Modifier to restrict access to only the owner
    modifier onlyOwner() {
        require(msg.sender == owner, "You are not the owner");
        _;
    }

    // Function that only owner can call
    function changeData(string memory _newData) public onlyOwner {
        secretData = _newData;
    }

    // Anyone can view the data
    function viewData() public view returns (string memory) {
        return secretData;
    }
}  

![WhatsApp Image 2025-05-19 at 16 17 31](https://github.com/user-attachments/assets/90a250bc-a4bd-4c45-96fe-ee02c5c864cd)


### *Step 4: Compile the Contract*

->Go to the Solidity Compiler tab

->Click Compile OwnerRestricted.sol

![WhatsApp Image 2025-05-19 at 16 10 56](https://github.com/user-attachments/assets/c7963fb2-6d5e-40a8-870c-899f766337ee)


### *Step 5: Deploy the Contract*

->Go to Deploy & Run Transactions tab

->Make sure Environment is Remix VM (London)

->Click Deploy

![WhatsApp Image 2025-05-19 at 16 11 41](https://github.com/user-attachments/assets/1dc8d42b-39ae-4b54-8c56-4d8ef2b6edc0)
![WhatsApp Image 2025-05-19 at 16 14 27](https://github.com/user-attachments/assets/9b68ef57-50b2-4a94-b3a9-f75214703b8c)


### *Step 6: Test the Restriction*

➤ Call

➤ Switch account

➤ Call viewData()

![WhatsApp Image 2025-05-19 at 16 15 02](https://github.com/user-attachments/assets/77d5dc86-4300-4f52-bb2c-7d6dc1084572)



