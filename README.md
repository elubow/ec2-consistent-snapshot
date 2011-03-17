## ec2-consistenet-snapshot

   This is a fork of the original ec2-consistent-snapshot written by Eric Hammond.

   The difference is that this version has support for MongoDB.

### Usage

   Below is an example command for snapshotting Mongo.  It will lock and fsync the DB, take the snapshot, and then unlock it.  You can add a _--stop_ to have Mongo restart afterwards.


    ec2-consistent-snapshot                                    \
    --mongo                                                    \
    --xfs-filesystem /data                                     \
    --region us-east-1                                         \
    --description "RAID snapshot $(date +'%Y-%m-%d %H:%M:%S')" \
    vol-VOL1 vol-VOL2 vol-VOL3 vol-VOL4 vol-VOL5 vol-VOL6 vol-VOL7 vol-VOL8

#### Author

   Originally by Eric Hammond.

#### Website

   https://launchpad.net/ec2-consistent-snapshot
