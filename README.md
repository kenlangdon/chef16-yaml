# chef16-yaml

An example of how to use yaml recipes

2020-05-05 - Workaround for kitchen to work while bug is being addressed:

$ touch recipes/default.rb
$ chef install
Building policy chef16-yaml
Expanded run list: recipe[chef16-yaml::default]
Caching Cookbooks...
Installing chef16-yaml >= 0.0.0 from path

Lockfile written to /Users/klangdon/kenlangdon/chef16-yaml/Policyfile.lock.json
Policy revision id: 217aafdf578494c95b18539b88c0b2fb2aa133a90d5bb44f1bb45b861ba06b97
$ rm recipes/default.rb
$ kitchen converge

```
-----> Starting Test Kitchen (v2.4.0)
-----> Converging <default-centos-7>...
       Preparing files for transfer
       Installing cookbooks for Policyfile /Users/klangdon/kenlangdon/chef16-yaml/Policyfile.rb using `chef install`
       Installing cookbooks from lock
       Installing chef16-yaml 0.1.0
       Preparing dna.json
       Exporting cookbook dependencies from Policyfile /var/folders/0n/gl3p2nk13qs0xbcd4rkt929c0000gp/T/default-centos-7-sandbox-20200505-82889-1pmvxzs...
       Exported policy 'chef16-yaml' to /var/folders/0n/gl3p2nk13qs0xbcd4rkt929c0000gp/T/default-centos-7-sandbox-20200505-82889-1pmvxzs

       To converge this system with the exported policy, run:
         cd /var/folders/0n/gl3p2nk13qs0xbcd4rkt929c0000gp/T/default-centos-7-sandbox-20200505-82889-1pmvxzs
         chef-client -z
       Removing non-cookbook files before transfer
       Preparing validation.pem
       Preparing client.rb
       el 7 x86_64
       Getting information for chef current latest for el...
       downloading https://omnitruck.chef.io/current/chef/metadata?v=latest&p=el&pv=7&m=x86_64
         to file /tmp/install.sh.2986/metadata.txt
       trying wget...
       sha1	4cab9012915a15978ba21be9ab6e073fde1d31c0
       sha256	c35f0be7c1b94f653d4bfe6323ae235f9fe4e580ea209c4f9bee3b8a6148a8b4
       url	https://packages.chef.io/files/current/chef/16.0.275/el/7/chef-16.0.275-1.el7.x86_64.rpm
       version	16.0.275
       downloaded metadata file looks valid...
       downloading https://packages.chef.io/files/current/chef/16.0.275/el/7/chef-16.0.275-1.el7.x86_64.rpm
         to file /tmp/omnibus/cache/chef-16.0.275-1.el7.x86_64.rpm
       trying wget...
       Comparing checksum with sha256sum...
       Installing chef latest
       installing with rpm...
       warning: /tmp/omnibus/cache/chef-16.0.275-1.el7.x86_64.rpm: Header V4 DSA/SHA1 Signature, key ID 83ef826a: NOKEY
       Preparing...                          ################################# [100%]
       Updating / installing...
          1:chef-16.0.275-1.el7              ################################# [100%]
       Thank you for installing Chef Infra Client! For help getting started visit https://learn.chef.io
       Transferring files to <default-centos-7>
       +---------------------------------------------+
       ✔ 2 product licenses accepted.
       +---------------------------------------------+
       Starting Chef Infra Client, version 16.0.275
       Creating a new client identity for default-centos-7 using the validator key.
       Using policy 'chef16-yaml' at revision 'b43a5e471e4393c89dc3e3cbdf1d1c2e91c8e7e036ef6eea76d97cefea68171e'
       resolving cookbooks for run list: ["chef16-yaml::default@0.1.0 (fa94fb5)"]
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
           --- /var/www/html/index.html	2020-05-05 16:03:47.115415769 +0000
           +++ /var/www/html/.chef-index20200505-3136-18azzc8.html	2020-05-05 16:03:47.115415769 +0000
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
       Chef Infra Client finished, 4/4 resources updated in 11 seconds
       Downloading files from <default-centos-7>
       Finished converging <default-centos-7> (0m26.96s).
-----> Test Kitchen is finished. (0m29.36s)
```
