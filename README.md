### Building a new vagrant parallels box from definitions (debian7.3-amd64)

**Requirements**:

 - you should have parallels installed (tested with 9)
 - the default ruby on OS X Mavericks is fine
 - go to [http://downloads.vagrantup.com/](http://downloads.vagrantup.com/) and install it

```
vagrant plugin install vagrant-parallels
TODO
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