# F5 Upgrade Process

The following playbook will upgrade your F5 device automatically 

* Generate a Pre Check on the existing Virtual Server Status
* Checks the failover state of a BIG-IP system {starts with standby}
* Prepares the BIG-IP system for an upgrade
* Performs load sys config verify
* Downloads the latest UCS File and uploads it the server
* Installs the image into the specified partition
* Converts the configuration and Boots to the newly upgraded boot location

Which version does it work with 
| version | ltm | asm | apm | f5-dns |
|---|---|---|---|---|
| v12 | pass | pass | pass | pass |
| v13 | pass | pass | pass | pass |
| v14 | pass | pass | pass | pass |
| v15 | pass | pass | pass | pass |
| v16 | pass | pass | pass | pass |
| v17 | pass | pass | pass | pass |


# How to use
Clone the following plabook or just copy and paste it.
* Edit the host file in the inventory folder to include your F5s and the license keys for them
* Credentials have been removed from the inventory
* Download you desired version of F5 and place it in the files folder

# Execute playbook 

To excute playbook run the following command 
```
ansible-playbook your_playbook.yml -e "ansible_user=admin ansible_ssh_pass=W3lcome098! version=17.1.1.3-0.0.5"
```
* note when it asks you to select the version just type the number ex. 17.1.1.3-0.0.5


## Notes
* Need to add mount -o remount,ro /usr for users that have ilx module deployed after version 13 all the way to 16

