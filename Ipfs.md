 # **What is IPFS?**

 ![image](https://github.com/user-attachments/assets/08e9d9cf-9f8a-49da-85d2-c3289ffb61eb)

**IPFS (InterPlanetary File System) is a peer-to-peer distributed file storage system. It allows users to store and share files in a decentralized way, using content-based addressing instead of location-based URLs.**

**Key Features:**

**->Files are identified by cryptographic hashes.**

**->Supports versioning and offline-first design.**

**->Efficient bandwidth usage via deduplication.**

**->Nodes store and cache files they access.**

# Step by Step implementation of Commands.....

1.	Install the IPFS through WSL:``` wget https://dist.ipfs.tech/kubo/v0.32.1/kubo_v0.32.1_linux- 
            amd64.tar.gz```

2.	```tar -xvzf kubo_v0.32.1_linux-amd64.tar.gz```
	
3.	Kubo is a reference implementation of IPFS in Go:``` cd kubo```
  
4.	```ls```
   
5.	```sudo bash install.sh```
	
6.	```ipfs –version```
	
7.	```ipfs init```


![image](https://github.com/user-attachments/assets/de6ea7cd-8ef6-4a29-b4e2-eeaf19aef8a4)

8.	```ipfs daemon```

![image](https://github.com/user-attachments/assets/6a10cf52-23bf-4e2d-a928-63a3b2903934)

9.	```On Browser: http://127.0.0.1:5001/webui```
    
![image](https://github.com/user-attachments/assets/4b2f5b7d-97f4-40b9-aca5-c49eda849ec2)

10.	```To run ipfs daemon in background: ipfs daemon > ipfs.log 2>&1 &```
	
11.	```This is daemon ID: [1] 772```
	
12.	```Add file: echo "Hello, IPFS!" > hello.txt```
	
13.	```ipfs add hello.txt```

![image](https://github.com/user-attachments/assets/351e47a6-f4dc-4e7f-960d-87c010f29de7)

14.``` ipfs cat <CID>```

15.	Add a directory: ```mkdir myfolder```
    
```echo "File 1 content" > myfolder/file1.txt```

```echo "File 2 content" > myfolder/file2.txt```

16.	```ipfs add -r myfolder```
	
17.	```ps aux | grep ipfs```
	
18.	```kill <PID>```

![image](https://github.com/user-attachments/assets/748f809b-d78d-4394-aa64-95014a40c5d4)

![image](https://github.com/user-attachments/assets/60833717-edf5-4c71-9494-3b8e54123ca5)

19.	```In Browser you can directly run this to see the IPFS: https://ipfs.io/ipfs/QmWd9cavD8UGZQcqYBVhZqs2Jure5W9cgxR7S6TC4StfZe```

![image](https://github.com/user-attachments/assets/7e9f5d08-d9b5-4c77-bcfc-57cb16ddb372)

# Privacy and encryption on IPFS through command line..

1.	```echo "Hello, IPFS!" > myfile.txt```
	
2.	```ipfs add myfile.txt
	openssl enc -aes-256-cbc -pbkdf2 -iter 100000 -salt -in myfile.txt -out myfile_encrypted.txt -pass pass:yourpassword```
	
3.	```ipfs add myfile_encrypted.txt```
	
4.	```cat myfile_encrypted.txt```
	
5.	```openssl enc -d -aes-256-cbc -pbkdf2 -iter 100000 -in myfile_encrypted.txt -out decrypted_file.txt -pass pass:yourpassword```
	
6.	```cat decrypted_file.txt```
	
7.	```ipfs add decrypted_file.txt```

![image](https://github.com/user-attachments/assets/2193dfec-be9f-47fd-91ec-99f266cdf1e6)
