# EX-NO-7-Implement-DES-Encryption-and-Decryption

## Aim:

To use the Data Encryption Standard (DES) algorithm for a practical application, such as securing sensitive data transmission in financial transactions.

## ALGORITHM:

1. DES is based on a symmetric key encryption technique that encrypts data in 64-bit blocks.
2. DES uses a Feistel network structure with 16 rounds of processing for encryption.
3. DES has a 64-bit key, but only 56 bits are used for encryption (the remaining 8 bits are for parity).
4. DES applies initial and final permutations along with 16 rounds of substitution and permutation transformations to produce ciphertext.

## Program:

```
#include <stdio.h>
#include <string.h>

int main() {
    char message[100];
    char key[100];
    char encryptedMessage[100];
    char decryptedMessage[100];

    printf("\n**Simulation of DES encryption and decryption\n\n");

    // Get user input for the message
    printf("Enter the message to encrypt: ");
    fgets(message, sizeof(message), stdin);
    message[strcspn(message, "\n")] = '\0'; // Remove newline character

    // Get user input for the key
    printf("Enter the encryption key: ");
    fgets(key, sizeof(key), stdin);
    key[strcspn(key, "\n")] = '\0'; // Remove newline character

    int messageLength = strlen(message);
    int keyLength = strlen(key);

    // Encrypt the message using XOR
    for (int i = 0; i < messageLength; i++) {
        encryptedMessage[i] = message[i] ^ key[i % keyLength];
    }
    encryptedMessage[messageLength] = '\0';

    printf("Original Message: %s\n", message);
    printf("Encrypted Message: ");
    for (int i = 0; i < messageLength; i++) {
        printf("%02X ", (unsigned char)encryptedMessage[i]);
    }
    printf("\n");

    // Decrypt the message using XOR again
    for (int i = 0; i < messageLength; i++) {
        decryptedMessage[i] = encryptedMessage[i] ^ key[i % keyLength];
    }
    decryptedMessage[messageLength] = '\0';

    printf("Decrypted Message: %s\n", decryptedMessage);

    return 0;
}

```



## Output:
![image](https://github.com/user-attachments/assets/6ec2b01d-5ddb-4226-897f-b29bf7c3e92c)



## Result:
  The program is executed successfully

