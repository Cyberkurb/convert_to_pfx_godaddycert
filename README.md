# Converting a Godaddy Security Certificate to PFX from IIS Download
Converting a GoDaddy Security certificate to a PFX for a Windows Machine using openssl

<ol>
  <li>Make sure you have downloaded the two keys give while creating the certificate.</li>
  <li>Once approved download the IIS Package from GoDaddy</li>
  <li>Unzip</li>
  <li>Add the key files into the same folder just for easier processing</li>
<li>Run in Command:<br>
  <b>iconv -c -f UTF8 -t ASCII generated-private.txt > key.pk8</b><br>
  <i>This will convert the key into a format will allow OpenSSL to read the key file.</i></li>
<li>Convert the pk8 into a PEM file<br>
  <b>openssl rsa -in key.pk8 -out key.pem</b></li>
<li>Then run the openssl conversion commands:<br>
<b>sudo openssl pkcs12 -export -out certificate.pfx -inkey keyjustcreatedin6.pem -in godaddycrtfileprovided.crt -certfile godaddycrtfileagain.crt</b></li>
  </ol>
<br><br>
<b>DONE!</b>
