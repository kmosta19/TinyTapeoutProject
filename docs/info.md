## How it works

This project is a hardware implementation of the **Tiny Encryption Algorithm (TEA)**.
It encrypts a single **64-bit block** (two 32-bit words) using a **128-bit key** (four 32-bit words) over **32 cycles**.
Each cycle updates a running sum with the constant **delta = 0x9E3779B9** and mixes the words using only 32-bit
add (mod 2^32), XOR, and shifts.

## How to test

You can test in simulation (Wokwi) or on a Tiny Tapeout demo board.

1. Reset the design.
2. Provide a 128-bit key and a 64-bit plaintext block using the project’s I/O protocol (see pin labels / IO table).
3. Start encryption and wait until the design finishes (or run for the documented number of cycles if there is no DONE flag).
4. Read the 64-bit ciphertext and compare with a reference.

Reference test vector (TEA):
- key       = 0x00000000_00000000_00000000_00000000
- plaintext = 0x00000000_00000000
- ciphertext= 0x41EA3A0A_94BAA940

## External hardware

None required.
(Optional: a Tiny Tapeout demo board + USB cable and a WebUSB-capable browser for the Commander interface.)
