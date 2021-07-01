Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/bionic64"
  config.vm.provision "docker",
    images: ["registry.gitlab.com/salamachinas/infra-challenge:latest"]
  config.vm.provision "ansible_local" do |ansible|
    ansible.playbook = "playbook.yml"
    # ansible.galaxy_role_file = "requirements.yml"
  end
  config.vm.provision "shell",
    inline: "docker-compose -f /vagrant/docker-compose.yml up"
  config.vm.network "forwarded_port",
    guest: 80, host: 8080
end