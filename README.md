### Building a new vagrant parallels box from definitions (debian7.3-amd64)

**Requirements**:

 - you should have parallels installed (tested with 9)
 - the default ruby on OS X Mavericks is fine
 - go to [http://downloads.vagrantup.com/](http://downloads.vagrantup.com/) and install it

```
vagrant plugin install vagrant-parallels
gem install veewee
bundle exec veewee parallels define 'debian-wheezy' 'https://github.com/shabbirh/debian-box-veewee-parallels/tree/master/definitions/parallels-debian-7.3-amd64-clean'
bundle exec veewee parallels build 'debian75-wheezy'  --workdir=.
bundle exec veewee parallels export 'debian75-wheezy' --workdir=.
```

Now you have a vagrant parallels box.

To import it into vagrant type:

```
vagrant box add 'debian75' './debian75-wheezy.box'
```

To use it:

```
vagrant init 'debian'
vagrant up --provider=parallels
vagrant ssh
```
