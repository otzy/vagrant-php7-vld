# Vagrant machine with PHP 7.0 and Vulcan Logic Disassembler

Look inside opcode, compiled from your phpcode.

## Installation

make sure you have [Vagrant](https://www.vagrantup.com/) installed.
Clone this repository and type:

`
vagrant up
`

In the end of installation process you will have virtual machine with installed php 7.0 and Vulcan Logic Disassembler (VLD) extension.

## Usage

VLD dumps PHP opcode compiled from your program to standard output.

Connect to the running VM with ```vagrant ssh``` or any other ssh client (username vagrant, password vagrant) and type command:

```
php -dvld.active=1 /src/program.php
```

It will output something like this:

```
vagrant@default:/src$ php -dvld.active=1 /src/program.php
Finding entry points
Branch analysis from position: 0
Jump found. Position 1 = -2
filename:       /src/program.php
function name:  (null)
number of ops:  9
compiled vars:  !0 = $a, !1 = $b
line     #* E I O op                           fetch          ext  return  operands
-------------------------------------------------------------------------------------
   2     0  E >   ASSIGN                                                   !0, 'a'
   3     1        ASSIGN                                                   !1, 'b'
   5     2        CONCAT                                           ~4      !0, !1
         3        CONCAT                                           ~5      ~4, '%0A'
         4        ECHO                                                     ~5
   6     5        ECHO                                                     !0
         6        ECHO                                                     !1
         7        ECHO                                                     '%0A'
         8      > RETURN                                                   1

branch: #  0; line:     2-    6; sop:     0; eop:     8; out1:  -2
path #1: 0,
ab
ab
```
## VM machine details

IP Address: 192.168.33.99

Shared folder: ./src -> /src 
