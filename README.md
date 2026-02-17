# How to create Self Signed Certificate

```
35  openssl genrsa -out sy.key 2048
36  openssl req -new -key sy.key -out sy.csr
37  openssl x509 -req -in sy.csr -signkey sy.key -out sy.crt
32  openssl x509 -in sy.crt -out sy.pem -outform PEM
```

if you want to add subjectAltName with IP:
```
xx  echo "subjectAltName = IP:10.36.159.75" > san.ext
xx  openssl x509 -req -in sy.csr -signkey sy.key -out sy.crt -extfile san.ext
xx  openssl x509 -req -days 365 -in sy.csr -signkey sy.key -out sy.crt -extfile san.ext 
Certificate request self-signature ok
subject=C = US, ST = TX, O = Keysight, CN = keysight.com
# openssl x509 -text -noout -in sy.crt
Certificate:
    Data:
        Version: 3 (0x2)
        Serial Number:
            1e:39:61:fa:cc:b1:d7:a5:5c:11:3f:85:65:34:bd:6b:ef:d8:ea:06
        Signature Algorithm: sha256WithRSAEncryption
        Issuer: C = US, ST = TX, O = Keysight, CN = keysight.com
        Validity
            Not Before: Mar 21 05:30:36 2025 GMT
            Not After : Mar 21 05:30:36 2026 GMT
        Subject: C = US, ST = TX, O = Keysight, CN = keysight.com
        Subject Public Key Info:
            Public Key Algorithm: rsaEncryption
                Public-Key: (2048 bit)
                Modulus:
                    00:a3:a2:40:e9:88:7d:7c:53:2d:cb:41:0a:78:33:
                    29:40:ea:11:4a:be:a7:1f:e0:86:f3:45:04:6a:17:
                    2b:d5:02:a7:d4:13:15:16:b1:f9:39:ff:02:24:98:
                    61:9e:4b:62:32:6e:25:49:49:ea:4b:86:40:c8:6a:
                    8e:0b:46:13:50:79:4d:96:46:94:88:47:73:df:30:
                    b6:6b:63:2a:30:53:bd:68:07:f9:51:8c:c7:9c:24:
                    b1:e3:f0:f0:a1:45:f9:18:ca:34:28:1a:71:be:02:
                    b2:6d:34:1c:1e:de:e5:93:f4:c6:3f:64:bc:29:7d:
                    20:5b:24:c2:f3:96:7d:02:b7:1f:31:8e:cb:2f:5b:
                    ee:9c:57:34:43:fd:1e:2e:02:29:c6:8f:2f:e8:b5:
                    a7:c7:bb:9d:20:e6:fd:46:83:18:33:54:c0:78:d7:
                    91:7c:d5:11:f6:29:3c:bb:5f:0f:7d:8b:55:b3:a7:
                    0c:9e:ab:37:10:36:da:7a:2e:74:b3:fc:75:8f:37:
                    c1:22:5e:13:f6:c1:67:ce:cd:b7:12:89:fe:e2:90:
                    11:18:bf:f0:41:85:3c:ea:f8:44:a5:79:fe:fa:05:
                    a4:fb:85:0b:fa:0d:af:c5:d8:4e:3a:a7:5d:63:bb:
                    c7:c5:2d:e5:8c:81:1e:24:e2:cd:7c:d2:e6:03:46:
                    96:0f
                Exponent: 65537 (0x10001)
        X509v3 extensions:
            X509v3 Subject Alternative Name: 
                IP Address:10.36.159.75
            X509v3 Subject Key Identifier: 
                7C:DA:2A:CB:55:11:E7:B7:8F:0A:DB:25:DA:39:97:A5:36:C5:4F:43
    Signature Algorithm: sha256WithRSAEncryption
    Signature Value:
        7e:77:6e:02:54:48:77:f2:17:e8:cf:9f:99:e7:4e:c4:97:1b:
        37:ec:98:39:a1:b6:cc:d4:48:40:1a:dd:a0:5f:9c:6f:ed:27:
        9d:aa:b5:76:54:67:95:2c:f2:a9:0e:95:99:05:98:09:2d:b8:
        57:42:d4:2f:d1:24:e0:2a:a4:64:8a:5f:ab:93:0c:ab:9e:68:
        51:21:ba:95:bd:c3:9e:48:7e:3c:8f:82:70:e6:a3:4c:2b:46:
        84:0e:10:6a:9b:f8:c9:d0:58:10:6d:28:53:b8:6e:dc:ec:7a:
        cd:f2:96:8f:38:d3:f6:7c:75:05:58:77:1a:2e:65:52:9e:2b:
        28:b8:5f:bf:32:ae:42:91:83:47:76:be:71:2e:18:79:88:dd:
        fc:2b:30:34:b8:89:9a:7e:84:88:f2:e6:97:1f:ec:8c:15:b2:
        41:8f:1d:f6:50:cc:7f:f5:29:c9:d4:67:0c:05:31:bb:f6:f3:
        d8:87:38:39:e6:db:49:6e:f0:1f:0b:94:64:44:0f:a0:90:8e:
        5e:70:ec:cc:be:2e:6a:7e:6e:5b:e6:ae:89:5b:ff:98:5c:fc:
        1d:b0:aa:de:53:58:b3:9c:26:fd:bd:e7:45:a9:54:f3:f4:2a:
        d4:a1:61:32:34:c7:40:12:e5:26:98:b5:7f:ff:b3:cf:7b:b7:
        14:ba:ad:59
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
Links to read:
1. one liner to create self signed cert: self_signed_cert[https://stackoverflow.com/a/10176685/29989976]
2. terraform provider: https://registry.terraform.io/providers/hashicorp/tls/latest
3. ansible crypto modules: https://docs.ansible.com/ansible/latest/collections/community/crypto/index.html
