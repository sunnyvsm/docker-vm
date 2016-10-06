# Docker VM
This is a simple Ubuntu VM with docker installed.

### Getting Started
1. Clone the repo
2. Open a terminal and navigate to the project folder
3. run `$ vagrant up`
4. once completed run `$ vagrant ssh` to access the VM.

### Working
For each new Project that has a docker container the following needs to be modified.
1. Add the projects *dockerfile* as a shared folder to the VM
2. Forward any needed ports
3. Access the VM and build the docker image
4. Start up the docker image
