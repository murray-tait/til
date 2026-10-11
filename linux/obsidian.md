The obsidian certificates configuration is specified on the obsidian server in the file `opt/couchdb/etc/local.ini`

The current locations configured in that file are follows:

```properties
cert_file = /etc/couchdb/cert/certificate.pem
key_file = /etc/couchdb/cert/private_key.pem
cacert_file = /etc/couchdb/cert/certificate_chain.pem
password = XXXXX
```

To renewal the certificate go to the AWS Console for the "Murray Tait" account as request a new certificate for `*.murraytait.net` with export enabled.

After creation you can export the cretificate form the `More actions` button. Enter the passphrase from the `local.ini` file above. The pem files can be download from the next screen into the files listed above

After the certificate files have been updated. the couchdb process needs to be re-started. Run

```bash
sudo systemctl restart couchdb
sudo systemctl status couchdb
```
