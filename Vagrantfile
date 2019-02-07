Vagrant.require_version ">= 1.7.0"

Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/bionic64"
  config.vm.box_version =  "20181214.0.0"

  config.vm.define "myproj-dev" do |machine|
    config.vm.network "forwarded_port", guest: 8000, host: 8000
    config.vm.network "forwarded_port", guest: 5000, host: 5000
    config.vm.network "forwarded_port", guest: 80, host: 8080
    config.vm.hostname = "myproj-dev"
  end

  config.vm.provision "ansible_local" do |ansible|
    ansible.playbook = "deploy/playbook.yml"
    ansible.install_mode = "pip"
    ansible.compatibility_mode = "2.0"
    ansible.limit = "myproj-dev"
    # ansible.vault_password_file = "deploy/DEV_PWD"
  end
end
