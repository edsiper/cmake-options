# CMake: override subdirectory options

This is a working example to demonstrate how you can override your subdirectory options from a parent project using a simple macro, more info at:

[http://edsiper.linuxchile.cl/blog/2016/01/08/cmake-override…ectory-options/](http://edsiper.linuxchile.cl/blog/2016/01/08/cmake-override…ectory-options/)

## Getting started

```bash
$ cd project_B/build/
$ cmake ../
```

Once you run the __cmake__ command, you will see that __project_B__ (parent), override the options of __project_A__, the terminal output should looks like this:

```bash
project_B/build/] $ cmake ../
-- The C compiler identification is GNU 5.2.1
-- The CXX compiler identification is GNU 5.2.1
-- Check for working C compiler: /usr/bin/cc
-- Check for working C compiler: /usr/bin/cc -- works
-- Detecting C compiler ABI info
-- Detecting C compiler ABI info - done
-- Detecting C compile features
-- Detecting C compile features - done
-- Check for working CXX compiler: /usr/bin/c++
-- Check for working CXX compiler: /usr/bin/c++ -- works
-- Detecting CXX compiler ABI info
-- Detecting CXX compiler ABI info - done
-- Detecting CXX compile features
-- Detecting CXX compile features - done
-- >>>>>>>> Project_A: Feature AA: OFF <<<<<<<<
-- >>>>>>>> Project_A: Feature BB: ON <<<<<<<<
-- Configuring done
-- Generating done
-- Build files have been written to: /home/edsiper/coding/cmake-options/project_B/build
```

The macro used to override the options is:

```cmake
macro(SET_OPTION option value)
  set(${option} ${value} CACHE "" INTERNAL FORCE)
endmacro()
```

If this repo did some help to solve your issue, please starred it!

Eduardo Silva <eduardo@monkey.io>