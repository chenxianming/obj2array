# obj2array
Convert json object to array, map each value and index position

## How was it work?
Parsed json object and converted an array to map, u can got each value and index position in that object.

Es5 browser supported, see
``` 
./src/main.js
``` 


## Installation

``` 
npm i obj2array -s
``` 

## Usage

``` 
const obj2array = require('obj2array');

let json = {
    "testNum": 5,
    "testString": "tester",
    "testBool": true,
    "testArray": [1, 2, 3, 4],
    "testObj": {
        "num": 5,
        "string": "tester",
        "bool": true,
        "obj": {
            "a": "123",
            "b": "456",
            "c": {
                "d": "111",
                "e": 123,
                "aa": [1, 2, 3, 4]
            }
        },
        "obj2": {
            "g": 1,
            "gg": '1111'
        },
        "array": [1, 2, 3, 4]
    }
};

``` 

map

``` 
// map each children value and index position
jsonParser(json, function (val, idx) {
    console.log( 'index', idx ); // ["testObj"]["obj"]["c"]["aa"][3]
    console.log( 'value', val ); // value 4
    // ...
});

``` 

set each value
``` 
// set value to each children key
jsonParser(json, function (val, idx) {
    eval( "json"+idx + " = '"+ idx +"'" );
});

console.log( JSON.stringify( json ) );
``` 



TODO
