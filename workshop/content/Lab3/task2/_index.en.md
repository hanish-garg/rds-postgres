+++
title = "2.	Connecting to the Multi-AZ"
date = 2020-04-22T23:10:28-05:00
weight = 30
+++

Using the client workstation configured in Lab 2

Run the command below, replacing the [DBEndpont] placeholder with the value of the DB endpoint created in the preceding steps at  [DB DBEndpont]({{< ref "/Lab1/_index.en.md" >}}) to find out the the current hostname & current time of the MySQL primary instance

```
while true ; do mysql -h[DBEndpoint] -u$DBUSER -p"$DBPASS" -e "  SELECT now(),@@hostname,@@global.innodb_read_only  ;"   ; echo -e "\n\n"  ; sleep 10 ;  done
```

You should be seeing output for the above command something similar to below

{{% img "output.png" "Output" %}}
