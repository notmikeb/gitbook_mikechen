# How to use libusb to communicate with bluetooth dongle

## install libusb
zadig easy usb-driver install for windows
http://zadig.akeo.ie/

## libusb-win32 windows version
related language wrapped or binding
https://sourceforge.net/p/libusb-win32/wiki/Examples/

## libusb example
http://www.jollen.org/blog/2008/01/libusb_hello_world.html

## ctype int array

```
int ==> c_int
int array ==> declear a type, intary = c_int * 10 ==> createa intarr_obj = intary() ==> using mydll.run2(intarr_obj,10) to get the data
   risk: array protection !!!
int array pointer ==>
```

```
from ctypes import *
mydll = cdll.LoadLibrary("libusbbt1.dll")
r1 = getattr(mydll, 'myrun1')
r1.restype = c_int
r1.argtypes = [c_int]

c_int_arr = c_int *10
r2 = getattr(mydll, 'myrun2')
r2.restype = c_int
r2.argtypes = [c_int_arr, c_int]
cia = c_int_arr
r2(cia, 10)

r3 = getattr(mydll, 'myrun3')
r3.restype = c_int
r3.argtypes = [c_int, c_char]
p1 = create_string_buffer(100)
p2 = ( c_char *100 )(100)
print (sizeof(p1), repr(p1.raw))
// p1.value will be printed out the whole string data
// p1[0] is the first char p1[1] is the second char
```

http://www.jollen.org/blog/2008/01/libusb_hello_world.html


## libbusb-0.1 wrappers
https://sourceforge.net/p/libusb-win32/wiki/Examples/

## libusb 's readme
o Visual Studio:
  
- Open existing or create a new project for your application
  
- Copy libusb.h, from the include\libusb-1.0\ directory, into your project and
    
make sure that the location where the file reside appears in the 'Additional
    
Include Directories' section (Configuration Properties -> C/C++ -> General).
  
- Copy the relevant .lib file from MS32\ or MS64\ and add 'libusb-1.0.lib' to
    
your 'Additional Dependencies' (Configuration Properties -> Linker -> Input)
    
Also make sure that the directory where libusb-1.0.lib resides is added to
    
'Additional Library Directories' (Configuration Properties -> Linker
    
-> General)
  - If you use the static version of the libusb library, make sure that
    
'Runtime Library' is set to 'Multi-threaded DLL (/MD)' (Configuration
    
Properties -> C/C++ -> Code Generation).
    
NB: If your application requires /MT (Multi-threaded/libCMT), you need to
    
recompile a static libusb 1.0 library from source.
  
- Compile and run your application. If you use the DLL version of libusb-1.0,
    
remember that you need to have a copy of the DLL either in the runtime
    
directory or in system32

