Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/focal64"
  config.vm.provision "docker",
    images: ["registry.gitlab.com/salamachinas/infra-challenge:latest"]
  config.vm.provision "ansible_local" do |ansible|
    ansible.playbook = "playbook.yml"
    ansible.install_mode = "pip"
    ansible.pip_install_cmd = "curl https://bootstrap.pypa.io/pip/2.7/get-pip.py | sudo python"
    # ansible.version = "2.10.7"
    ansible.galaxy_role_file = "requirements.yml"
  end
  # config.vm.provision "shell",
  #   inline: "docker-compose -f /vagrant/docker-compose.yml up"
  config.vm.network "forwarded_port",
    guest: 80, host: 8080
end