ref-union-napi
=========
### Create ABI-compliant "[union][]" instances on top of Buffers
[![Build Status](https://secure.travis-ci.org/josemanuelcarretero/ref-union-napi.svg)](https://travis-ci.org/josemanuelcarretero/ref-union-napi)
[![Build Status](https://ci.appveyor.com/api/projects/status/github/josemanuelcarretero/ref-union-napi?svg=true)](https://ci.appveyor.com/project/josemanuelcarretero/ref-union-napi)



Installation
------------

Install with `npm`:

``` bash
$ npm install ref-union-napi
```


Examples
--------

``` js
var ref = require('ref-napi')
var Union = require('ref-union-napi')

// a couple typedefs
var int = ref.types.int
var float = ref.types.float
var string = ref.types.CString

// define a Union type with 3 data fields
var u_tag = new Union({
    ival: int
  , fval: float
  , sval: string
})

// the size of the union matches the largest data type in the union type
u_tag.size === string.size

// and you can create new instances of the union type
var tag = new u_tag
tag.ival = 5
```


License
-------

(The MIT License)

Copyright (c) 2012 Nathan Rajlich &lt;nathan@tootallnate.net&gt;

Permission is hereby granted, free of charge, to any person obtaining
a copy of this software and associated documentation files (the
'Software'), to deal in the Software without restriction, including
without limitation the rights to use, copy, modify, merge, publish,
distribute, sublicense, and/or sell copies of the Software, and to
permit persons to whom the Software is furnished to do so, subject to
the following conditions:

The above copyright notice and this permission notice shall be
included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED 'AS IS', WITHOUT WARRANTY OF ANY KIND,
EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF
MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT.
IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY
CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT,
TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE
SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.


[union]: http://wikipedia.org/wiki/Union_(computer_science)
