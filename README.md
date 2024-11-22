# SRVLAB - Server Configurations & Documentation


## Cloning Repository on Server

Using sparse shallow checkout to clone only the server folder of the repository on the server.
And creatinga symlink to easy acces to the dockers config files from the home folder.

```bash
git clone https://github.com/UbioZur/srvlab.git --no-checkout --depth 1 --sparse srvlab
cd srvlab
git sparse-checkout set SERVERNAME
git checkout
cd ..
ln -s ./srvlab/stratus/dockers ./dockers
```

## Docker Network & Traefik

When Traefik is present, it should be the first stack to be run as it will create the network required for the others stacks.
