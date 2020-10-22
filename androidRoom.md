# ANDROID ROOM   
[Home](./README.md) 

[Overview](https://developer.android.com/training/data-storage/room)  

__Room__ provides an abstraction layer over SQLite to allow fluent database access while harnessing the full power of SQLite.   

__Why?__: It allows persisting that data locally. The most common use case is to cache relevant pieces of data. That way, when the device cannot access the network, the user can still browse that content while they are offline. Any user-initiated content changes are then synced to the server after the device is back online.  

