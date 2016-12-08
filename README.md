## Vagrant issue

Vagrant deletes my data after `vagrant halt` and `vagrant up`

Please test it and post the feedback on https://gitter.im/mitchellh/vagrant @ehernandez-xk

- Vagrant: 1.8.6
- VB: 5.1.6r110634
- mac OS X Yosemite 10.10.5

```
git clone
vagrant up
# provision: creates /xxx directory
vagrant ssh
ls -la /xxx
sudo mkdir /yyy
exit
vagrant halt
vagrant up
vagrant ssh
ls -la /xxx
ls: /xxx: No such file or directory
```

and the directories xxx yyy are gone

Vagrant restores all the files

### Another weird behaviour, the docker images are not deleted.

```
vagrant ssh
docker pull alpine
exit
vagrant halt
vagrant up
vagrant ssh
docker images
```

The docker image is still there.
