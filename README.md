# Description of DES
DES takes 64-bit plaintext and converts it to 64-bit ciphertext, similar to decryption. A 56-bit key is used for encryption and decryption.
![image](https://github.com/Illmaxname/DEScipherWithCBC/assets/81902786/d5734494-736a-478c-8c47-e42ab3b3c4f8)<br />
The encryption process consists of two permutations, called initial and final, and 16 Feistel rounds. Each round uses a different generated 48-bit key.<br />
## Initial and final permutations
The input of each permutation receives 64 bits, which are permuted in accordance with the given tables. These permutations are mutually inverse.<br />
![image](https://github.com/Illmaxname/DEScipherWithCBC/assets/81902786/2d6dcda0-1a29-4d34-a23a-70e7987c3400)
## Feistel rounds
DES uses 16 rounds. Each round applies a Feistel cipher<br />
![image](https://github.com/Illmaxname/DEScipherWithCBC/assets/81902786/8168b283-3587-490b-85ac-4760dc8ebe62)<br />
The round takes Li-1 and Ri-1 half-blocks from the previous round (or the initial permutation block) and creates Li and Ri half-blocks to enter the next round.
## DES function
The DES function encrypts the 32 rightmost bits of Ri-1 using a 48-bit key to produce a 32-bit output. This function contains: an XOR operation, an expansion p-box, a group of S-boxes, and a forward block.<br />
![image](https://github.com/Illmaxname/DEScipherWithCBC/assets/81902786/05393e01-aedb-4af4-8ab3-f0a1a38191c5)<br />
The extension p-box is used to extend the 32-bit Ri-1 block to 48 bits to match its size with the size of the round subkey. Block Ri-1 is divided into 8 sections of 4 bits. Each section expands to 6 bits<br />
![image](https://github.com/Illmaxname/DEScipherWithCBC/assets/81902786/3d00291d-97cc-4e25-b9a9-20374a98f88f)<br />
After the expansion, DES uses the XOR operation on the expanded part of the right half block Ri-1 and the round key ki.<br />
After summing with the key bits, a block of 48 bits is divided into 8 consecutive 6-bit vectors b1, b2,…,b8, each of which is replaced by a 4-bit vector b'j using S-boxes.<br />
![image](https://github.com/Illmaxname/DEScipherWithCBC/assets/81902786/7aff399e-73a7-47c3-9e9c-22432cde9022)<br />
1 vector b1 goes to box S1, 2 vector b2 goes to box S2. S-box is a table with 4 rows and 16 columns. To find the vector ciphers in the S-box, you need to:
- Form a binary number from the 1st and last bits of the vector, convert it to the decimal system. This will be line number m;
- Form a binary number from the 2nd, 3rd, 4th and 5th bits of the vector, convert it to the decimal system. This will be the column number l;
- The number in the S-box at the intersection of the m-th row and the l-th column will be the cipher b'j of the vector bj;
- Cipher designation b'j to be converted into binary system. Answer ready
