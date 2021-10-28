# Create 2 ubuntu machines with vagrant


## Create vms

Download the repository
```
git clone https://github.com/ion-training/vagrant-2vms.git
```

Change directory into the repo
```
cd vagrant-2vms
```

Add necessary scripts to the client.sh and server.sh

Bring up the vms
```
vagrant up
```

Check status of the VMs
```
vagrant status
```
```
vagrant global status
```

SSH into the server vm
```
vagrant ssh server
```

SSH into the client vm
```
vagrant ssh client
```

## Destroy the vms

Check location of the vagrant vms running
```
vagrant global-status
```

Drive into thhat directory
```
cd <DIR-VAGRANT-PROJ>
```

Stop the vms
```
vagrant halt
```

Destroy the VMs
```
vagrant destroy
```

# Sample output

```
$ vagrant up
Bringing machine 'server' up with 'virtualbox' provider...
Bringing machine 'client' up with 'virtualbox' provider...
==> server: Importing base box 'ubuntu/impish64'...
==> server: Matching MAC address for NAT networking...
==> server: Checking if box 'ubuntu/impish64' version '20211014.0.0' is up to date...
==> server: Setting the name of the VM: vagrant-2vms_server_1635455550470_86719
==> server: Fixed port collision for 22 => 2222. Now on port 2200.
==> server: Clearing any previously set network interfaces...
==> server: Preparing network interfaces based on configuration...
    server: Adapter 1: nat
    server: Adapter 2: hostonly
==> server: Forwarding ports...
    server: 22 (guest) => 2200 (host) (adapter 1)
==> server: Running 'pre-boot' VM customizations...
==> server: Booting VM...
==> server: Waiting for machine to boot. This may take a few minutes...
    server: SSH address: 127.0.0.1:2200
    server: SSH username: vagrant
    server: SSH auth method: private key
    server: 
    server: Vagrant insecure key detected. Vagrant will automatically replace
    server: this with a newly generated keypair for better security.
    server: 
    server: Inserting generated public key within guest...
    server: Removing insecure key from the guest if it's present...
    server: Key inserted! Disconnecting and reconnecting using new SSH key...
==> server: Machine booted and ready!

==> server: Booting VM...
==> server: Waiting for machine to boot. This may take a few minutes...
==> server: Machine booted and ready!
==> server: Checking for guest additions in VM...
==> server: Setting hostname...
==> server: Configuring and enabling network interfaces...
==> server: Mounting shared folders...
    server: /vagrant => /Users/ion/Documents/dev/vagrant-proj/vagrant-2vms
==> server: Running provisioner: shell...
    server: Running: /var/folders/k2/jxw8lbzx3k91ml2q8w02zfv00000gq/T/vagrant-shell20211028-48136-wr6oli.sh
    server: server
==> client: Importing base box 'ubuntu/impish64'...
==> client: Matching MAC address for NAT networking...
==> client: Checking if box 'ubuntu/impish64' version '20211014.0.0' is up to date...
==> client: Setting the name of the VM: vagrant-2vms_client_1635455669213_20373
==> client: Fixed port collision for 22 => 2222. Now on port 2201.
==> client: Clearing any previously set network interfaces...
==> client: Preparing network interfaces based on configuration...
    client: Adapter 1: nat
    client: Adapter 2: hostonly
==> client: Forwarding ports...
    client: 22 (guest) => 2201 (host) (adapter 1)
==> client: Running 'pre-boot' VM customizations...
==> client: Booting VM...
==> client: Waiting for machine to boot. This may take a few minutes...
    client: SSH address: 127.0.0.1:2201
    client: SSH username: vagrant
    client: SSH auth method: private key
    client: 
    client: Vagrant insecure key detected. Vagrant will automatically replace
    client: this with a newly generated keypair for better security.
    client: 
    client: Inserting generated public key within guest...
    client: Removing insecure key from the guest if it's present...
    client: Key inserted! Disconnecting and reconnecting using new SSH key...
==> client: Machine booted and ready!
==> server: Checking for guest additions in VM...
==> server: Setting hostname...
==> server: Configuring and enabling network interfaces...
==> server: Mounting shared folders...
    server: /vagrant => /Users/ion/Documents/dev/vagrant-proj/vagrant-2vms
==> server: Running provisioner: shell...
    server: Running: /var/folders/k2/jxw8lbzx3k91ml2q8w02zfv00000gq/T/vagrant-shell20211028-48136-wr6oli.sh
    server: server
==> client: Importing base box 'ubuntu/impish64'...
==> client: Matching MAC address for NAT networking...
==> client: Checking if box 'ubuntu/impish64' version '20211014.0.0' is up to date...
==> client: Setting the name of the VM: vagrant-2vms_client_1635455669213_20373
==> client: Fixed port collision for 22 => 2222. Now on port 2201.
==> client: Clearing any previously set network interfaces...
==> client: Preparing network interfaces based on configuration...
    client: Adapter 1: nat
    client: Adapter 2: hostonly
==> client: Forwarding ports...
    client: 22 (guest) => 2201 (host) (adapter 1)
==> client: Running 'pre-boot' VM customizations...
==> client: Booting VM...
==> client: Waiting for machine to boot. This may take a few minutes...
    client: SSH address: 127.0.0.1:2201
    client: SSH username: vagrant
    client: SSH auth method: private key
    client: 
    client: Vagrant insecure key detected. Vagrant will automatically replace
    client: this with a newly generated keypair for better security.
    client: 
    client: Inserting generated public key within guest...
    client: Removing insecure key from the guest if it's present...
    client: Key inserted! Disconnecting and reconnecting using new SSH key...
==> client: Machine booted and ready!
==> client: Checking for guest additions in VM...
==> client: Setting hostname...
==> client: Configuring and enabling network interfaces...
==> client: Mounting shared folders...
    client: /vagrant => /Users/ion/Documents/dev/vagrant-proj/vagrant-2vms
==> client: Running provisioner: shell...
    client: Running: /var/folders/k2/jxw8lbzx3k91ml2q8w02zfv00000gq/T/vagrant-shell20211028-48136-a4wuxm.sh
    client: client
```

