accept-language-parser
======================

[![Build Status](https://travis-ci.org/texh/accept-language-parser.png?branch=master)]

Parses the accept-language header from an HTTP request and produces an array of language objects sorted by quality.

dependencies: none

~~installation:~~


~~npm install accept-language-parser~~


usage:

```
var parser = require('accept-language-parser');

var language = parser.parse('en-GB,en;q=0.8');

console.log(language);
```

Output will be:

```
[ 
  { 
    code: 'en',
    name: 'English',
    region: 'GB',
    regionName: 'United Kingdom',
    quality: 1
  },
  { 
    code: 'en',
    name: 'English',
    region: undefined,
    regionName: undefined,
    quality: 0.8
  }
]
```

Output is always sorted in quality order from highest -> lowest. as per the http spec, omitting the quality value implies 1.0.

__Known issues__
- Cannot cope with multi-part region codes, i.e. 'az-AZ-Cyrl' will be treated as 'az-AZ'

__Running tests__
```
npm install
grunt test
```
