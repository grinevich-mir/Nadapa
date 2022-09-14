![Nadapa](https://lh3.googleusercontent.com/CyGGnsOjYmE05xJWGtYOuFBdq45ytWSXx9NRpfOjeVs=w859-h282-no)

# Nadapa
> Simple micro-library for human readable dates parsing.

### Table of contents
* [Synopsis](#synopsis)
* [Installation](#installation)
* [Usage](#usage)
* [Authors](#authors)
* [License](#license)

## Synopsis
Nadapa is a small utility library that can be used for extracting DateTime objects from natural language text.

It is written in F# with the use of [FParsec](http://www.quanttec.com/fparsec/) parser combinator library.
## Installation
To install Nadapa using Nuget, run the following command in the Package Manager Console:
```
PM> Install-Package Nadapa 
```
Alternatively you can use the following Paket command:
```
$ paket add nuget Nadapa
```

## Usage
```fsharp
open Nadapa
let parser = DateParser()

// Try to parse string using current timestamp as a starting point
let basicCase = parser.TryParse("2 days from now")
// basicCase = Some (System.DateTime(2015,8,10))
// assuming that the code was executed on 8 Aug 2015

// Optionally you can specify starting point
let withAnchor = parser.TryParse("yesterday", System.DateTime(1984, 1, 5))
// withAnchor = Some (System.DateTime(1984, 1, 4))

// You can also make parser case sensitive
let csParser = DateParser(caseSensitive=true)

let good = csParser.TryParse("yesterday", System.DateTime(1984, 1, 5))
// good = Some (System.DateTime(1984, 1, 4))
let bad = csParser.TryParse("yEstErDay", System.DateTime(1984, 1, 5))
// bad = None

// Additionally you can modify parser config by loading modified YAML file
let config = ParserConfig()
config.Load("path/to/config.yaml")
let parserWithConfig = DateParser(config)
```

## License
[The MIT License (MIT)](LICENSE.txt)
