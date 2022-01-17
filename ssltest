#!/bin/sh
PATH=/usr/local/bin:/usr/local/sbin:/bin:/sbin:/usr/bin:/usr/sbin

for cipher in `openssl ciphers -s 'ALL:eNULL' | sed 's/:/ /g'`;do
       echo -n|openssl s_client -cipher $cipher -connect $1:443 -tls1_2 > /dev/null 2>&1
       if [ $? = 0 ];then
               echo TLSv1.2 $cipher IS support
       fi
done
