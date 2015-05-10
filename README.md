# AWS DevOps Bootstrap
Bootstrapped project for working with AWS using Vagrant and Ansible.

## Security
Do not save your AWS access key/secret key inside your provisioning scripts. Set them using enviornment variables as shown below.
```
export AWS_ACCESS_KEY="AKXXXXXXXXXXXXXXX"
export AWS_SECRET_KEY="XXXXXXXXXXXXXXXXXXXXXXXXXX"
```
This bootsrap expects a `WebServerSG` security group to be present in your AWS configuration. Follow [these](https://docs.aws.amazon.com/AmazonVPC/latest/UserGuide/VPC_Scenario3.html#SecurityGroups-3) instructions to set up the same group.

## Usage
### Pre-requisites
* [Vagrant](https://docs.vagrantup.com/v2/installation/)
* [Vagrant AWS plugin](https://github.com/mitchellh/vagrant-aws)
* [Ansible](http://docs.ansible.com/intro_installation.html)

### The Commands
Then you can control the instance with the following:
* To privision an EC2 instance: `vagrant up`
* Stop the instance: `vagrant halt`
* Terminate the instance: `vagrant destroy`

## License
MIT