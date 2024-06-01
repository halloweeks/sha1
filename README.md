# SHA-1 Implementation in C

This is a simple implementation of the SHA-1 hashing algorithm in pure C language.

## Introduction

The Secure Hash Algorithm 1 (SHA-1) is a cryptographic hash function that produces a 160-bit (20-byte) hash value known as a message digest, typically rendered as a hexadecimal number, 40 digits long. It was designed by the National Security Agency (NSA) and published by the National Institute of Standards and Technology (NIST) as a U.S. Federal Information Processing Standard.

## Features

- Implemented in pure C language.
- Supports hashing of data from memory buffers.
- Follows the SHA-1 specification as outlined in FIPS PUB 180-1.
- Provides both a simple function interface (`SHA1()`) and a `SHA1_CTX` structure for processing multiple chunks of data.

## Usage

### Using the `SHA1()` Function

```c
#include "sha1.h"

int main() {
    unsigned char data[] = "Hello, World!";
    unsigned char hash[SHA1_BLOCK_SIZE];

    SHA1(data, sizeof(data) - 1, hash);

    // Print or use the hash as needed
    return 0;
}
```

### Using the `SHA1_CTX` Structure

```c
#include "sha1.h"

int main() {
    unsigned char data1[] = "Hello, ";
    unsigned char data2[] = "World!";
    unsigned char hash[SHA1_BLOCK_SIZE];
    
    SHA1_CTX ctx;

    SHA1_Init(&ctx);
    SHA1_Update(&ctx, data1, sizeof(data1) - 1);
    SHA1_Update(&ctx, data2, sizeof(data2) - 1);
    SHA1_Final(&ctx, hash);

    // Print or use the hash as needed
    return 0;
}
```

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
