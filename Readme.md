This is my final term project, written for the Computer Science course _"Esperienze di Programmazione"_  (ESP) at the University of Pisa.

It is a very basic implementation of a multi precision library that uses _Fast Fourier Transforms_ algorithms in order to compute factorial.

The functions `realFFT(...)` and `four1(...)` have been copy-pasted from [Numerical Recipes in C - Third edition](http://www.nr.com/), a really good book about numerical code.
I strongly suggest you to take a look at the website.

Actually the code is (not so) fine-tuned to run on system that support `uint64_t` unsigned integers. 
It won't even compile on system that doesn't offer that type via `inttypes.h`.
Also it is not guaranteed that this code will terminate if you try to compute the factorial of any number greater than 10^6.
I may work on it later during my lifetime :)

You can test the code by typing in a shell
```bash
$ cd src
$ make test
```
This will compile the code and run it, computing 1.000.000!

Otherwise you can fastly compute the factorial of any number lower or equal to 10^6 by using this main file:
```c
int main(){
  size_t n = put_your_value_here;
  m_print(Q(0,n));
  return 0;
  }
```

Compiling it with
```bash
$ gcc -std=gnu99 -O3 fact.c -o factorial -lm
```

If you have `gcc >= 4.2.3` you can also use `-march=native` in order to have a little speed up (few seconds).


If you are interested in understanding the math behind this stuff (explained in a simple fashion since i'm not a master in math) you can take a look at my [report](https://www.dropbox.com/s/n7ban1ebspb0eph/ESP.pdf).
Be aware that the report is written in italian, but if you are really curious about it you can send me a message or open an issue and i will find the time to translate it.