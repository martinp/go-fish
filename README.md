fish
=======

[![Build Status](https://travis-ci.org/martinp/fish.svg)](https://travis-ci.org/martinp/fish)

Implementation of FiSH IRC encryption in Go.

Installation
============

    go get github.com/martinp/fish

Usage
=====
Basic example:

```go
package main

import (
    "github.com/martinp/fish"
    "log"
)

func main() {
    key := "secret key"
    message := "some message"

    enc, err := fish.Encrypt(key, message)
    if err != nil {
        log.Fatalf("Failed to encrypt: %s", err)
    }
    log.Printf("Encrypted: %s => %s", message, enc)

    dec, err := fish.Decrypt(key, enc)
    if err != nil {
        log.Fatalf("Failed to decrypt: %s", err)
    }
    log.Printf("Decrypted: %s => %s", enc, dec)
}
```
