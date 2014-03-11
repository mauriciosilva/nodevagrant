## a node env vagrant setup 

simple node development environment vagrant setup

includes the following recipes 

  `devbox::nodejs`

  `devbox::nvm`

  `devbox::vim`

  `devbox::redis`

check [https://github.com/mauriciosilva/devbox](https://github.com/mauriciosilva/devbox) for more info on recipes.

*updated readme to follow*

### setup

* make sure you have ruby 1.9+ installed.
* install virtual box from [https://www.virtualbox.org/wiki/Downloads](https://www.virtualbox.org/wiki/Downloads)
* install vagrant from [http://vagrantup.com](http://vagrantup.com)

execute the following:

`$ vagrant plugin install vagrant-berkshelf`
`$ vagrant plugin install vagrant-omnibus`


### starting vm

`berks install`

`vagrant up`

as soon as box comes up

`vagrant ssh`



