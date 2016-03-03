# 0xb01dfacedebac1e

`0xb01dfacedebac1e` is here: https://golang.org/src/runtime/signal_amd64x.go#L53

Crashes on OS X 10.11.3.

```
$ go test -v
=== RUN   TestCrash
unexpected fault address 0xb01dfacedebac1e
fatal error: fault
[signal 0xb code=0x1 addr=0xb01dfacedebac1e pc=0xe081f]

goroutine 5 [running]:
runtime.throw(0x40e958, 0x5)
	/usr/local/Cellar/go/1.6/libexec/src/runtime/panic.go:530 +0x90 fp=0xc82004cd18 sp=0xc82004cd00
runtime.sigpanic()
	/usr/local/Cellar/go/1.6/libexec/src/runtime/sigpanic_unix.go:27 +0x2ba fp=0xc82004cd68 sp=0xc82004cd18
unicode/utf8.DecodeRuneInString(0x35393538203a4449, 0x3237323439303133, 0x410280, 0x6)
	/usr/local/Cellar/go/1.6/libexec/src/unicode/utf8/utf8.go:206 +0x3f fp=0xc82004cd70 sp=0xc82004cd68
strconv.CanBackquote(0x35393538203a4449, 0x3237323439303133, 0x3237323439303133)
	/usr/local/Cellar/go/1.6/libexec/src/strconv/quote.go:177 +0x43 fp=0xc82004cd98 sp=0xc82004cd70
fmt.(*fmt).fmt_q(0xc820060e28, 0x35393538203a4449, 0x3237323439303133)
	/usr/local/Cellar/go/1.6/libexec/src/fmt/format.go:372 +0x8b fp=0xc82004ce18 sp=0xc82004cd98
fmt.(*pp).fmtString(0xc820060dd0, 0x35393538203a4449, 0x3237323439303133, 0xc800000071)
	/usr/local/Cellar/go/1.6/libexec/src/fmt/print.go:527 +0x9e fp=0xc82004ce48 sp=0xc82004ce18
fmt.(*pp).printArg(0xc820060dd0, 0x2fefc0, 0xc820011430, 0x71, 0x0, 0x0)
	/usr/local/Cellar/go/1.6/libexec/src/fmt/print.go:797 +0xd95 fp=0xc82004cfd0 sp=0xc82004ce48
fmt.(*pp).doPrintf(0xc820060dd0, 0x40be08, 0x3, 0xc82004d420, 0x1, 0x1)
	/usr/local/Cellar/go/1.6/libexec/src/fmt/print.go:1238 +0x1dcd fp=0xc82004d358 sp=0xc82004cfd0
fmt.Sprintf(0x40be08, 0x3, 0xc82004d420, 0x1, 0x1, 0x0, 0x0)
	/usr/local/Cellar/go/1.6/libexec/src/fmt/print.go:203 +0x6f fp=0xc82004d3a8 sp=0xc82004d358
github.com/AlekSi/0xb01dfacedebac1e.Inspect(0x2fefc0, 0xc820011420, 0xc820011400, 0x0, 0x0)
	/Users/aleksi/Code/My/0xb01dfacedebac1e/src/github.com/AlekSi/0xb01dfacedebac1e/inspect.go:11 +0x3e3 fp=0xc82004d4b0 sp=0xc82004d3a8
github.com/AlekSi/0xb01dfacedebac1e.Inspect(0x2e8540, 0xc8200ba980, 0x1, 0x0, 0x0)
	/Users/aleksi/Code/My/0xb01dfacedebac1e/src/github.com/AlekSi/0xb01dfacedebac1e/inspect.go:17 +0x278 fp=0xc82004d5b8 sp=0xc82004d4b0
github.com/AlekSi/0xb01dfacedebac1e.Person.String(0xc8200ba900, 0x99, 0x0, 0xc8200ba980, 0x0, 0x0)
	/Users/aleksi/Code/My/0xb01dfacedebac1e/src/github.com/AlekSi/0xb01dfacedebac1e/person.go:17 +0x23e fp=0xc82004d670 sp=0xc82004d5b8
github.com/AlekSi/0xb01dfacedebac1e.(*Person).String(0xc8200ba948, 0x0, 0x0)
	<autogenerated>:1 +0xa2 fp=0xc82004d6a8 sp=0xc82004d670
github.com/AlekSi/0xb01dfacedebac1e/vendor/github.com/stretchr/testify/vendor/github.com/davecgh/go-spew/spew.handleMethods(0x5ef8c0, 0x1214920, 0xc820056af0, 0x37b220, 0xc8200ba948, 0x16, 0x0)
	/Users/aleksi/Code/My/0xb01dfacedebac1e/src/github.com/AlekSi/0xb01dfacedebac1e/vendor/github.com/stretchr/testify/vendor/github.com/davecgh/go-spew/spew/common.go:137 +0x6e8 fp=0xc82004d780 sp=0xc82004d6a8
github.com/AlekSi/0xb01dfacedebac1e/vendor/github.com/stretchr/testify/vendor/github.com/davecgh/go-spew/spew.(*dumpState).dump(0xc82004dad0, 0x3bde80, 0xc8200ba900, 0x99)
	/Users/aleksi/Code/My/0xb01dfacedebac1e/src/github.com/AlekSi/0xb01dfacedebac1e/vendor/github.com/stretchr/testify/vendor/github.com/davecgh/go-spew/spew/dump.go:308 +0x496 fp=0xc82004da20 sp=0xc82004d780
github.com/AlekSi/0xb01dfacedebac1e/vendor/github.com/stretchr/testify/vendor/github.com/davecgh/go-spew/spew.fdump(0x5ef8c0, 0x1214920, 0xc820056af0, 0xc82004dc78, 0x1, 0x1)
	/Users/aleksi/Code/My/0xb01dfacedebac1e/src/github.com/AlekSi/0xb01dfacedebac1e/vendor/github.com/stretchr/testify/vendor/github.com/davecgh/go-spew/spew/dump.go:467 +0x2dc fp=0xc82004db08 sp=0xc82004da20
github.com/AlekSi/0xb01dfacedebac1e/vendor/github.com/stretchr/testify/vendor/github.com/davecgh/go-spew/spew.Sdump(0xc82004dc78, 0x1, 0x1, 0x0, 0x0)
	/Users/aleksi/Code/My/0xb01dfacedebac1e/src/github.com/AlekSi/0xb01dfacedebac1e/vendor/github.com/stretchr/testify/vendor/github.com/davecgh/go-spew/spew/dump.go:482 +0xaa fp=0xc82004db88 sp=0xc82004db08
github.com/AlekSi/0xb01dfacedebac1e/vendor/github.com/stretchr/testify/assert.diff(0x3bde80, 0xc8200ba900, 0x3bde80, 0xc8200ba920, 0x0, 0x0)
	/Users/aleksi/Code/My/0xb01dfacedebac1e/src/github.com/AlekSi/0xb01dfacedebac1e/vendor/github.com/stretchr/testify/assert/assertions.go:990 +0x1de fp=0xc82004dd80 sp=0xc82004db88
github.com/AlekSi/0xb01dfacedebac1e/vendor/github.com/stretchr/testify/assert.Equal(0x12148f8, 0xc820080090, 0x3bde80, 0xc8200ba900, 0x3bde80, 0xc8200ba920, 0x0, 0x0, 0x0, 0x0)
	/Users/aleksi/Code/My/0xb01dfacedebac1e/src/github.com/AlekSi/0xb01dfacedebac1e/vendor/github.com/stretchr/testify/assert/assertions.go:264 +0x9d fp=0xc82004de50 sp=0xc82004dd80
github.com/AlekSi/0xb01dfacedebac1e.TestCrash(0xc820080090)
	/Users/aleksi/Code/My/0xb01dfacedebac1e/src/github.com/AlekSi/0xb01dfacedebac1e/person_test.go:13 +0x1e0 fp=0xc82004df58 sp=0xc82004de50
testing.tRunner(0xc820080090, 0x5eedf0)
	/usr/local/Cellar/go/1.6/libexec/src/testing/testing.go:473 +0x98 fp=0xc82004df90 sp=0xc82004df58
runtime.goexit()
	/usr/local/Cellar/go/1.6/libexec/src/runtime/asm_amd64.s:1998 +0x1 fp=0xc82004df98 sp=0xc82004df90
created by testing.RunTests
	/usr/local/Cellar/go/1.6/libexec/src/testing/testing.go:582 +0x892

goroutine 1 [chan receive]:
testing.RunTests(0x4b7280, 0x5eedf0, 0x1, 0x1, 0x5f7a01)
	/usr/local/Cellar/go/1.6/libexec/src/testing/testing.go:583 +0x8d2
testing.(*M).Run(0xc82004bef8, 0x0)
	/usr/local/Cellar/go/1.6/libexec/src/testing/testing.go:515 +0x81
main.main()
	github.com/AlekSi/0xb01dfacedebac1e/_test/_testmain.go:54 +0x117

goroutine 17 [syscall, locked to thread]:
runtime.goexit()
	/usr/local/Cellar/go/1.6/libexec/src/runtime/asm_amd64.s:1998 +0x1
exit status 2
FAIL	github.com/AlekSi/0xb01dfacedebac1e	0.013s
```
