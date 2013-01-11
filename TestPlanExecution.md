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

PASS

First run... log without timestamp as I didn't rename the bitcoin.conf.txt to bitcoin.conf =)
http://dl.dropbox.com/u/82192439/Bitcoin/debug-upgrade-first%20run.7z

Second run with timestamp.


Downgrade

    Shut down the new bitcoind/Bitcoin-Qt, wait for it to completely exit
    Run the old version of bitcoind/Bitcoin-Qt

EXPECT:

    Quick startup
    Old version is synchronized to blockchain from where it last exited

FAIL

I got two error messages:
http://dl.dropbox.com/u/82192439/Bitcoin/debug-downgrade.log

I had to delete all the subdirectories to get the old Bitcoin-Qt client working (the old blk.dat files where still there).
http://dl.dropbox.com/u/82192439/Bitcoin/debug-downgrade-second%20run.log
