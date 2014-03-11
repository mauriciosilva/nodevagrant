# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  %w[
    vagrant-berkshelf
    vagrant-omnibus
    vagrant-cachier
  ].each { | plugin |
    Vagrant.require_plugin plugin
  }

  config.omnibus.chef_version = :latest

  config.vm.hostname = "node-environment-berkshelf"

  config.vm.box = "devbox-vagrant"

  config.vm.box_url = "https://dl.dropbox.com/u/31081437/Berkshelf-CentOS-6.3-x86_64-minimal.box"

  config.vm.network :private_network, ip: "33.33.33.10"

  config.berkshelf.enabled = true

  config.vm.provider :virtualbox do |vb|
   vb.customize ["modifyvm", :id, "--memory", "1024", "--cpus", "2"]
  end

  config.vm.provision :chef_solo do |chef|
    chef.json = { 
      'vim' => {
        'install_dir' => '/etc/vim',
        'config_file_name' => 'vimrc.local',
        'plugins' => [
          "git://github.com/scrooloose/nerdtree.git",
          "git://github.com/kien/ctrlp.vim.git",
          "git://github.com/altercation/vim-colors-solarized.git",
          "https://github.com/godlygeek/tabular.git",
          "https://github.com/jnwhiteh/vim-golang.git"
        ]
      }
    }
    chef.run_list = [
        "recipe[devbox::nodejs]",
        "recipe[devbox::vim]"
    ]
  end
end
