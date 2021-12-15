# CPUs

- CPU grabs data from RAM

## Memory Controller Chip
- CPU has an external data bus
    - Connect to motherboard, which allows other devices to communicate with CPUs
- Electronically, RAM is made up of 8 rows, a byte
- Memory controller chip - used to be a separate chip, but now is a part of CPUs
    - Has a clock built in that grabs a single byte of memory and sends it to CPU
    - Address bus - a direct connection between MCC and CPU to so CPU can tell MCC which byte of memory it needs
        - Each wire added to the address bus can communicate 2 types of data (0 or 1)
        - If an address bus has 16 bits (or 16 wires), it can communicate 2^16 bytes of RAM
        - Today we have 32 bit and 64 bit
            - 64bit CPU can run 32bit software
        - We need to increase the the wires on the MCC as we use more ram: 32bit can only use 4gb of ram