```
$ vagrant status
Current machine states:

server                    running (virtualbox)
client                    running (virtualbox)

This environment represents multiple VMs. The VMs are all listed
above with their current state. For more information about a specific
VM, run `vagrant status NAME`.
$
```

```
$ vagrant global-status
id       name             provider   state    directory                                                     
------------------------------------------------------------------------------------------------------------               
54db3d9  server           virtualbox running  /Users/ion/Documents/dev/vagrant-proj/vagrant-2vms            
fec8857  client           virtualbox running  /Users/ion/Documents/dev/vagrant-proj/vagrant-2vms            
 
The above shows information about all known Vagrant environments
on this machine. This data is cached and may not be completely
up-to-date (use "vagrant global-status --prune" to prune invalid
entries). To interact with any of the machines, you can go to that
directory and run Vagrant, or you can use the ID directly with
Vagrant commands from any directory. For example:
"vagrant destroy 1a2b3c4d"
$
```

```
$ vagrant ssh server
Welcome to Ubuntu 21.10 (GNU/Linux 5.13.0-19-generic x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage

  System information as of Thu Oct 28 21:23:45 UTC 2021

  System load:  0.0               Processes:               104
  Usage of /:   7.8% of 39.86GB   Users logged in:         0
  Memory usage: 8%                IPv4 address for enp0s3: 10.0.2.15
  Swap usage:   0%                IPv4 address for enp0s8: 192.168.56.91


0 updates can be applied immediately.


vagrant@server:~$ 
```

```
$ vagrant ssh client 
Welcome to Ubuntu 21.10 (GNU/Linux 5.13.0-19-generic x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage

  System information as of Thu Oct 28 21:24:24 UTC 2021

  System load:  0.0               Processes:               104
  Usage of /:   7.8% of 39.86GB   Users logged in:         0
  Memory usage: 8%                IPv4 address for enp0s3: 10.0.2.15
  Swap usage:   0%                IPv4 address for enp0s8: 192.168.56.92


0 updates can be applied immediately.


vagrant@client:~$ 
```
