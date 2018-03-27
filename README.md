# vagrant-freebsd-4.4-i386-minimal
A custom, minimal VirtualBox vagrant box of FreeBSD 4.4 i386, which is special custom for my another open source project [Z-Language](https://github.com/AlbertZheng/zlang-zvm). But you can also utilize it in your projects which need a FreeBSD 4.4 environment.

For more, please refer to [official hosting site of this box](https://app.vagrantup.com/AlbertZheng/boxes/vagrant-freebsd-4.4-i386-minimal).


## How to play this box

Note: Using vagrant 2.0.1 or previous versions. DON'T use vagrant 2.0.2 that has a unresolved OpenSSL library dependence issue as below error messages !

  > /opt/vagrant/embedded/gems/2.0.3/gems/net-ssh-4.2.0/lib/net/ssh/transport/openssl.rb:112:in `ssh_do_verify':
  > uninitialized constant OpenSSL::Digest::DSS1 (NameError)


- Using this box:
```bash
$ git clone git@github.com:AlbertZheng/vagrant-freebsd-4.4-i386-minimal.git
$ cd vagrant-freebsd-4.4-i386-minimal
$ vagrant up
Bringing machine 'default' up with 'virtualbox' provider...
==> default: Clearing any previously set forwarded ports...
==> default: Clearing any previously set network interfaces...
==> default: Preparing network interfaces based on configuration...
    default: Adapter 1: nat
==> default: Forwarding ports...
    default: 23 (guest) => 2223 (host) (adapter 1)
    default: 22 (guest) => 2222 (host) (adapter 1)
==> default: Running 'pre-boot' VM customizations...
==> default: Booting VM...
==> default: Waiting for machine to boot. This may take a few minutes...
    default: SSH address: 127.0.0.1:2222
    default: SSH username: root
    default: SSH auth method: private key
==> default: Machine booted and ready!
Sorry, don't know how to check guest version of Virtualbox Guest Additions on this platform. Stopping installation.
==> default: Checking for guest additions in VM...
    default: No guest additions were detected on the base box for this VM! Guest
    default: additions are required for forwarded ports, shared folders, host only
    default: networking, and more. If SSH fails on this machine, please install
    default: the guest additions and repackage the box to continue.
    default:
    default: This is not an error message; everything may continue to work properly,
    default: in which case you may ignore this message.
==> default: Machine already provisioned. Run `vagrant provision` or use the `--provision`
==> default: flag to force provisioning. Provisioners marked to run always will still run.
```

- SSH into this box as `root`:
```bash
$ vagrant ssh
```
