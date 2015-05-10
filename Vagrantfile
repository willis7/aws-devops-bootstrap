# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  # Box configuration
  config.vm.box = "dev"
  config.vm.box_url = "https://github.com/mitchellh/vagrant-aws/raw/master/dummy.box"

  # Provider
  config.vm.provider :aws do |aws, override|
  	aws.keypair_name = "dev"
  	override.ssh.username = "ubuntu"
  	override.ssh.private_key_path = "~/.ssh/amz.pem"

  	aws.ami = "ami-234ecc54" # Ubuntu 14.04.1 LTS
  	aws.region = "eu-west-1"
  	aws.instance_type = "t2.micro"
  	aws.security_groups = ["WebServerSG"]

  	aws.tags = {
  		"Name" => "Dev Vagrant"
  	}
  end

  # Provisioning
  config.vm.provision :ansible do |ansible|
  	ansible.playbook = "provisioning/playbook.yml"
  end
end