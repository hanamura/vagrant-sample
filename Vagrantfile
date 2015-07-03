Vagrant.configure(2) do |config|
  config.vm.box = "precise64"
  config.vm.box_url = "http://files.vagrantup.com/precise64.box"

  config.vm.hostname = 'example.com'
  config.vm.network :private_network, ip: '192.168.11.10'

  config.vm.synced_folder 'www', '/var/www', :create => true, :mount_options => ['dmode=755', 'fmode=644']

  config.vm.provision :shell, path: "provision.sh"

  if Vagrant.has_plugin?('vagrant-hostsupdater')
    config.hostsupdater.remove_on_suspend = true
  end
end
