# Sample Makefile for a Go project

# Go command
GOCMD = go

# Go build command
GOBUILD = $(GOCMD) build

# Go clean command
GOCLEAN = $(GOCMD) clean

# Go get command
GOGET = $(GOCMD) get

# Target executable name
BINARY_NAME = my_go_app

# Target executable for Unix
BINARY_UNIX = $(BINARY_NAME)_unix

all: build

build:
	$(GOBUILD) -o $(BINARY_NAME) -v

test:
	$(GOCMD) test -v ./...

clean:
	$(GOCLEAN)
	rm -f $(BINARY_NAME)
	rm -f $(BINARY_UNIX)

run:
	$(GOBUILD) -o $(BINARY_NAME) -v ./...
	./$(BINARY_NAME)

deps:
	$(GOGET) github.com/markbates/goth
	$(GOGET) github.com/markbates/pop

# Build for unix systems
build-unix:
	CGO_ENABLED=0 GOOS=linux GOARCH=amd64 $(GOBUILD) -o $(BINARY_UNIX) -v

.PHONY: all build test clean run deps build-unix
