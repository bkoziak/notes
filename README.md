# notes

#Certyfikaty

Listuje wpisy w keystorze (domyślne hasło to 'changeit')

  keytool -list -keystore {path}/keystore.jks
  
  $ keytool -genkey -keystore flashphone.jks -alias flashphone -dname "CN=flashphone,OU=flashphone" -keyalg "RSA" -sigalg "SHA1withRSA" -keysize 2048 -validity 731
  
export klucza
  $ keytool -export -keystore flashphone.jks -alias flashphone -file flashphone.crt

konwersja klucza
  $ openssl x509 -in flashphone.crt -inform der -out flashphone.pem -outform pem

weryfikacja klucza
  $openssl x509 -in osk_ft_x509.pem -text -noout

import
  openssl x509 -outform der -in certificate.pem -out certificate.der
  keytool -import -alias your-alias -keystore cacerts -file certificate.der
