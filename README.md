# Blockchain Application Using Merkle Trees

## Overview
This project demonstrates the working of Merkle trees in blockchain technology to ensure transparency and reliability in food traceability. It utilizes a distributed immutable digital ledger to securely store and verify critical data in supply chain management, particularly in agriculture and food industries.

[![forthebadge](https://forthebadge.com/images/badges/made-with-java.svg)](https://forthebadge.com)
## Key Features
- **Transparency & Reliability**: Tracks and traces the reliability of food using blockchain.
- **Immutable Ledgers**: Ensures data cannot be edited, only recorded and distributed.
- **Merkle Tree Structure**: Uses a hash-based binary tree for efficient data verification.
- **Cryptographic Security**: Uses cryptographic hash functions to prevent tampering.
- **QR Code Integration**: Enables consumers to scan QR codes on product packaging to verify authenticity and traceability.
- **Database Integration**: Stores necessary details of food products in a MySQL database, connected via JDBC.
- **Blockchain-based Validation**: Verifies and secures information through Merkle root generation and blockchain integration.

## Merkle Tree in Blockchain

![image](https://github.com/user-attachments/assets/8a0498ce-7e5b-461d-b65e-57e003792bec)

- A Merkle tree is a hash-based data structure, generalizing a hash list.
- Typically implemented as a binary tree, where:
  - Each leaf node is a hash of a block of data.
  - Each non-leaf node is a hash of its children.
- Used in distributed systems for efficient data verification.
- Built using Merkle–Damgård construction with one-way compression functions.
- Provides strong collision resistance (brute-force attack would require 2²⁵⁶ attempts).

## Implementation Details
![image](https://github.com/user-attachments/assets/72fc5fa9-5dc4-4fb4-8242-ef7c98d0598b)

1. **Data Storage**:
   - A MySQL database stores product details (e.g., eggs, food items).
   - JDBC is used to connect the project with the database.
2. **Merkle Tree Construction**:
 ![image](https://github.com/user-attachments/assets/a3aa1038-214d-4185-92af-bf9562d1f9a6)
   - Built using the database tables as data.
   - Generates a Merkle root value for verification.
4. **Blockchain Integration**:
   - A Single Linked List (SLL) blockchain is generated with the same data fields.
   - The blockchain is connected to the Merkle tree.
5. **Validation Process**:
   - An empty string array is generated based on the number of leaf nodes.
   - Hash values are compared with existing hashes in the table.
6. **QR Code Implementation**:
   - A blockchain-enabled QR code is generated and printed on product packaging.
   - Consumers scan the QR code to access certification details and timestamps.

  # Merkle-Tree-Blockchain

This project implements a blockchain-based system for storing and accessing data securely. Here's an overview of the classes and their functionalities:

## `Merkle_Main`

This class handles the major implementation of the code by calling methods from various classes based on user's choice via a switch case menu.

- **Case 1:** Inserts data into a singly linked list (SLL) with only the table name as the data in the SLL node.
- **Case 2:** Displays all the data stored in the SLL.
- **Case 3:** Generates a secret key for accessing classified data stored in the blockchain. Data is displayed only if the key matches for the respective company.
- **Case 4:** Allows tracing back to the origin of a product by scanning the blockchain-generated QR code.
- **Case 5:** Displays the Merkle root node hash, which is public.

## `MerkleTree`

This class describes the functionality and implementation of a Merkle Tree, a tamper-proof data structure. It creates a Merkle Tree only if the number of child nodes entered by the user is a power of two. Hash values of children and parent nodes are stored in ArrayLists. Parent hash values are calculated based on the position of child nodes in the ArrayLists. The Merkle Tree ensures data integrity by comparing child and parent node hash values with pre-calculated hash values. Access to data is granted if the root node matches the public root node hash.

## `Block`

Represents a block in the blockchain, containing fields such as timestamp, previous hash value, and table name. This block is used to insert data of type Node in the SLL.

## `Connection`

Establishes a connection between the SQL databases and the Java code for data retrieval and storage.

## `GenerateQR`

Generates a blockchain-generated QR code used for tracing back to the origin of a product. Encodes a bit matrix and formats it to a barcode image.

## `HashAlgorithm`

Utilizes the SHA-256 hashing algorithm to generate hash values stored in the Merkle Tree for respective table names in the SLL.

## `Node` and `Node1`

Represent nodes used in different contexts. `Node` is used in the Merkle Tree, while `Node1` represents blocks inserted into the SLL.

## `SLL1`

Creates a singly linked list with table names as data stored in the nodes. Blocks are added to the back of the SLL, establishing connections to SQL databases.

## Use Cases
- **Agriculture & Food Industry**: Prevent counterfeits, ensure authenticity, and track GI-tagged products.
- **Supply Chain & Logistics**: Automate and optimize processes for greater efficiency.
- **Public Safety & Transparency**: Provide consumers with real-time access to verified product information.

## Conclusion
This blockchain-based Merkle tree application is a robust solution for ensuring transparency and reliability in critical industries. By integrating cryptographic security and distributed ledger technology, it provides a scalable and secure method for product authentication and supply chain management.

## How to Use

1. Run `Merkle_Main.java`.
2. Use the switch case menu to perform various operations such as data insertion, display, access control, tracing, and viewing Merkle root hash.

## Dependencies

- Java Development Kit (JDK)
- SQL Database

Feel free to explore and modify the code to fit your specific use case. 
