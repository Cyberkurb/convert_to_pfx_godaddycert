# Converting a Godaddy Security Certificate to PFX form IIS Download
Converting a GoDaddy Security certificate to a PFX for a Windows Machine using openssl


1. Make sure you have downloaded the two keys give while creating the certificate.
2. Once approved download the IIS Package from GoDaddy
3. Unzip
4. Add the key files into the same folder just for easier processing
5. Run in Command:<br>
  <b>iconv -c -f UTF8 -t ASCII generated-private.txt > key.pk8</b><br>
  <br>
  This will convert the key into a format will allow OpenSSL to read the key file.<br>
6. Convert the pk8 into a PEM file<br>
  <b>openssl rsa -in key.pk8 -out key.pem</b>
7. Then run the openssl conversion commands:<br>
<b>sudo openssl pkcs12 -export -out certificate.pfx -inkey keyjustcreatedin6.pem -in godaddycrtfileprovided.crt -certfile godaddycrtfileagain.crt</b>
<br><br>
<b>DONE!</b>
