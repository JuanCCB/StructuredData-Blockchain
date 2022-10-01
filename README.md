# StructuredData-Blockchain
A blockchain structure that allows to storage useful data with the purpose of having a better track of every transaction or record. This blockchain emulates how cryptocurrencies work with particular applications to the data management field.
Prerequisites
python3 should be installed.

## Installing needed python modules:

pip install -r requirements.txt [criptography 2.3.1]

## Running
cd Blockchain-demo/

### Generating asymmetric cryptography to be used in transactions:

![image](https://user-images.githubusercontent.com/107895120/193429547-5f84959c-22a9-4c19-a376-002baff1fffa.png)

generate_encryption_keys() return a dictionnary object with public_key and private_key as keys. Note that the dictionnary values are respectively RSAPublicKey and RSAPrivateKey objects from the cryptography module.

### Making a transaction : person_1 sends something to person_2:

![image](https://user-images.githubusercontent.com/107895120/193429575-60aa5e05-bb45-4ba2-9fe9-ce4c06dbcb08.png)

A transaction must be signed with sign() methods in order to be valid. The is_valid() method can be used to verify wether a transaction object is valid or not.

![image](https://user-images.githubusercontent.com/107895120/193429585-5ba077f4-494d-4b5f-bbad-0f0ad2653564.png)


Now, we will create a block that holds the transaction.

![image](https://user-images.githubusercontent.com/107895120/193429606-56c87f31-7d18-49cd-8573-76ae576ba397.png)


To be a valid block (also to be added to the blockchain), a proof of work is required. mine() method will find a solution to the hash puzzle according to a difficulty level.

![image](https://user-images.githubusercontent.com/107895120/193429625-ec58269c-a433-4a49-92f6-5132697c0689.png)

Creating a Blockchain and adding a block.

![image](https://user-images.githubusercontent.com/107895120/193429640-846aa873-9ae5-43ae-87b4-84cfa6e590e2.png)


show_blocks() can be used to print all blocks in the blockchain.

![image](https://user-images.githubusercontent.com/107895120/193429647-f168ea9b-c7a6-4643-a6fc-7c10610704ec.png)
