# Trigrams Finder

Simple Go program that identifies the top-n most common _trigrams_ (sequences of 3 words) in a text.

## Requirements

* Built on MacOS Sonoma 14.4.1
* Git 2.41.0
* Go 1.22

```bash
brew install go
```

## Execution Instructions

* To install external dependencies:

```bash
go mod download
```

* To run the program:

```bash
go run ./main.go -- ./texts/file1.txt ./texts/file2.txt
# or
cat ./texts/file1.txt | go run ./main.go
```

* To run all tests:

```bash
go test -v ./...
```

## Next Steps


## Known Issues & Design Flaws

* The whole application is built with object-oriented (OO) paradigms even though Go is not an OO programming language per se. I chose to build the app this way since OO is the paradigm that I've used 95% of the time in the industry. However, I would be more than willing to get constructure criticism and tips on the best way to architect Go apps.

* At the moment, input files and STDIN input are read in their entirety upon program execution. This method of parsing doesn't scale to large files and could cause buffer overflows and/or abnormally high memory usage if in a production use-case.

* Hyphens on line-endings not handled; they are considered punctuation and stripped from the original text during the sanitization stage
