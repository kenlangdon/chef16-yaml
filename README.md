# Chef 16 Yaml Example

## An example of how to use yaml recipes

## Environment Set-up

1. Install [Chef Workstation](https://downloads.chef.io/chef-workstation)
2. Install [git](https://git-scm.com/downloads)
3. Clone this repo
4. Try out the yaml that's included in the recipes folder (installs and starts httpd with a "Hello World" index.html) or modify it to use other [resources](https://docs.chef.io/resources/)

Once you're ready to try it, change into the repo's root where the kitchen.yml is found and ...

`kitchen converge`


```
-----> Starting Test Kitchen (v2.5.1)
-----> Creating <default-centos-7>...
       Bringing machine 'default' up with 'virtualbox' provider...
       ==> default: Importing base box 'bento/centos-7'...
==> default: Matching MAC address for NAT networking...
       ==> default: Setting the name of the VM: kitchen-chef16-yaml-default-centos-7-d726ad36-1109-4119-8484-004252c6f8b8
       ==> default: Clearing any previously set network interfaces...
       ==> default: Preparing network interfaces based on configuration...
           default: Adapter 1: nat
       ==> default: Forwarding ports...
           default: 22 (guest) => 2222 (host) (adapter 1)
       ==> default: Running 'pre-boot' VM customizations...
       ==> default: Booting VM...
       ==> default: Waiting for machine to boot. This may take a few minutes...
           default: SSH address: 127.0.0.1:2222
           default: SSH username: vagrant
           default: SSH auth method: private key
           default: Vagrant insecure key detected. Vagrant will automatically replace
           default: this with a newly generated keypair for better security.
           default:
           default: Inserting generated public key within guest...
           default: Removing insecure key from the guest if it's present...
           default: Key inserted! Disconnecting and reconnecting using new SSH key...
       ==> default: Machine booted and ready!
       ==> default: Checking for guest additions in VM...
           default: The guest additions on this VM do not match the installed version of
           default: VirtualBox! In most cases this is fine, but in rare cases it can
           default: prevent things such as shared folders from working properly. If you see
           default: shared folder errors, please make sure the guest additions within the
           default: virtual machine match the version of VirtualBox you have installed on
           default: your host and reload your VM.
           default:
           default: Guest Additions Version: 5.2.6
           default: VirtualBox Version: 6.0
       ==> default: Setting hostname...
       ==> default: Mounting shared folders...
           default: /tmp/omnibus/cache => /Users/klangdon/.kitchen/cache
       ==> default: Machine not provisioned because `--no-provision` is specified.
       [SSH] Established
       Vagrant instance <default-centos-7> created.
       Finished creating <default-centos-7> (0m47.26s).
-----> Converging <default-centos-7>...
       Preparing files for transfer
       Policy lock file doesn't exist, running `chef install` for Policyfile /Users/klangdon/kenlangdon/chef16-yaml/Policyfile.rb...
       Building policy chef16-yaml
       Expanded run list: recipe[chef16-yaml::default]
       Caching Cookbooks...
       Installing chef16-yaml >= 0.0.0 from path

       Lockfile written to /Users/klangdon/kenlangdon/chef16-yaml/Policyfile.lock.json
       Policy revision id: 55cc8343f8c2d867d85c2230e8c7bceff4c10377b5b44264695ac800499af2ec
       Preparing dna.json
       Exporting cookbook dependencies from Policyfile /var/folders/0n/gl3p2nk13qs0xbcd4rkt929c0000gp/T/default-centos-7-sandbox-20200610-66731-b7b1ur...
       Exported policy 'chef16-yaml' to /var/folders/0n/gl3p2nk13qs0xbcd4rkt929c0000gp/T/default-centos-7-sandbox-20200610-66731-b7b1ur

       To converge this system with the exported policy, run:
         cd /var/folders/0n/gl3p2nk13qs0xbcd4rkt929c0000gp/T/default-centos-7-sandbox-20200610-66731-b7b1ur
         chef-client -z
       Removing non-cookbook files before transfer
       Preparing validation.pem
       Preparing client.rb
       el 7 x86_64
       Getting information for chef current latest for el...
       downloading https://omnitruck.chef.io/current/chef/metadata?v=latest&p=el&pv=7&m=x86_64
         to file /tmp/install.sh.2961/metadata.txt
       trying wget...
       sha1	ff00c86369765e9bea290c4b5c44d9c5160c5f1b
       sha256	9aed2e1d1f021bfeb54b139e7f6710cadf5dde1f2d7644d80adb4409022fc52b
       url	https://packages.chef.io/files/current/chef/16.2.9/el/7/chef-16.2.9-1.el7.x86_64.rpm
       version	16.2.9
       downloaded metadata file looks valid...
       downloading https://packages.chef.io/files/current/chef/16.2.9/el/7/chef-16.2.9-1.el7.x86_64.rpm
         to file /tmp/omnibus/cache/chef-16.2.9-1.el7.x86_64.rpm
       trying wget...
       Comparing checksum with sha256sum...
       Installing chef latest
       installing with rpm...
       warning: /tmp/omnibus/cache/chef-16.2.9-1.el7.x86_64.rpm: Header V4 DSA/SHA1 Signature, key ID 83ef826a: NOKEY
       Preparing...                          ################################# [100%]
       Updating / installing...
          1:chef-16.2.9-1.el7                ################################# [100%]
       Thank you for installing Chef Infra Client! For help getting started visit https://learn.chef.io
       Transferring files to <default-centos-7>
       +---------------------------------------------+
       ✔ 2 product licenses accepted.
       +---------------------------------------------+
       Starting Chef Infra Client, version 16.2.9
       Creating a new client identity for default-centos-7 using the validator key.
       Using policy 'chef16-yaml' at revision '55cc8343f8c2d867d85c2230e8c7bceff4c10377b5b44264695ac800499af2ec'
       resolving cookbooks for run list: ["chef16-yaml::default@0.1.0 (4f8b018)"]
       Synchronizing Cookbooks:
         - chef16-yaml (0.1.0)
       Installing Cookbook Gems:
       Compiling Cookbooks...
       Converging 3 resources
       Recipe: chef16-yaml::default
         * yum_package[httpd] action install
           - install version 0:2.4.6-93.el7.centos.x86_64 of package httpd
         * template[/var/www/html/index.html] action create
           - create new file /var/www/html/index.html
           - update content in file /var/www/html/index.html from none to 2914aa
           --- /var/www/html/index.html	2020-06-10 21:11:10.142876257 +0000
           +++ /var/www/html/.chef-index20200610-3111-yg7xz0.html	2020-06-10 21:11:10.142876257 +0000
           @@ -1 +1,6 @@
           +<html>
           +  <body>
           +    <h1>hello world</h1>
           +  </body>
           +</html>
           - restore selinux security context
         * service[httpd] action enable
           - enable service service[httpd]
         * service[httpd] action start
           - start service service[httpd]

       Running handlers:
       Running handlers complete
       Chef Infra Client finished, 4/4 resources updated in 10 seconds
       Downloading files from <default-centos-7>
       Finished converging <default-centos-7> (0m30.12s).
-----> Test Kitchen is finished. (1m20.85s)
```
