# humanparser

[![Build Status](https://travis-ci.org/compwright/humanparser.svg?branch=master)](https://travis-ci.org/compwright/humanparser)

Parse a human name string into salutation, first name, middle name, last name, suffix.

## Installation

```bash
$ npm install @compwright/humanparser --save
```

## Usage

### Parse human name    

```javascript
const human = require('@compwright/humanparser');
const fullName = 'Mr. William R. Hearst, III';
const attrs = human.parseName(fullName);

console.log(attrs);
```

Produces the following output:
    
    { 
        saluation: 'Mr.',
        firstName: 'William',
        suffix: 'III',
        lastName: 'Hearst',
        middleName: 'R.',
        fullName: 'Mr. William R. Hearst, III'
    }
      
### Get fullest name in string

```javascript
const human = require('@compwright/humanparser');
const name = 'John & Peggy Sue';
const fullName = human.getFullestName(name);
```

Produces the following output:

    {
        fullName: 'Peggy Sue'
    }
      
### Parse address

```javascript
const human = require('@compwright/humanparser');
const address = '123 Happy Street, Honolulu, HI  65780';
const parsed = human.parseAddress(address);
```

Produces the following output:

    {
        address: '123 Happy Street',
        city: 'Honolulu',
        state: 'HI',
        zip: '65780',
        fullAddress: '123 Happy Street, Honolulu, HI  65780'
    }

## License

MIT License
