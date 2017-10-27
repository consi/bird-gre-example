bird-gre-example
================

A combination of Vagrant and ansible, that shows how to simply create kind of overlay network 
from scratch using GRE tunnels and BGP protocol.

Usage
-----
Just clone this repository and invoke command:
```
vagrant up
```

Environment in default mode will set up 5 VMs connected by GRE tunnels to demonstrate how 
bird works with BGP configuration. To access vm, type:
```
vagrant ssh birdN
```
where N is number of VM (1-5 in default configuration)

License
-------
The MIT License (MIT)

Copyright (c) 2013 Thomas Park

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.