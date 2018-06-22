# No longer maintained

We only maintain the following:
* stable releases
  * package based installation https://github.com/stellar/packages
  * docker based Horizon & core combo https://github.com/stellar/docker-stellar-core-horizon
* experimental releases
  * docker based stellar-core only https://github.com/stellar/docker-stellar-core

# stellar vagrant examples

## Usage

Each directory contains a Vagrantfile that describes a particular scenario.

Start off by cloning the repo:

```sh
git clone https://github.com/stellar/vagrant-examples
cd vagrant-examples
```

Then cd into one of the directories to start your desired vagrant scenario.

### single-peer

```sh
cd single-peer
vagrant up
```

This will stand up a single peer that trusts the SDF testnet nodes.

### stellare-core-base

```sh
cd stellar-core-base
vagrant up
```

This builds and installs stellar-core then cleans up any extra artifacts yielding a vagrant-friendly disk image.

Once it's done run this to package the box:

```sh
vagrant package --output stellar-core-base.box
```

Then you can upload it to [HashiCorp's Atlas](https://atlas.hashicorp.com) or
host it wherever is convenient for your team.

The latest SDF builds are available as "[stellar/stellar-core-base](https://atlas.hashicorp.com/stellar/boxes/stellar-core-base)" on Atlas.

### full-network (WIP)

```sh
cd full-network
vagrant up
```

This stands up a 3 node private stellar network similar to the SDF testnet. You
can use this for testing or just to get a feel for how to run stellar in
production.

**Note:** As of 2015/07/30 the horizon VM is not provisonable and the core vms don't achieve consensus. This appears to be an issue with the start script. Rather than fixing this script, any new examples will be based on https://github.com/stellar/docker-stellar-core

## Contributing

Please [see CONTRIBUTING.md for details](CONTRIBUTING.md).
