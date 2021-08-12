# MEFS Daemon flow

This doc is aimed at describing how the mefs daemon will start and go through initializations.

1. Args parsing. The arguments will be the state in which the node will start, by default it is mute, but it can start in anxious, calm and rude.
2. Daemonize the process.
3. Create (If the dirs already don't exist) the /var/lib/mefs dirs which is responsible for metadata store and /var/run/mefs dirs for storing the running daemon and process data.
4. Read the config file (default path being /home/mefs.conf ) for messaging system broker details and configuration.
5. based on the input, get into the state
