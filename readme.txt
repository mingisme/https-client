cat XXXX000000000001.crt ca.crt > combined.crt
openssl pkcs12 -export -in combined.crt -inkey priv_key_XXXX000000000001.pem -out XXXX000000000001.p12 -name XXXX000000000001
keytool -importkeystore -srckeystore XXXX000000000001.p12 -srcstoretype PKCS12 -srcstorepass "" -destkeystore XXXX000000000001.jks -deststorepass 123456 -destkeypass 123456 -alias XXXX000000000001 -destalias XXXX000000000001 -noprompt
