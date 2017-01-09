# Create a shared library for OSX

Our simple library code:

* hello.c
* hello.h

Our test client code which uses the library :

* main.c

The process is as followed:

1. `gcc -c -Wall -fpic hello.c` generates a object file `hello.o`
2. `gcc -shared -o libhello.dylib hello.o` creates the shared library
3. `mv libhello.dylib /usr/local/lib` moves the libaray to one of the standard dynamic load paths.
4. `gcc client.c -o /tmp/hello_client -lhello` compiles the client code.

Then you can run the client code by `/tmp/hello_client` and it will print out "hello form C".

# Links

* http://www.cprogramming.com/tutorial/shared-libraries-linux-gcc.html
* https://developer.apple.com/library/content/documentation/DeveloperTools/Conceptual/DynamicLibraries/100-Articles/UsingDynamicLibraries.html


