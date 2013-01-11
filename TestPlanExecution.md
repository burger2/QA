Tests
Upgrade

Running Windows 7 Ultimate SP1 64-bit

    Note how much disk space is being used by the bitcoin data directory.
    Run the new bitcoind/Bitcoin-Qt binary.
    

5,97 GB (6 420 704 610 byte)


EXPECT (all tests except for FAT32 filesystem):

    blktree/ subdirectory created in bitcoin data directory
    small (less than 1GB) increase in disk space usage
    startup takes longer than ususual (blocks are re-indexed)
    but startup does not take hours (blocks are not re-downloaded)

PASS/FAIL

EXPECT (FAT32 or other filesystem that does not support hardlinks):

    blktree/ subdirectory created in bitcoin data directory
    same experience as a brand-new user: entire blockchain is re-downloaded

PASS/FAIL

Downgrade

    Shut down the new bitcoind/Bitcoin-Qt, wait for it to completely exit
    Run the old version of bitcoind/Bitcoin-Qt

EXPECT:

    Quick startup
    Old version is synchronized to blockchain from where it last exited

PASS/FAIL
