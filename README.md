### Building a new vagrant parallels box from definitions (debian7.3-amd64)

**Requirements**:

 - you should have parallels installed (tested with 9)
 - the default ruby on OS X Mavericks is fine
 - go to [http://downloads.vagrantup.com/](http://downloads.vagrantup.com/) and install it

```
vagrant plugin install vagrant-parallels
sudo gem install veewee
bundle exec veewee parallels define 'debian-73' 'https://github.com/mkoryak/vagrant-parallels-ubuntu-12.04-lts.git/definitions/parallels-ubuntu-12.04-server-amd64'
bundle exec veewee parallels build 'debian-73'  --workdir=.
bundle exec veewee parallels export 'debian-73' --workdir=.
```

Now you have a vagrant parallels box.

To import it into vagrant type:

```
vagrant box add 'ubuntu' './debian73.box'
```

To use it:

```
vagrant init 'debian'
vagrant up --provider=parallels
vagrant ssh
```