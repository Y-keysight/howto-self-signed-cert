# How to create Self Signed Certificate

```
35  openssl genrsa -out sy.key 2048
36  openssl req -new -key sy.key -out sy.csr
37  openssl x509 -req -in sy.csr -signkey sy.key -out sy.crt
32  openssl x509 -in sy.crt -out sy.pem -outform PEM
```

```
# openssl req -new -key sy.key -out sy.csr
You are about to be asked to enter information that will be incorporated
into your certificate request.
What you are about to enter is what is called a Distinguished Name or a DN.
There are quite a few fields but you can leave some blank
For some fields there will be a default value,
If you enter '.', the field will be left blank.
-----
Country Name (2 letter code) [AU]:US
State or Province Name (full name) [Some-State]:Texas
Locality Name (eg, city) []:Austin
Organization Name (eg, company) [Internet Widgits Pty Ltd]:*******
Organizational Unit Name (eg, section) []:nvs
Common Name (e.g. server FQDN or YOUR name) []:hawkeye
Email Address []:*********

Please enter the following 'extra' attributes
to be sent with your certificate request
A challenge password []:
An optional company name []:
#
```
