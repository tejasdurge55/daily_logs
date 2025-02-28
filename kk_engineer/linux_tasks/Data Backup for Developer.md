Within the Stratos DC, the Nautilus storage server hosts a directory named /data, serving as a repository for various developers non-confidential data. Developer ammar has requested a copy of their data stored in /data/ammar. The System Admin team has provided the following steps to fulfill this request:

a. Create a compressed archive named ammar.tar.gz of the /data/ammar directory.

b. Transfer the archive to the /home directory on the Storage Server.
```
tar -cf ammar.tar /data/ammar
ls
gzip --help
gzip  ammar.tar 
ls
sudo cp ammar.tar.gz /home
```
