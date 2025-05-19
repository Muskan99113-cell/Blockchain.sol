# Write a contract that manages a list of student records (name, roll number). Allow adding and retrieving student data.
# *Solidity Smart Contract*
### *->Adds student records (name and roll number)*

### *->Retrieves student data*

*A blockchain-based contact manager for students uses a decentralized ledger to securely store and manage student records. This includes adding, retrieving, and deploying student data while ensuring data integrity and privacy.*

![image](https://github.com/user-attachments/assets/b595662b-5b58-4f8a-aea1-5cf8ce892e87)

# Step 1: Open Remix IDE

https://remix.ethereum.org

# Step 2: Create a New File

![WhatsApp Image 2025-05-19 at 15 11 39](https://github.com/user-attachments/assets/c2c21aa5-3c0e-447f-a0c5-2bc06a68c99a)


StudentRecords.sol

![WhatsApp Image 2025-05-19 at 15 12 15](https://github.com/user-attachments/assets/64b923d9-75aa-4fc7-8dfe-a53bed67e8e2)


# Step 3: Execute the code

// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

contract StudentRecords {
    struct Student {
        string name;
        uint rollNumber;
    }

    Student[] public students;

    function addStudent(string memory _name, uint _rollNumber) public {
        students.push(Student(_name, _rollNumber));
    }

    function getStudent(uint index) public view returns (string memory, uint) {
        require(index < students.length, "Invalid index");
        Student memory s = students[index];
        return (s.name, s.rollNumber);
    }

    function getStudentCount() public view returns (uint) {
        return students.length;
    }
}

![WhatsApp Image 2025-05-19 at 15 13 33](https://github.com/user-attachments/assets/f7cf52c5-c04e-46d2-bd01-7a9b1c5d94f8)

# Step 4: Compile the Contract

![WhatsApp Image 2025-05-19 at 15 14 05](https://github.com/user-attachments/assets/b45dc6c5-37f1-4e07-ac7f-5ba6e3825a96)


# Step 5: Deploy the Contract

![WhatsApp Image 2025-05-19 at 15 21 18](https://github.com/user-attachments/assets/bbdf6a8d-a431-4430-9dd8-6410dfe08ed7)


# Step 6: Interact with the Contract

![image](https://github.com/user-attachments/assets/034b5a30-9918-441c-b62a-cc599cdda63e)












