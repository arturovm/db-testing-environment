# Testing environment for upper.io tools

## Prerequisites

* [Vagrant](https://www.vagrantup.com/)
* [git](https://git-scm.com/)

## Setting up an environment

This should be pretty much straightforward:

```
git clone https://github.com/upper/db-testing-environment.git
cd db-testing-environment
vagrant up
```

The virtual machine is going to install docker and use it to build disposable
containers that can be used for development and testing.

If this is the first time you use `vagrant up` it's going to take a while, just
wait a bit for all the docker images to be built and then log in into the
virtual machine:

```
cd db-testing-environment
vagrant ssh
```

Once inside the virtual machine you can confirm all the images are working with
`docker ps`

```
docker ps
```

To turn off the machine use `vagrant stop` outside the virtual machine and
within the checked out directory:

```
cd db-testing-environment
vagrant stop
```

To turn it on again use `vagrant up --provision` or `vagrant up && vagrant
provision`, after the first time turning on the machines will take considerably
less time.
