
# PGP Email Encryption – Java Console Simulation

A Java console-based application that simulates the **Pretty Good Privacy (PGP)** email encryption workflow using asymmetric cryptography and client-server communication.

Developed as part of a **Data Security** course, this project demonstrates how encrypted and digitally signed messages can be exchanged between a sender and recipient using RSA cryptography and Java Sockets.

> **Note:** This is an educational simulation of a PGP-style workflow, not a complete implementation of the OpenPGP standard.

---

## Features

- Generation of 2048-bit RSA key pairs for the sender and recipient
- Message encryption using the recipient's public key
- Digital signatures generated using the sender's private key
- Signature verification using the sender's public key
- Message decryption using the recipient's private key
- Client-server communication using Java Sockets
- Interactive console interface with detailed logs of cryptographic operations

---

## Technologies Used

- Java
- RSA Asymmetric Cryptography
- Public-Key Encryption
- Digital Signatures
- Java Sockets
- Client-Server Architecture
- Object-Oriented Programming (OOP)

---

## Project Structure

The application is organized into three main components:

### `Service/` – Shared Cryptographic Services

- **KeyManager.java** – Generates RSA key pairs and stores keys in `.key` files.
- **CryptoService.java** – Handles message encryption and decryption.
- **SignatureService.java** – Creates and verifies digital signatures.

### `client/` – Sender Application

- **MainClient.java** – Entry point for starting the client application.
- **PGPClient.java** – Accepts user input, encrypts and signs messages, and sends them to the server. It also waits for incoming responses, decrypts them, and verifies their signatures.

### `server/` – Receiver Application

- **MainServer.java** – Starts the server and listens for incoming connections.
- **PGPServer.java** – Receives encrypted messages from the client and simulates forwarding them to the intended recipient.

---

## How It Works

1. The sender and recipient generate RSA key pairs.
2. The sender writes an email message in the console.
3. The message is encrypted using the recipient's public key.
4. A digital signature is generated using the sender's private key.
5. The encrypted message and signature are transmitted through a socket connection.
6. The recipient decrypts the message using their private key.
7. The digital signature is verified using the sender's public key.

This workflow demonstrates the concepts of **confidentiality, integrity, and sender authentication** through public-key cryptography.

---

## How to Run

### Requirements

- Java Development Kit (JDK)
- IntelliJ IDEA or another Java IDE
- Local networking support for Java Sockets

### Step 1 – Start the Server

Open the project in IntelliJ IDEA.

Locate `MainServer.java` and run the `MainServer` class.

The server will start listening for incoming messages.

### Step 2 – Start the Client

While the server is running, open a second run configuration or console window.

Locate `MainClient.java` and run the `MainClient` class.

Follow the console instructions to enter email addresses and compose an encrypted message.

---

## Example Console Output

### Server

```text
Email server started, waiting for messages...
New encrypted email received from sender@example.com
Email forwarded to receiver@example.com
```

### Client

```text
Welcome to the PGP Email Client!

Enter your email address: sender@example.com
Enter recipient email address: receiver@example.com

Generating PGP key pair...
Done.

[INFO] Sender Private Key:
MIIEvAIBADANB... (Base64 truncated)

[INFO] Sender Public Key:
MIIBIjANBgkqh... (Base64 truncated)

[INFO] Receiver Public Key:
MIIBIjANBgkqh... (Base64 truncated)

Please enter your email content below:
> Hello, this is a test email.

Encrypting and signing the email...

[INFO] Encrypted Message (Base64):
agT0Gdf9AoiUF... (Base64 truncated)

[INFO] Digital Signature (Base64):
GJfdXl2YDc4E... (Base64 truncated)

Email successfully sent to receiver@example.com

Awaiting encrypted messages...
New encrypted email received. Decrypting...

The email from sender@example.com has been successfully decrypted and verified.
```

*The output above is an illustrative example. Base64 values are shortened for readability.*

---

## Security Concepts Demonstrated

### Confidentiality

RSA public-key encryption is used to protect message contents so that the intended recipient can decrypt them using their private key.

### Integrity

Digital signatures allow the recipient to detect unauthorized changes to a signed message.

### Authentication

The recipient can verify that a message was signed using the private key corresponding to the sender's public key.

### Public-Key Cryptography

The project demonstrates the relationship between public and private keys in asymmetric encryption and digital signature workflows.

---

## Educational Purpose

This project was developed to explore practical concepts in:

- Cryptography and data security
- RSA key generation and management
- Email encryption and digital signatures
- Client-server networking
- Secure communication principles
- Java application development

**Security Disclaimer:** This project is intended for educational and demonstration purposes. It is not a production-ready email encryption system and does not implement the complete OpenPGP specification.

Private keys should never be exposed in application logs or shared publicly.

---

## Author

**Dalina Baraliu**

Computer Science student interested in cybersecurity, networking, malware analysis, digital forensics, and software development.

[GitHub Profile](https://github.com/dalina-baraliu)






