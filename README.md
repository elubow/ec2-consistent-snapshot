## ec2-consistenet-snapshot

   This is a fork of the original ec2-consistent-snapshot written by Eric Hammond.

   The difference is that this version has support for MongoDB.
### Installation
    On Ubuntu Lucid EC2 instance:

    sudo apt-get -y install build-essential libio-socket-ssl-perl libdatetime-perl 
    sudo PERL_MM_USE_DEFAULT=1 cpan -fi MongoDB MongoDB::Admin

    Copy this ec2-consistent-snapshot to /usr/bin/ replacing old file.
     
### Usage

   Below is an example command for snapshotting Mongo.  It will lock and fsync the DB, take the snapshot, and then unlock it.  You can add a _--stop_ to have Mongo restart afterwards.


    ec2-consistent-snapshot                                    \
    --mongo                                                    \
    --xfs-filesystem /data                                     \
    --region us-east-1                                         \
    --description "RAID snapshot $(date +'%Y-%m-%d %H:%M:%S')" \
    vol-VOL1 vol-VOL2 vol-VOL3 vol-VOL4 vol-VOL5 vol-VOL6 vol-VOL7 vol-VOL8

#### Author

   Originally by Eric Hammond.  Modified by Eric Lubow.

#### Website

   https://launchpad.net/ec2-consistent-snapshot

   Examples are in a blog post available here: http://eric.lubow.org/2011/databases/mongodb/ec2-consistent-snapshot-with-mongo/
