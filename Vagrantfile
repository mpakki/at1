Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/focal64"
  config.vm.define "at1"
  config.vm.provider :virtualbox do |vb|
    vb.name = "at1"
  end
  config.vm.hostname = "at1"
  config.vm.provision "docker",
    images: ["registry.gitlab.com/salamachinas/infra-challenge:latest"]
  config.vm.provision "ansible_local" do |ansible|
    ansible.playbook = "playbook.yml"
    ansible.install_mode = "pip"
    ansible.pip_install_cmd = "curl https://bootstrap.pypa.io/pip/2.7/get-pip.py | sudo python"
    ansible.galaxy_role_file = "requirements.yml"
  end
  config.vm.network "forwarded_port",
    guest: 80, host: 8080
end
