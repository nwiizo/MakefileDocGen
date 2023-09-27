# 📋 Makefile Overview

- 💬 Comment:  Sample Makefile for a Go project

- 📝 Other: ``

- 💬 Comment:  Go command

- 🌍 Variable: `GOCMD = go`

- 📝 Other: ``

- 💬 Comment:  Go build command

- 🌍 Variable: `GOBUILD = $(GOCMD) build`

- 📝 Other: ``

- 💬 Comment:  Go clean command

- 🌍 Variable: `GOCLEAN = $(GOCMD) clean`

- 📝 Other: ``

- 💬 Comment:  Go get command

- 🌍 Variable: `GOGET = $(GOCMD) get`

- 📝 Other: ``

- 💬 Comment:  Target executable name

- 🌍 Variable: `BINARY_NAME = my_go_app`

- 📝 Other: ``

- 💬 Comment:  Target executable for Unix

- 🌍 Variable: `BINARY_UNIX = $(BINARY_NAME)_unix`

- 📝 Other: ``

- 📝 Other: `all: build`

- 📝 Other: ``

## 🎯 `build` Target
Run the following command:

```bash
make build
```

- 📝 Other: `$(GOBUILD) -o $(BINARY_NAME) -v`

- 📝 Other: ``

## 🎯 `test` Target
Run the following command:

```bash
make test
```

- 📝 Other: `$(GOCMD) test -v ./...`

- 📝 Other: ``

## 🎯 `clean` Target
Run the following command:

```bash
make clean
```

- 📝 Other: `$(GOCLEAN)`

- 📝 Other: `rm -f $(BINARY_NAME)`

- 📝 Other: `rm -f $(BINARY_UNIX)`

- 📝 Other: ``

## 🎯 `run` Target
Run the following command:

```bash
make run
```

- 📝 Other: `$(GOBUILD) -o $(BINARY_NAME) -v ./...`

- 📝 Other: `./$(BINARY_NAME)`

- 📝 Other: ``

## 🎯 `deps` Target
Run the following command:

```bash
make deps
```

- 📝 Other: `$(GOGET) github.com/markbates/goth`

- 📝 Other: `$(GOGET) github.com/markbates/pop`

- 📝 Other: ``

- 💬 Comment:  Build for unix systems

## 🎯 `build-unix` Target
Run the following command:

```bash
make build-unix
```

- 🌍 Variable: `CGO_ENABLED=0 GOOS=linux GOARCH=amd64 $(GOBUILD) -o $(BINARY_UNIX) -v`

- 📝 Other: ``

- 📝 Other: `.PHONY: all build test clean run deps build-unix`

