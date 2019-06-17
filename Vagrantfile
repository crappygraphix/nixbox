Vagrant.configure('2') do |config|
  config.vm.box = "crappygraphix/nixos-19.03-x86_64"
  config.vm.hostname = 'nixos-dev-box'

  config.vm.provider 'virtualbox' do |v, override|
    v.memory = 16384
    v.cpus = 6
    v.customize ["modifyvm", :id, "--audio", "none"]
    v.customize ["modifyvm", :id, "--vrde", "off"]
    v.customize ["guestproperty", "set", :id, "--timesync-threshold", 1000]
    override.vm.network 'private_network', ip: '128.128.128.128'
  end

  config.vm.synced_folder '.', '/vagrant', disabled: true
  config.vm.synced_folder '.', '/src'
end
