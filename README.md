# 3DES-Image-Encryption


DES Algorithm Steps
To put it in simple terms, DES takes 64-bit plain text and
turns it into a 64-bit ciphertext. And since we’re talkingabout asymmetric algorithms, the same key is used
when it’s time to decrypt the text.
The algorithm process breaks down into the following
steps:
1. The process begins with the 64-bit plain text block
getting handed over to an initial permutation (IP)
function.
2. The initial permutation (IP) is then performed on
the plain text.
3. Next, the initial permutation (IP) creates two
halves of the permuted block, referred to as Left
Plain Text (LPT) and Right Plain Text (RPT).
4. Each LPT and RPT goes through 16 rounds of the
encryption process.
5. Finally, the LPT and RPT are rejoined, and a Final
Permutation (FP) is performed on the newly
combined block.
6. The result of this process produces the desired
64-bit ciphertext.
The encryption process step (step 4, above) is further
broken down into five stages:
1. Key transformation
2. Expansion permutation
3. S-Box permutation4. P-Box permutation
5. XOR and swap


For decryption, we use the same algorithm, and we
reverse the order of the 16 round keys.
Next, to better understand what is DES, let us learn the
various modes of operation for DES.
DES Modes of Operation
Data encryption experts using DES have five different
modes of operation to choose from.

● Electronic Codebook (ECB). Each 64-bit block is
encrypted and decrypted independently

● Cipher Block Chaining (CBC). Each 64-bit block
depends on the previous one and uses an
Initialization Vector (IV)

● Cipher Feedback (CFB). The preceding ciphertext
becomes the input for the encryption algorithm,
producing pseudorandom output, which in turn is
XORed with plaintext, building the next ciphertext
unit

● Output Feedback (OFB).Much like CFB, except
that the encryption algorithm input is the output
from the preceding DES●

Counter (CTR). Each plaintext block is XORed with
an encrypted counter. The counter is then
incremented for each subsequent block.

We will next improve our understanding of what DES is,
let us look into the DES implementation and testing.

The Data Encryption Standard (DES) is a
symmetric-key block cipher published by the National
Institute of Standards and Technology (NIST).
DES is an implementation of a Feistel Cipher. It uses a
16 round Feistel structure. The block size is 64-bit.
Though, key length is 64-bit, DES has an effective key
length of 56 bits, since 8 of the 64 bits of the key are not
used by the encryption algorithm (function as check bits
only).

Since DES is based on the Feistel Cipher, all that is
required to specify DES is −

● Round function

● Key schedule

● Any additional processing − Initial and final
permutation
Initial and Final Permutation
The initial and final permutations are straight
Permutation boxes (P-boxes) that are inverses of eachother. They have no cryptography significance in DES.
The initial and final permutations are shown as follows −

Round Function
The heart of this cipher is the DES function, f. The DES
function applies a 48-bit key to the rightmost 32 bits to
produce a 32-bit output.● Expansion Permutation Box − Since right input is
32-bit and round key is a 48-bit, we first need to
expand right input to 48 bits. 

Permutation logic is
graphically depicted in the following illustration −

● The graphically depicted permutation logic is
generally described as table in DES specification
illustrated as shown −● XOR (Whitener). − After the expansion permutation,
DES does XOR operation on the expanded right
section and the round key. The round key is used
only in this operation.

● Substitution Boxes. − The S-boxes carry out the
real mixing (confusion). DES uses 8 S-boxes, each
with a 6-bit input and a 4-bit output. Refer the
following illustration −

● The S-box rule is illustrated below −● There are a total of eight S-box tables. The output
of all eight s-boxes is then combined in to 32 bit
section.

● Straight Permutation − The 32 bit output of S-boxes
is then subjected to the straight permutation with
rule shown in the following illustration:
Key GenerationThe round-key generator creates sixteen 48-bit keys out
of a 56-bit cipher key. 
The process of key generation is
depicted in the following illustration −
The logic for Parity drop, shifting, and Compression
P-box is given in the DES description.

DES Analysis
The DES satisfies both the desired properties of block
cipher. These two properties make cipher very strong.

● Avalanche effect − A small change in plaintext
results in the very great change in the ciphertext.

● Completeness − Each bit of ciphertext depends on
many bits of plaintext.
During the last few years, cryptanalysis have found
some weaknesses in DES when key selected are weak
keys. These keys shall be avoided.
DES has proved to be a very well designed block
cipher. There have been no significant cryptanalytic
attacks on DES other than exhaustive key search.
3-KEY Triple DES
As the security weaknesses of DES became more
apparent, 3DES was proposed as a way of extending its
key size without having to build an entirely new
algorithm. Rather than using a single key as in DES,
3DES runs the DES algorithm three times, with three
56-bit keys:

● Key one is used to encrypt the plaintext.

● Key two is used to decrypt the text that had been
encrypted by key one.

● Key three is used to encrypt the text that was
decrypted by key two.Before using 3TDES, user first generate and distribute
a 3TDES key K, which consists of three different DES
keys K1, K2 and K3. This means that the actual 3TDES
key has length 3×56 = 168 bits. The encryption scheme
is illustrated as follows −

The encryption-decryption process is as follows −

● Encrypt the plaintext blocks using single DES with
key K1.

● Now decrypt the output of step 1 using single DES
with key K2.

● Finally, encrypt the output of step 2 using single
DES with key K3.

● The output of step 3 is the ciphertext.● Decryption of a ciphertext is a reverse process.
User first decrypt using K3, then encrypt with K2,
and finally decrypt with K1.

Due to this design of Triple DES as an
encrypt–decrypt–encrypt process, it is possible to use a
3TDES (hardware) implementation for single DES by
setting K1, K2, and K3 to be the same value. This
provides backwards compatibility with DES.
Second variant of Triple DES (2TDES) is identical to
3TDES except that K3is replaced by K1. In other words,
user encrypt plaintext blocks with key K1, then decrypt
with key K2, and finally encrypt with K1 again.
Therefore, 2TDES has a key length of 112 bits.
Triple DES systems are significantly more secure than
single DES, but these are clearly a much slower
process than encryption using single DES.WORKING
Triple-DES encryption uses a triple-length DATA key
comprised of three 8-byte DES keys to encipher 8 bytes
of data using this method:

● Encipher the data using the first key

● Decipher the result using the second key

● Encipher the second result using the third key

The procedure is reversed to decipher data that has
been triple-DES enciphered:

● Decipher the data using the third key

● Encipher the result using the second key

● Decipher the second result using the first keyIMPLEMENTATION:

1. Importing libraries in the system
2. Uploading / Selecting the Image in the System
3. Running the Triple DES (3DES) Algorithm
4. Running the Encryption Process
5. Running the Decryption Process

