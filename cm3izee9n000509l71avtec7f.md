---
title: "When to use crypto/rand and where to use math/rand?"
datePublished: Fri Nov 15 2024 16:56:46 GMT+0000 (Coordinated Universal Time)
cuid: cm3izee9n000509l71avtec7f
slug: when-to-use-cryptorand-and-where-to-use-mathrand
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/Oj7nnln5k3k/upload/275a35e691e08b0619b50045c6a3a6cc.jpeg
tags: golang, coding, random, crypto, cryptocurrency

---

In coding, randomness is not as random as you think. There are two distinct paths to generating randomness: `math/rand` and `crypto/rand`. Both have their merits, but they serve very different purposes.

### math/rand

If `math/rand` were a person, it would be that friend who always suggests flipping a coin when no one can decide where to eat. It's fast, reliable for non-critical decisions, but you wouldn’t want to trust it with your credit card number. It’s pseudo-random, meaning that it generates sequences of numbers that only *look* random but are completely predictable if you know the starting seed. They are more like an hash if you have ever used those, but still random *enough.*

```go
package main

import (
	"fmt"
	"math/rand"
	"time"
)

func main() {
	rand.Seed(time.Now().UnixNano()) // seed it to get different results
	fmt.Println(rand.Intn(100))      // prints a random number between 0 and 99
}
```

Here, `math/rand` gives you a number between 0 and 99. It’s great for simple tasks like shuffling a playlist or deciding who gets the last slice of pizza. But under the hood, it’s deterministic. Give it the same seed, and it’ll spit out the same sequence every time. So, if you’re thinking about using it for anything security-related…don’t.

### crypto/rand

Enter `crypto/rand`, the guy in a black suit who checks IDs at the door and asks if you have clearance. `crypto/rand` taps into your system’s entropy sources, which means it gathers real-world randomness—things like mouse movements or hard drive noise—to generate numbers that are cryptographically secure.

```go
package main

import (
	"crypto/rand"
	"fmt"
	"math/big"
)

func main() {
	n, err := rand.Int(rand.Reader, big.NewInt(100))
	if err != nil {
		fmt.Println("Error:", err)
		return
	}
	fmt.Println(n) // prints a cryptographically secure random number between 0 and 99
}
```

In this example, `crypto/rand` takes its time to produce a truly random number. It’s not as fast as `math/rand`, but if you need unpredictability that a hacker can’t reverse-engineer, this is your go-to. It’s perfect for generating passwords, tokens, or anything where security matters.

### When to Use Which?

Use `math/rand` when:

* You need random numbers for non-security purposes (e.g., simulations, random animations).
    
* Speed is more important than security.
    
* Predictability isn’t a concern.
    

Use `crypto/rand` when:

* Security is crucial (e.g., generating encryption keys, passwords).
    
* You need true randomness that can’t be guessed or predicted.
    
* You can afford a little extra time for the sake of security.  
    

In the end, if you’re thinking of letting `math/rand` handle your passwords… just don’t.