# Understanding Mass Storage


## Understanding Partitioning
- A new drive can work on a computer right off the bat, but needs to be prepared to work on OS
- If a drive is a house, partitioning is building the rooms so we can put stuff in it
- Common partitions
    - OS partition
    - Swap file partition (Linux)
    - Recovery partition
- The partitions are created by the OS
    - OS comes with tools that allow you to edit partitions
- Mounting - be able to see the partition
- Windows names partitions with a letter followed by a colon `C:`

## MBR Partitioning
- MBR (Master Boot Record) - Oldest type of partitioning
- Defines partitions and tells computer where to find the operating system
- LBA0 - This is where the computer starts reading when booting up
    - This is where MBR is located
- MBR has 5 pieces
    - Boot loader - First code read off of mass storage
    - Partition tables
- MBR has a max size of 2TB per partition
- MBR is limited to 4 partitions
- MBR on Windows
    - Disk management allows you to see drives
- Primary partitions - the 4 partitions MBR allows you to create
- Extended partitions - created to bypass the 4 partition limit
    - Logical partitions - additional partitions created inside the extended partition
- MBR problems
    - 2TB limit
    - 4 partition limit
