.PHONY: build clean willUseGo 
run: willUseGo
	./willUseGo
build: go.mod 
	@go build -o usedByC.o -buildmode=c-shared usedByC.go
go.mod:
	go mod init exam/ple
	go mod tidy
usedByC.o:build
	@echo "need go build to create usedByC.o"	
willUseGo:usedByC.o
	gcc -o $@ willUseGo.c ./usedByC.o
clean:
	rm -rf go.* willUseGo *.o *.h
