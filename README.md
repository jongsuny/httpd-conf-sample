# httpd-conf-sample
This is apache httpd config sample.

**Remember**, this is sample,before apply to your server, make sure all config goes right.

======
## Includes

1. httpd.conf                   # base config
2. common/base.conf             # common apache config
3. common/modules.conf          # loaded modules
4. common/cache.conf            # cache options,gzip compression
5. common/mpm.conf              # mpm config for several platforms
6. common/secure.conf           # some configs related secure
7. common/server-status.conf    # apache server status config,config as only allow from internal IP
8. tomcat/ajp.conf              # examples for integrate with tomcat via mod_jk
9. tomcat/workers.conf          # modjk config samples
10. tomcat/proxy.conf           # example for integrate with tomcat via proxy
11. tomcat/ajp-proxy.conf       # example for integrate with tomcat via ajp proxy

======
## How to use

```shell
cd $HTTPD_HOME
git clone https://github.com/jongsuny/httpd-conf-sample.git
mv conf conf_bak
ln -sf httpd-conf-sample conf
apachectl -t
apachectl stop
apachectl start
curl http://localhost:8088/
```

======
### Before apply, you must...

1. make sure your apache version is 2.4 or above
2. change **ServerRoot** to your apache root directory. ex)_/Users/jongsuny/apps/apache-httpd-2.4.20_
3. change **ServerAdmin** to your email address. ex)jongsuny@github.com
4. change **ServerName** to your domain. ex)github.com
5. change your **Listen** to your server listening port. ex)80
6. change _/Users/jongsuny/apps/apache-httpd-2.4.20/htdocs_ to your proper directory,like tomcat webapps
7. change **DocumentRoot** to same above 6.
8. mark as comment useless files included from httpd.conf. ex) #Include conf/tomcat/ajp_proxy.conf
9. you can also recover from your original config file. see original
