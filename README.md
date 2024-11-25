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


## Traefik & Multiple Cloudflare Accounts

To use a domain name on traefik that is not on the main cloudflare account, there is the need to use the CNAME trick as traefik does not accept multiple account per provider type (Like multiple cloudflare account).

If traefik is setup to used `cloudflare_account_1` where `domain1.tld` is setup, and you need to redirect (with SSL) `domain2.com` which is connected to `cloudflare_account_2`, here how to do it using the [CNAME trick](https://letsencrypt.org/2019/10/09/onboarding-your-customers-with-lets-encrypt-and-acme/#the-advantages-of-a-cname).

* `cloudflare_account_2`: Prepare the CNAMEs
    * `service.domain2.com` CNAME to `domain1.tld`: Redirect all request to your server ip where traefik is installed.
    * `_acme-challenge.service.domain2.com` CNAME to `_acme-challenge.domain1.tld`: Redirect the ACME challenge to the server where traefik is installed.
* `Traefik`: Configure traefik for your docker
````yaml
labels:
  # ROUTER Enable traefik for reverse proxy
  - traefik.enable=true
  - traefik.http.routers.myapp-r.rule=Host(`service.domain2.com`)
  - traefik.http.routers.myapp-r.entrypoints=websecure
  - traefik.http.routers.myapp-r.tls.certresolver=cloudflare
  - traefik.http.routers.myapp-r.tls.domains[0].main=domain1.tld
  - traefik.http.routers.myapp-r.tls.domains[0].sans=*.domain1.tld
  - traefik.http.routers.myapp-r.service=myapp-s
  - traefik.http.services.myapp-s.loadbalancer.server.port=8080
````

Now when you connect to `service.domain2.com`, you have a SSL certificate from let's encrypt that is valid.
