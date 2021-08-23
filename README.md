# Web Browser Based Public-Key Encryption

Simple public-key cryptography using just your web browser. Use your web browser to encrypt and decrypt files using public-key cryptography, in order to exchange confidential files with others through an insecure medium such as email, instant messaging, etc.

## Usage

Download [web-browser-based-public-key-encryption.html](https://github.com/meixler/web-browser-based-public-key-encryption/blob/master/web-browser-based-public_key-encryption.html), then open the .html document in your web browser.  Or, simply point your web browser to the .html document hosted [here](https://www.meixler-tech.com/web-browser-based-public-key-encryption.html).

Then, if you are already familiar with the basics of public-key encryption (also known as asymmetric cryptography), great!  But if not, no problem.
The main menu will guide you through the process.  Start by indicating whether you sending a confidential file to someone else or you are receiving a confidential file from someone else.

## Operation and privacy

The page uses javascript running within your web browser to encrypt and decrypt files client-side, in-browser. The page makes no network connections during this process, to ensure that your files and keys do not leave your web browser during the process. This can be independently verified by reviewing the source code for the page, or by monitoring your web browser's [networking activity](https://developer.mozilla.org/en-US/docs/Tools/Network_Monitor) during operation of the page. The page can also be downloaded and run locally on your system offline. 

## Cryptography

All client-side cryptography is implemented using the [Web Crypto API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Crypto_API). 
Public/private key pairs are generated using Diffie-Hellman elliptic curve cryptography with the P-256 curve.
A shared secret between the sender and recipient is derived using ECDH key exchange.
The confidential file is then encrypted using 256-bit AES-GCM, using the shared secret as the AES key.

## Running the page offline

The web page is self-contained. The page does not require any supporting files; all javascript and css for the page is contained in the source code of the page. 
To run the page locally on your system offline, simply save the page to your system as a .html file, then open the file from your system in your web browser (optionally with networking disabled).

## Verifying the integrity of the page

The expected SHA256 checksum hash of the .html file containing the page is:

    63841a493283db2441650667c55cd18289d132668ee9bb6d83e4bcf8fccba3e6

If loading the page from a web server, you can verify that the checksum hash of the .html file downloaded from the web server matches the expected checksum hash using the [Page Integrity browser extension](https://www.pageintegrity.net/).
If running the page offline, it is recommended that you verify that the checksum hash of the .html file matches the expected checksum hash before opening the file in your web browser.

## Contributing

Pull requests are welcome.

## License

This project is licensed under the [GPL-3.0](https://www.gnu.org/licenses/gpl-3.0.en.html) open source license.

## Contact

Please [contact MTI](https://www.meixler-tech.com/contact.php) for any questions or comments concerning this project.
