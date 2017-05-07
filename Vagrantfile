# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|

   config.vm.box = "debian/jessie64"

   config.vm.network "forwarded_port", guest: 8080, host: 8080

   config.vm.synced_folder "/mnt/storage/downloads/complete", "/opt/downloads/sabnzbd/downloads"
   # config.vm.synced_folder "/mnt/storage/watchfolder", "/opt/appdata/sabnzbd/watchfolder"
   config.vm.synced_folder "/mnt/storage/downloads/incomplete", "/opt/downloads/sabnzbd/incomplete"

   config.vm.provider :virtualbox do |v|
     v.name = "epsilon.dev"
     v.memory = 16048
     v.cpus = 4
   end

   config.vm.provision :ansible do |ansible|
     ansible.verbose = "vvv"
     ansible.playbook = "main.yml"


   end



end
