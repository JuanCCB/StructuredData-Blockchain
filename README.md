# StructuredData-Blockchain
A blockchain structure that allows to storage useful data with the purpose of having a better track of every transaction or record. This blockchain emulates how cryptocurrencies work with particular applications to the data management field.
Prerequisites
python3 should be installed.

##Installing needed python modules:

pip install -r requirements.txt [criptography 2.3.1]

##Running
cd Blockchain-demo/

Generating asymmetric cryptography to be used in transactions:
from utils.encryption import *
person_1 = generate_encryption_keys()
person_2 = generate_encryption_keys()

generate_encryption_keys() return a dictionnary object with public_key and private_key as keys. Note that the dictionnary values are respectively RSAPublicKey and RSAPrivateKey objects from the cryptography module.

Making a transaction : person_1 sends something to person_2:

from transaction import Transaction
tr_1 = Transaction(sender=person_1["public_key"], receiver=person_2["public_key"], assets="SOMETHING")
tr_1.sign(person_1["private_key"])

A transaction must be signed with sign() methods in order to be valid. The is_valid() method can be used to verify wether a transaction object is valid or not.

tr_1.is_valid()
True

Now, we will create a block that holds the transaction.

from block import Block
bl_1 = Block(tr_1)
To be a valid block (also to be added to the blockchain), a proof of work is required. mine() method will find a solution to the hash puzzle according to a difficulty level.

bl_1.mine()
Creating a Blockchain and adding a block..

from blockchain import Blockchain
blc = Blockchain()
blc.add_block(bl_1)

show_blocks() can be used to print all blocks in the blockchain.

from blockchain import Blockchain
blc.show_blocks()
