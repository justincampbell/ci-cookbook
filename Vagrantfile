require 'berkshelf/vagrant'

Vagrant::Config.run do |config|
  config.vm.box = "opscode-centos-6.3"
  config.vm.box_url = "https://opscode-vm.s3.amazonaws.com/vagrant/opscode_centos-6.3_chef-11.2.0.box"

  config.vm.host_name = "ci"
  config.vm.network :hostonly, "33.33.33.10"

  config.vm.provision :chef_solo do |chef|
    chef.run_list = [
      "recipe[ci-cookbook::default]"
    ]
  end
end
