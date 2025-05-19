# Write a contract where people can donate Ether and the top 3 donors are tracked.

 ### *Step 1: Open https://remix.ethereum.org*

 ### *Step 2: Create a New File TopDonors.sol*
 
 ![image](https://github.com/user-attachments/assets/d17b38ec-2e80-4201-8451-f280addbfa51)
 ![image](https://github.com/user-attachments/assets/5affe17e-44a3-4373-b4c4-bc23c671563b)

 ### *Step 3: Execute the code*

// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;
contract TopDonors {
    struct Donor {
        address addr;
        uint amount;
    }

    mapping(address => uint) public donations;
    Donor[3] public topDonors;

    // Donate Ether to the contract
    function donate() public payable {
        require(msg.value > 0, "Must send some ether");

        donations[msg.sender] += msg.value;

        updateTopDonors(msg.sender, donations[msg.sender]);
    }

    // Internal function to update the top 3 donors
    function updateTopDonors(address donor, uint totalDonation) internal {
        // Check if donor is already in top 3
        for (uint i = 0; i < 3; i++) {
            if (topDonors[i].addr == donor) {
                topDonors[i].amount = totalDonation;
                sortTopDonors();
                return;
            }
        }

        // Check if this donation qualifies for top 3
        for (uint i = 0; i < 3; i++) {
            if (totalDonation > topDonors[i].amount) {
                topDonors[2] = Donor(donor, totalDonation);
                sortTopDonors();
                return;
            }
        }
    }

    // Sort top donors in descending order
    function sortTopDonors() internal {
        for (uint i = 0; i < 3; i++) {
            for (uint j = i + 1; j < 3; j++) {
                if (topDonors[j].amount > topDonors[i].amount) {
                    Donor memory temp = topDonors[i];
                    topDonors[i] = topDonors[j];
                    topDonors[j] = temp;
                }
            }
        }
    }

    // View function to get a top donor's address and amount
    function getTopDonor(uint index) public view returns (address, uint) {
        require(index < 3, "Index must be 0, 1 or 2");
        return (topDonors[index].addr, topDonors[index].amount);
    }

    // Function to get total donations by a donor
    function getMyDonations() public view returns (uint) {
        return donations[msg.sender];
    }
}

![image](https://github.com/user-attachments/assets/9c4509ca-69c5-41a6-abfc-cb4d26a2cc2b)
![image](https://github.com/user-attachments/assets/b35676d0-b49e-4dec-bf42-8781a97c0dd5)
![image](https://github.com/user-attachments/assets/7e4c15b8-9250-4b32-9ef7-68da5406382f)

### *Step 4: Compile the Contract*

![image](https://github.com/user-attachments/assets/327fdc22-af59-43b2-9132-b651e4623ad0)


### *Step 5: Deploy the Contract*

->Go to Deploy & Run tab:

->Environment: Remix VM (London)

->Click Deploy
![image](https://github.com/user-attachments/assets/11cd8b9e-920b-48ef-a178-ae0dc61a5194)

### *Step 6: Donate Ether*

To test:

->Enter some Ether (e.g., 1 in "Value")

->Call the donate() function

![image](https://github.com/user-attachments/assets/c271a36e-9b6a-4d55-96f3-82b3b4bed398)

### *Step : View Top Donors*
Call:

getTopDonor(0)

getTopDonor(1)

getTopDonor(2)

![image](https://github.com/user-attachments/assets/42acf9e5-751b-4ca8-9e88-95696fc16cd3)








