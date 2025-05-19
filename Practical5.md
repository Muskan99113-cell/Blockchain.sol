# Implement a simple auction system where users can place bids, and the highest bidder wins.

### *Step 1: Go to https://remix.ethereum.org*

###*Step 2: Create a New File*
![image](https://github.com/user-attachments/assets/d67495dc-c015-4901-bba0-a0590c93f4f9)


File name: SimpleAuction.sol

![image](https://github.com/user-attachments/assets/fca1ec21-249d-4ff8-9eff-1f27502ae12f)


### *Step 3:Execute the code*


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

![image](https://github.com/user-attachments/assets/049d8371-d632-4f80-911d-36d3a3738805)
![image](https://github.com/user-attachments/assets/099adcc1-57f4-4e4b-bc3a-6c25709180c8)
![image](https://github.com/user-attachments/assets/97027a41-de02-4e15-a49d-38297a32ab5d)

### *Step 4: Compile*

->Open the Solidity Compiler tab
![image](https://github.com/user-attachments/assets/9110e313-5e34-4d36-9cee-c24737bee17f)

->Click Compile

![image](https://github.com/user-attachments/assets/40ccb915-762e-4c11-8363-e5d514c92897)


### *Step 5: Deploy*

->Open the Deploy & Run Transactions tab 

->Choose Remix VM (London)

->Click Deploy

![image](https://github.com/user-attachments/assets/cbcb5d9a-cf9a-4a72-90e5-7df6b672e9fb)
![image](https://github.com/user-attachments/assets/5df77705-ff90-41b0-931c-06d7ea4a46b1)



### *Step 6: Test Bidding*

->Select an account from dropdown

->Enter some Ether value 

->Call bid() 

->Change to another account and place a higher bid




### *Step 7: Test Withdrawals*

->Previous highest bidders can call withdraw() to get their funds back

### *Step 8: End the Auction*

->Use the deployer account to call endAuction()

### *Step 8: Declare Winner*

->Call getWinner() → Shows the winning bidder and bid amount

![image](https://github.com/user-attachments/assets/18eb0b0f-91a3-466d-86c8-eeffb33f5382)





