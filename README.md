# AES-implementation
implementation and analysis of AES algorithm

Dependencies -
Numpy - Python's Array Processing Library
Tinkter - Python's GUI Library
Pillow - Python's Image Processing Library

Installing Dependencies -
Install PIP (Python Package Installer) -
sudo apt update
sudo apt install python3-pip
pip3 --version

Numpy -
pip3 install numpy

Pillow -
pip3 install Pillow

Tkinter -
sudo apt-get install python-tk

A typical AES encryption algorithm runs for 10 rounds -each round comprising of 4 processes.The 1st round is shown below -

First Round Process

Byte Substitution (SubBytes)
The 16 input bytes are substituted by looking up a fixed table (S-box) given in design.

Shiftrows
Each of the four rows of the matrix is shifted to the left. Any entries that ‘fall off’ are re-inserted on the right side of row. Shift is carried out as follows −

First row is not shifted.

Second row is shifted one (byte) position to the left.

Third row is shifted two positions to the left.

Fourth row is shifted three positions to the left.

The result is a new matrix consisting of the same 16 bytes but shifted with respect to each other.


MixColumns
Each column of four bytes is now transformed using a special mathematical function. This function takes as input the four bytes of one column and outputs four completely new bytes, which replace the original column. The result is another new matrix consisting of 16 new bytes. We have used the Galois Field Lookup tables for the sake of simplicity.



Addroundkey
The 16 bytes of the matrix are now considered as 128 bits and are XORed to the 128 bits of the round key. If this is the last round then the output is the ciphertext. Otherwise, the resulting 128 bits are interpreted as 16 bytes and we begin another similar round.

Decryption Algorithm -
The process of decryption of an AES ciphertext is similar to the encryption process in the reverse order. Each round consists of the four processes conducted in the reverse order −

Add round key
Mix columns
Shift rows
Byte substitution

How to use :
Encryption -
Run the gui.py script to start the application
Select the encrypt tab
Enter the text you want to encrpyt. You can also select a txt file that contains the text to be encrypted
Enter a 16 character key (make sure to remember this otherwise you wont be able to decrypt later on)
Enter the name of the file you wish to be saved without any extensions
Click encrypt. it will be saved as txt fille in the Encrypted folder

Decryption -
Select the decrypt tab
Enter the name of the encypted file (no need to worry about the relative path,just enter file name without extension)
Enter the 16 character key used for encryption
Click decrypt. it will be saved in the Decrypted folder as a txt file.


