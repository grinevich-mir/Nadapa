![Nadapa](https://lh3.googleusercontent.com/CyGGnsOjYmE05xJWGtYOuFBdq45ytWSXx9NRpfOjeVs=w859-h282-no)

# Nadapa
> Sweet and simple micro-library for human readable dates parsing.

### Table of contents
* [Synopsis](#synopsis)
* [Installation](#installation)
* [Usage](#usage)
* [API Reference](#api-reference)
* [Authors](#authors)
* [License](#license)

## Synopsis

## Installation
To install Nadapa using Nuget, run the following command in the Package Manager Console:
```
PM> Install-Package Nadapa -Pre
```
Alternatively you can use following Paket command:
```
$ paket add nuget Nadapa
```

## Usage
```fsharp
open Nadapa
let parser = DateParser()

// Try to parse string using current timestamp as a starting point
let result = parser.Parse("2 days from now")

// You can specify starting point explicitly
let result = parser.Parse("yesterday", System.DateTime(1984, 1, 5))
```

## API Reference
Work in progress...

Will be finished once library API stabilize.

## Authors
* [Michal Kijowski](http://www.michalkijowski.pl)

## License
[The MIT License (MIT)](LICENSE.txt)
