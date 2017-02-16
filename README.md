# About

<img align="right" src="icon/hwcrypto_icon.png" width="200px" style="padding: 1em">

[hwcrypto](https://github.com/hwcrypto) is a techie umbrella name for a set of specifications, software and API-s, to enable the use of PKI based eID cards on the web for signing and authentication. It is designed to be vendor neutral and horizontally re-usable, to compete with the proliferation of proprietary, sector-specific vertical implementation silos and to avoid the resulting ["nascar problem"](https://indieweb.org/NASCAR_problem) on end-users and integrators alike.

It consists of three major parts:

* [hwcrypto.js](https://github.com/hwcrypto/hwcrypto.js) (MIT) is a JavaScript library for web developers who work with hardware backed eID cards, providing a [high-level API](https://github.com/hwcrypto/hwcrypto.js/wiki/API) that allows for the developer to focus on building things that have value to users, instead of messing with the underlying technological plumbing. The library follows [semantic versioning](http://semver.org/) and a simple [demo site](https://hwcrypto.github.io/demo/) is available.

* [hwcrypto-extension](https://github.com/hwcrypto/hwcrypto-extension) (LGPL) is a reference implementation of a modern broser extension that provides access to cryptographic smart card services of the host computer via [Native Messaging](https://developer.chrome.com/extensions/nativeMessaging). The extension is available for Chrome/Chromium, Firefox and Opera.

* [hwcrypto-native](https://github.com/hwcrypto/hwcrypto-native) (LGPL, formerly [chrome-token-signing](https://github.com/open-eid/chrome-token-signing)) is the Native Messaging counterpart of the browser extension, with installers available for Windows, macOS and Linux. It is intended to be extended, branded, repackaged and redistributed by vendors and service providers, as needed.

Being a collaboration platform for real-life integrators is another goal of this open source effort.

## Related projects
A bunch of other efforts are underway to define an API, to be implemented by browser vendors, to facilitate access to cryptographic hardware.

 * [WebCryptoAPI](https://www.w3.org/TR/WebCryptoAPI/)
   * :) [implemented by browser vendors](http://caniuse.com/#feat=cryptography)
   * :( [explicitly leaves out pre-provisioned hardware tokens](https://www.w3.org/TR/WebCryptoAPI/#scope-out-of-scope)
 * [Hardware Based Secure Services](https://rawgit.com/w3c/websec/gh-pages/hbss.html)
   * :&#124; similar API level, intended to be implemented by user agent vendors
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
   * :&#124; low level USB access, would require to implement something like [CCID](https://en.wikipedia.org/wiki/CCID_(protocol)) by a JavaScript library, to talk APDU-s to a smart card token. Possible, but not very viable. Desktop-oriented.
 * [Web Bluetooth](https://webbluetoothcg.github.io/web-bluetooth/)
   * :&#124; low level Bluetooth access, would require to implement bluetooth connectivity to a smart card reader/token, to transfer APDU-s to smart cards. Possible, but not very viable. Mobile-oriented.
   * :( no standardisation of bluetooth smart card readers
