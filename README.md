# About

[hwcrypto.js](https://github.com/hwcrypto/hwcrypto.js) is a JavaScript library for web developers who work with hardware backed eID cards, alleviating the imminent ["nascar problem"](https://indieweb.org/NASCAR_problem) from proliferation of vendors and underlying platforms and technologies.

It provides a vendor-neutral, high-level API, with a selection of shims on top of the zoo of plugins, extensions, services and API-s, allowing the developer to focus on building things that have value to users, instead of messing with technological plumbing.

Being a collaboration platform for real-life integrators is another goal of this open source, MIT licensed effort.

## History
TBD, see https://github.com/hwcrypto/hwcrypto.js/wiki and https://github.com/open-eid/chrome-token-signing/wiki


## Related projects
A bunch of efforts are underway to define an API, to be implemented by browser vendors, to facilitate access to cryptographic hardware.
 * [WebCryptoAPI](https://www.w3.org/TR/WebCryptoAPI/)
   * :) [implemented by browser vendors](http://caniuse.com/#feat=cryptography)
   * :( [explicitly leaves out pre-provisioned hardware tokens](https://www.w3.org/TR/WebCryptoAPI/#scope-out-of-scope)
 * [Hardware Based Secure Services](https://rawgit.com/w3c/websec/gh-pages/hbss.html)
   * :| similar API level, intended to be implemented by user agent vendors
   * :( no working sample code
   * :( [no interest from browser vendors](https://poulpita.com/2016/11/28/is-hardware-based-secure-web-services-a-lost-quest-no-well/)
 * [Web API For Accessing Secure Element](http://globalplatform.github.io/WebApis-for-SE/doc/)
   * :( low level, ISO7816-4 based APDU interface, not unlike [PC/SC](https://en.wikipedia.org/wiki/PC/SC)
   * :( no working sample code
   * :( no known intention from browser vendors to implement (more likely to happen on mobiles)
 * [FIDO U2F / WebAuthn](https://www.w3.org/TR/webauthn/)
   * :) [being implemented](http://caniuse.com/#feat=u2f)
   * :( only authentication, and scoped credentials

Some other initiatives with working code and standardisation efforst exist, that allow to bridge the gap between a website and a hardware token, by exposing a common "transport mechanism" to JavaScript:

 * [WebUSB](https://wicg.github.io/webusb/)
   * :| low level USB access, would require to implement something like [CCID](https://en.wikipedia.org/wiki/CCID_(protocol)) by a JavaScript library, to talk APDU-s to a smart card token. Possible, but not very viable. Desktop-oriented.
 * [Web Bluetooth](https://webbluetoothcg.github.io/web-bluetooth/)
   * :| low level Bluetooth access, would require to implement bluetooth connectivity to a smart card reader/token, to transfer APDU-s to smart cards. Possible, but not very viable. Mobile-oriented.
   * :( no standardisation of bluetooth smart card readers
