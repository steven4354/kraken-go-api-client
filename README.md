Kraken GO API Client
====================

[![build status](https://img.shields.io/travis/beldur/kraken-go-api-client/master.svg)](https://travis-ci.org/beldur/kraken-go-api-client)

Updated API Client for the [Kraken](https://www.kraken.com/ "Kraken") Trading platform. Accounts for the bitcoin cash abc and bsv hard fork

Example usage:

```go
package main

import (
	"fmt"
	"log"

	"github.com/beldur/kraken-go-api-client"
)

func main() {
	api := krakenapi.New("KEY", "SECRET")
	result, err := api.Query("Ticker", map[string]string{
		"pair": "XXBTZEUR",
	})

	if err != nil {
		log.Fatal(err)
	}

	fmt.Printf("Result: %+v\n", result)

	// There are also some strongly typed methods available
	ticker, err := api.Ticker(krakenapi.XXBTZEUR)
	if err != nil {
		log.Fatal(err)
	}

	fmt.Println(ticker.XXBTZEUR.OpeningPrice)
}
```

## Source
https://github.com/beldur/kraken-go-api-client
