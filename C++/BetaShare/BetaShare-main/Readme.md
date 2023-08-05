#BetaShare

Peer to Peer File sharing network system mimicing Bitrrent's Choke Unchoke prortocol for peer discovery via single tracker.

## Prerequisites
Following C++ libraries are needed (Linux)
```
openssl; ibssl-dev
Tools: CMake for compiling and build management.
```

## Floder Structure for compiling.
* Code is divided into 2 folders: client and tracker
* Both folders have corresponding Makefiles. 

## Running
* Run tracker
```
./tracker_86317877 <my_tracker_ip>:<my_tracker_port> <other_tracker_ip>:<other_tracker_port> <seederlist_file> <log_file>
```
* Run client
```
./client_86317877 <CLIENT_IP>:<UPLOAD_PORT> <TRACKER_IP_1>:<TRACKER_PORT_1> <TRACKER_IP_2>:<TRACKER_PORT_2> <log_file>
```
log_file(s) can be used to check the activities

## Commands for client
* File share: 
share <local_file_path> <filename>.<file_extension>.mtorrent

It generates an mtorrent file and shares the information with tracker so that tracker can add the peer to seederlist

* Get File:
get <path_to_.mtorrent_file> <destination_path>

Gets data about the peers sharing the required file and starts downloading the file in destination_path

* Cancle sharing
remove <filename.mtorrent>

Deletes mtorrent file and remove information about the peer from the tracker

* Show downloads
show downloads

show downloaded and downloading files

* Close the peer
exit

Remove information from the tracker and closes the client program

Note: Currently works with one tracker system. But for future advancements it can be made available for more than 1 clusters of peers utilizing multiple trackers system where 1 traker watches a single cluster.
