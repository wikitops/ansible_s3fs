# Ansible : Playbook S3fs
The aim of this project is to deploy s3fs and configure multiple AWS bucket on Vagrant instance.

## Getting Started

These instructions will get you a copy of the project up and running on your local machine for development and testing purposes.

### Prerequisites

What things you need to run this Ansible playbook :

* [Vagrant](https://www.vagrantup.com/docs/installation/) must be installed on your computer
* Update the Vagrant file based on your computer (CPU, memory), if needed
* You must have download the ubuntu Xenial64 vagrant box :

```
vagrant box add https://app.vagrantup.com/ubuntu/boxes/xenial64
```
* Make sure to create an AWS Bucket
* Make sure to create an AWS IAM user with AccessKey

### Usage

A good point with Vagrant is that you can create, update and destroy all architecture easily with some commands.

Be aware that you need to be in the Vagrant directory to be able to run the commands.

#### Build Environment

Vagrant needs to init the project to run and build it :

```
vagrant up
```

After build, you can check which virtual machine Vagrant has created :

```
vagrant status
```

If all run like it is expected, you should see something like this :

```
$ vagrant status

Current machine states:

s3fs01                  running (virtualbox)
```

#### Deployment

To deploy the s3fs software, you just have to run the Ansible playbook s3fs.yml with this command :

```
ansible-playbook s3fs.yml
```

If everything run has expected, you should see the command to mount AWS bucket on instance startup in the fstab file with this command :

```
cat /etc/fstab
```

And you should access your bucket throw the local mount.

#### Destroy

To destroy on what Vagrant has created, just run this command :

```
vagrant destroy
```

## Author

Member of Wikitops : https://www.wikitops.io/
