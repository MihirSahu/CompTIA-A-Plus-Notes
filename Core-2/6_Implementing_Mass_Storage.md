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

## GPT Partitioning
- GPT (GUID Partition Table) - Replaced MBR
- GPT takes adventage of uefi bios
- GUID (global unique identifier) - a 128bit unique value that defines your partioning system take makes your partition unique worldwide
- Advantages over MBR
    - Up to 128 partitions
    - No primary, logical, or extended partitions; just partitions
    - Each partition can have 18.8 milltion TB
    - Is backwards compatible with MBR
        - Protective MBR
- Windows uses GPT
- LBA 1 is the primary GPT header and stores information needed for the partitions
- Secondary GPT header - a copy of the primary GPT header
    - If something happens to the primary header, the secondary can take over
- If you have an MBR drive, you can convert it to GPT

## Understanding File Systems
- Formatting is like creating shelves so we can organize out files and folders
- If you want to use a drive, you partition it and then format it
- File allocation table - keeps track of where all files and folders are located
- Drives can have bad spots, and formatting queries each spot to make sure it can read and write data
- Fragmentation - occurs when files are deleted and overwritten

## Popular File Systems
- FAT32
    - Supported 8 TiB volumes
    - Each file could be 4gb
- NTFS
    - New Technology File Systems
    - Up to 16 EiB volume size
    - Indivitual files can be 256TiB
    - MFT (Master file table)
    - Supports compression, encryption
    - De Facto standard for security
    - Has many features, but is very big
    - Supported by many other OS
- ExFAT
    - Halfway between FAT32 and NTFS
    - Gets rid of unnecessary features from NTFS
- CDFS (Compact disk file system)
    - Used for optical discs, like bluray and dvd
    - Standard for all optical media
- ext3
    - 32Tib volumes
    - 2gb files
- ext4
    - 2EiB volumes
    - 16TiB files
- HFS+ (Hierarchical file system plus)
    - De facto file system for MacOS
    - 8 EiB volumes
    - 8 EiB files

## Dynamic Disks
- Microsoft created their own partitioning scheme, unique to windows
- Can shrink/expand
- By default drives are basic, to convert them to dynamic go to partition manager > right click > Convert to Dynamic Disk
- Stripe, Span, Mirroring
- Microsoft recommendations
    1. Keep boot drive basic
    2. Use GTP to boot drive
    3. Easy to convert from basic to dynamic, but dynamic to basic will delete al data

## Software Raid
- Let OS handle raid for you
- Storage Spaces app in Windows helps manage software raid
- Software raid doesn't have a dedicated raid controller, so it requires the cpu to perform operations

## Encrypting Mass Storage
- Two types
    - File based - encrypts individual files and folders
        - Windows uses Encrypting File System (EFS), and is built in NTFS
        - On windows, right click > Propertiess > Attributes > Advanced
    - Disk based - encrypts entire disk
        - Bitlocker
        - Trusted Platform Module (TPM) - chip attached to motherboard that encrypts drive
            - Must be turned on in bios/uefi
        - Bitlocker to go can encrypt removable media and doesn't require TPM
- Content is decrypted once user is logged in
