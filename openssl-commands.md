## OpenSSL commands

### Chack if cert is valid
```
$ openssl x509 -noout -in <path_to_cert> -dates
notBefore=Jul 28 00:00:00 2017 GMT
notAfter=Jul 27 23:59:59 2020 GMT
```

### Check if cert and key are the same
```
$ openssl x509 -in <path_to_cert> -noout -modulus | openssl md5 ; openssl rsa -in <path_to_key> -noout -modulus |openssl md5
e3bbe9d2591ebcb12895724562837
45bf0d683ed48d8a9ab9378658726
```

### Check if wildcard or different
```
$ openssl x509 -in <path_to_cert> -noout -subject
subject= /CN=*.<domain_name>
subject= /OU=Domain Control Validated/OU=PositiveSSL/CN=<domain_name>
```

### Check DNS
```
$ openssl x509 -in <path_to_cert> -noout -text | grep DNS
                DNS:<domain_name>, DNS:www.<domain_name>
```
