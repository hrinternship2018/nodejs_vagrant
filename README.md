# nodejs_server
Vagrantfile and init nodejs environment

## init
In host OS command prompt, excute following command. Excution in admin mode is recommanded.
start virtual machine
```
vagrant up
```

login to virtural machine
```
vagrant ssh
```

## Tip
Windows+vagrant enviroment maybe have trouble.
when installation of dependency of nodejs project, that may be because of permission of symlink ,then execute command below in windows admin command prompt. (default is L2L:1 R2R:0 L2R:1 R2L:0)
```
fsutil behavior set SymlinkEvaluation L2L:1 R2R:1 L2R:1 R2L:1
```

And you don't have to forget `vagrant up` in admin mode.

### npm error

`npm install` has problem in excution within the synced files or directry. Then try `yarn install`.
