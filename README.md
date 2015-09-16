# dev-interview-code
A series of code exercises for potential employment candidates

## To Setup Candidate Development Environment

1) Install [VirtualBox](https://www.virtualbox.org/wiki/Downloads), a free to use virtual machine manager.
2) Install [Vagrant](http://www.vagrantup.com/downloads.html) on the host machine
3) From the root of this repository run the command
```bash
vagrant up --provider virtualbox
```
This will start up a virtual machine with all the needed development tools. To login to the machine, use:
username: vagrant
password: vagrant

The code exercises for the candidate will be mounted into the VM at /home/vagrant/assignments.

## Cleaning up after an interview

1) Destroy the VM that was used for the interview by running the following command from the root of the project.
```bash
vagrant destroy
```


