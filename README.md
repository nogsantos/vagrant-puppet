# Vagrant Puppet

Puppet study using vagrant with virtual box.

## Vagrant Commands

Create vagrant virtual machine

```bash
$ vagrant up 
```

Connect to created machine

```bash
$ vagrant ssh 
```

Reload machine with new configurations

```bash
$ vagrant reload
```

Completely removes created machine

```bash
$ vagrant destroy
```

## Puppet

To run puppet, inside virtual machine, run:

```bash
$ sudo puppet apply /vagrant/manifests/web.pp
```

This command will run `web.pp` tasks.

## Issues

To run vagrant in my environment, occurred some errors, so, to fix them, follow the saga:

### Installation of `vagrant-libvirt` plugin failed on Fedora 29

```bash
$ sudo dnf install -y qemu libvirt libvirt-devel ruby-devel gcc qemu-kvm
```

### GuestAdditions seems to be installed (5.0.14) correctly, but not running.

After `vagrant up` do 

```bash
$ vagrant vbguest --do install 
```

then `vagrant reload` to check 

```bash
$ vagrant vbguest --status 
```

Should be ok