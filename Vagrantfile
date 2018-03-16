# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure('2') do |config|
  config.vm.box = 'bento/ubuntu-16.04'

  config.vm.provider 'virtualbox' do |v|
    v.memory = 512
    v.cpus = 2
  end

  config.vm.network "forwarded_port", guest: 2999, host: 2999, protocol: "udp"
  config.vm.network "forwarded_port", guest: 3000, host: 3000
  config.vm.network "forwarded_port", guest: 3001, host: 3001

  config.vm.provision 'ansible' do |ansible|
    ansible.become = true
    ansible.playbook = 'tests/test-vagrant.yml'
    ansible.raw_arguments = [ '--diff' ]
    ansible.compatibility_mode = '2.0'
  end
end
