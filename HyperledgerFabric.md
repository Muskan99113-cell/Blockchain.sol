# HYPERLEDGER FABRIC 

**Hyperledger Fabric is a modular, open-source blockchain framework, part of the Hyperledger project hosted by the Linux Foundation, designed for enterprise use cases, offering a permissioned network and focus on privacy and scalability.**
![image](https://github.com/user-attachments/assets/91fa2ff5-1ef8-4a16-b823-c5909fd48c88)

# 1. Install Go Programming Language

### sudo apt install golang-go ###

![image](https://github.com/user-attachments/assets/186812aa-aedd-429d-b92d-ef72466d0869)

# 2. Check Docker Version

### docker --version ###

![image](https://github.com/user-attachments/assets/dda0ef68-9214-4568-9b2d-a9ca36d8c2a0)

# 3. Check Docker Compose Version

### docker-compose --version ###
![image](https://github.com/user-attachments/assets/3f413d15-4656-4a36-aff3-6502b2dad186)

# 4. List Directory Contents

### ls ###

![image](https://github.com/user-attachments/assets/b7678241-0831-419a-91f3-6ff72b0bac2d)

# 5. Clone the Fabric Samples Repository

### git clone -b main https://github.com/hyperledger/fabric-samples.git ###

![image](https://github.com/user-attachments/assets/10cf23d7-abee-464c-8f46-86c33f08e927)

# 6. Change Directory to fabric-samples

### cd fabric-samples ###

![image](https://github.com/user-attachments/assets/2c947b9a-99cd-49ee-88b1-dd91ff309180)

# 7. Download Fabric Binaries and Docker Images

### curl -sSL https://bit.ly/2ysbOFE | bash -s ###

![image](https://github.com/user-attachments/assets/fd30afdd-cdd4-43f4-a1d0-eaf127dd9e12)
![image](https://github.com/user-attachments/assets/570049b4-a9bf-4c09-8c37-e44ae8ac7305)

# 8. Change Directory to test-network

#### cd test-network ###

![image](https://github.com/user-attachments/assets/091162b3-f76a-429b-aa9a-620ae2fc5a5d)

# 9. Check Network Script Help

### ./network.sh ###

![image](https://github.com/user-attachments/assets/b201a79c-aa9e-4353-86c9-d34defecdb25)
![image](https://github.com/user-attachments/assets/3ac9eb7e-078b-42ea-9eec-a68cef015872)

# 10. Start the Test Network

### ./network.sh up ###

![image](https://github.com/user-attachments/assets/53b0b471-e535-4436-8f5b-a3ce65043c0d)
![image](https://github.com/user-attachments/assets/2f6bdea1-6992-42de-b0a5-430f28c5ac10)

# 11. Create a Channel in the Network

### ./network.sh createChannel ###

![image](https://github.com/user-attachments/assets/0bc3e841-ce5a-4f72-874d-e6ec010048a2)
![image](https://github.com/user-attachments/assets/bb4a1099-f89c-421c-8cb8-d26b47d55c19)
![image](https://github.com/user-attachments/assets/0d6fa312-fb34-40ee-8981-8f36fdb49030)

# 12. Shut Down the Network

### ./network.sh down ###

![image](https://github.com/user-attachments/assets/fdfec789-8c78-4d6a-a771-1ca660ce4824)
