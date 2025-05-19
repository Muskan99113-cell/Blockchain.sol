# Create a voting system with multiple candidates. Each address can vote only once.

# *Blockchain Voting System*

A simple voting system smart contract written in Solidity. Each Ethereum address can vote once for a candidate. Deployed and tested on Remix IDE.

![image](https://github.com/user-attachments/assets/ece07a07-5c9c-4553-9ffb-e4fe54887ba7)

# Step 1:

Open your browser.

Visit https://remix.ethereum.org

# Step 2: Create a New Solidity File

In the File Explorer (left side panel), click the "New File" icon.

![image](https://github.com/user-attachments/assets/5fe0bf15-0ecf-4bec-a08a-999de3342a4a)


Name your file something like:

VotingSystem.sol

![image](https://github.com/user-attachments/assets/acd27732-ddd7-4fc1-82a3-3115f813e63c)


# Step 3:

Execute the code:

// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

contract VotingSystem {
    address public admin;

    struct Candidate {
        string name;
        uint voteCount;
    }

    mapping(address => bool) public hasVoted;
    Candidate[] public candidates;

    constructor(string[] memory candidateNames) {
        admin = msg.sender;
        for (uint i = 0; i < candidateNames.length; i++) {
            candidates.push(Candidate({
                name: candidateNames[i],
                voteCount: 0
            }));
        }
    }

    function vote(uint candidateIndex) public {
        require(!hasVoted[msg.sender], "You have already voted.");
        require(candidateIndex < candidates.length, "Invalid candidate index.");
        hasVoted[msg.sender] = true;
        candidates[candidateIndex].voteCount++;
    }

    function getNumCandidates() public view returns (uint) {
        return candidates.length;
    }

    function getCandidate(uint index) public view returns (string memory name, uint voteCount) {
        require(index < candidates.length, "Invalid candidate index.");
        Candidate storage candidate = candidates[index];
        return (candidate.name, candidate.voteCount);
    }
}

![WhatsApp Image 2025-05-19 at 14 29 16](https://github.com/user-attachments/assets/028ce02e-c1d3-4f7d-9f79-168a20d9419c)
![WhatsApp Image 2025-05-19 at 14 29 37](https://github.com/user-attachments/assets/5eaf7d3d-a419-44b8-9684-f3810aa84d14)


# Step 4: Compile the Contract

![WhatsApp Image 2025-05-19 at 14 32 58](https://github.com/user-attachments/assets/9cc06efc-b27b-4f51-aacd-0e745e074195)


# Step 5: Deploy the Contract

->Click the “Deploy & Run Transactions.

->Set Environment to:

->Remix VM (London) — for testing locally.
 
->In the input box under the Deploy section.

  ["Alice", "Bob", "Charlie"]
  
->Click the Deploy button.

![WhatsApp Image 2025-05-19 at 14 33 26](https://github.com/user-attachments/assets/f8d5dac0-1870-4049-905e-54d6f67cf003)

# Step 6: Interact with the Contract
![WhatsApp Image 2025-05-19 at 14 30 50](https://github.com/user-attachments/assets/056d2c90-c8ab-4b0d-8763-c0666224fcbf)



