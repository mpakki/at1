# How to install and maintanance application

## Requirements

To run application you will need:

1. Ubuntu 20.10
1. Vagrant 2.2.9 with VirtualBox 6.1.16_Ubuntur140961 or higher

## Get the code and place you there

To get code please run:
```bash
git clone https://github.com/mpakki/at1.git
cd at1
```

## Start it up

To start application you need to run the following command:

```bash
vagrant up
```

## Clean up

To halt and delete VM you started please run:

```bash
vagrant destroy -f
```

## Maintenance

Application runs as a 3 backend containers and one proxy so you can manage these containers (vagrant_backend*) as independent.