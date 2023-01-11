# haproxy_home_config
HA Proxy home setup for multiple DNS names resolving to home ISP with 1 IP address


## Overview:  
I was playing around with HA Proxy, trying to host several websites from my Home internet connection, and I came up with this configuration, and used some NO-IP dns forwarding to my home IP address.  
This configuration works for multiple websites using HAProxy's ACL function (access control list) by routing the requested DNS name over 80/443 to the HAProxy load balancer.  
HAProxy does the port translation for the servers in the backend which are all running on different ports.

One last note:  I figured out that you can store the multiple SSL/TLS certs in one location using this block
```
    # Default SSL material locations
    ca-base /etc/ssl/certs
    crt-base /etc/ssl/private
```
and HAProxy with serve up the certificate for the requested site.


  [![HitCount](https://hits.dwyl.com/ferdinandbergen/haproxy_home_config.svg?style=flat-square&show=unique)](http://hits.dwyl.com/ferdinandbergen/haproxy_home_config)
