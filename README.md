## x509.js

parsing of x509 certificates and keys in javascript (via emscripten)

### Installation
```
npm install x509.js
```

### Browser use
TODO (accepting pull requests)

### Usage

```js
var fs = require('fs');
var x509 = require('x509.js');
var parsedData = x509.parseCert(fs.readFileSync('domain.crt')); // use fs.readFile in actual code
/* parsedData looks like
{ publicModulus: 'B27DB7A94351A4E542245917C579C7DFC8A703CEDE18D5CC0A40DB41B2B17B79AFF559F9B952824B78D8D41475060D5D7E44D47E360AD03083C8222EAC3AD9A1241CB4376855CC99C324B4253EFFFBE6DDC303E5284A44AC7163D6B3950D406085172492602BBF68D6F4C2A7AD80A10691E5D11CCA7EA3911EECDF98F9946FAB35193D56D7129ED8AA1545FA1DCA2422F1DF7E997A616B406D98A07E6EB0EEC125B7B6E00FE8E5879DE617DBF61296D068BB1529A31A1CB95B81E1B83B0C3E0305A7A5F5260451E29364F7444F785B1AA49540980CDB2F34B4D0C1ADF874323425B508D44C4B0BB968D3E7C98029CB7F75376AFB146EEA3EF2799254B85DCE47',
        publicExponent: '010001',
        subject: 
         { commonName: 'www.acaline.com',
           organizationalUnitName: 'Domain Control Validated' },
        issuer: 
         { commonName: 'Go Daddy Secure Certification Authority',
           countryName: 'US',
           localityName: 'Scottsdale',
           organizationName: 'GoDaddy.com, Inc.',
           organizationalUnitName: 'http://certificates.godaddy.com/repository',
           serialNumber: '07969287',
           stateOrProvinceName: 'Arizona' },
        serial: '27ACAE30B9F323',
        notBefore: 'Apr 26 14:51:17 2013 GMT',
        notAfter: 'Apr 26 14:51:17 2014 GMT',
        altNames: [ 'www.acaline.com', 'acaline.com' ],
        ocspList: [ 'http://ocsp.godaddy.com/' ] });
  }
*/
var parsedKey = x509.parseKey(fs.readFileSync('domain.key')); // use fs.readFile in actual code
/* parsedKey looks like
{ 
  publicExponent: '010001',
  publicModulus: 'E6C5BC84CF79CC6EDB1A1F7ED0CE39EFA413395C055886605AB66E2DE1C0B31C8D1C12F436FD222C167DDE44928F72F72DFE9E5420FD0595836D47A163CC59A1C444AEE8C0E9CE3B8A53D2FCD569A4ADA38D537E3542C81F887538E6B6A953D82ADC6150B88B09E961E451D721895002A0628A4F7387E3D99ED78E05AC94F5640698D833BC518CEF5A2192B2F58FB79BD6F1F499FA603C9A3DB4AD8EF6EAB4071D25CBC2A41F9CC8BA1D47B9135AAE53ED479B00F09C40B4607274FEA4585E61D541DB297336F373DF1DB569AD41D17D1A04EFAED7A9938F651C71AA99C0C4D4BFB6347CCE90469B12A23F04BDD32DB4066DB22E757D57272BAD6485A9F61D1D',
}
*/
```
