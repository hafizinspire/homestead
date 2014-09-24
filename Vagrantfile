VAGRANTFILE_API_VERSION = "2"

path = "#{File.dirname(__FILE__)}"

require 'yaml'
require path + '/scripts/homestead.rb'

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  Homestead.configure(config, YAML::load(File.read(path + '/Homestead.yaml')))
end

# Updating the hosts file with all the sites that are defined in Homestead.yaml
if defined? VagrantPlugins::HostsUpdater

	hosts = []
	settings["sites"].each do |site|
		hosts.push(site["map"])
	end
	config.hostsupdater.aliases = hosts

end