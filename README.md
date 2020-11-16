# Remote.it Scripts

This is a collection of shell scripts to make calls to the remote.it API for establishing proxy connections to a remote host.

## Files

* .rt3-setup : Contains the variables needed to pass as arguments in the shell scripts. Some variables will need to be updated based on a change in network, or after an extended down time. 
You will need to source this file in your shell configuration (`~/.bashrc` or `~/.zshrc` in order for the scripts to work)
* dev_check_list : Checks the status of the devices associated with the specified remote.it developer account. Returns the output in (prettier-formatted) JSON.
* key : fetches and returns your developer token. Token changes roughly every 24 hours. Run at least once per day to stay updated.
* rem0te_connect : executes a remote connection to a specified service on a given device associated with the developer account beingused. Writes the retrieved proxy address and port to the screen.
Usage : ` ./rem0te_connect $RT3_DEVICE_ADDRESS [HOST_IP]`
NB: Host IP is set as default to the variable $RT3_LAPTOP_PUBLIC_IP, which is the public IPv4 address of the computer making the connection request. Rarely needs to be specified as an argument to this script.
* rem0te_connect_ssh_autologin : Convenience script to retrieve ssh login credentials and log in to remote host automatically. No arguments required. 


## Steps

1. `$ ./key`
2. `$ ./dev_check_list`
3. `$ ./rem0te_connect $RT3_DEVICE_ADDRESS` or `./rem0te_connect_ssh_autologin` [Depends on what you want to do.]
