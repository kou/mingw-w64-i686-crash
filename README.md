# MinGW-w64 i686 g++.exe is crashed

## Version

```console
$ g++ --version
g++.exe (Rev2, Built by MSYS2 project) 7.3.0
Copyright (C) 2017 Free Software Foundation, Inc.
This is free software; see the source for copying conditions.  There is NO
warranty; not even for MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.
```

## Message

`crash.cc` is included in this repository. It's pre-processed C++ code. The original code is https://github.com/apache/arrow/blob/apache-arrow-0.11.0/cpp/src/arrow/util/memory.h .

```console
$ g++ -c crash.cc
In file included from C:/msys64/home/kou/MINGW-packages/mingw-w64-arrow/src/apache-arrow-0.11.0/cpp/src/arrow/io/memory.cc:29:0:
C:/msys64/home/kou/MINGW-packages/mingw-w64-arrow/src/apache-arrow-0.11.0/cpp/src/arrow/util/memory.h: In substitution of 'template<class Function, class ... Args, class Result> std::future<Result> arrow::internal::ThreadPool::Submit(Function&&, Args&& ...) [with Function = <missing>; Args = <missing>; Result = <missing>]':
C:/msys64/home/kou/MINGW-packages/mingw-w64-arrow/src/apache-arrow-0.11.0/cpp/src/arrow/util/memory.h:63:72:   required from here
C:/msys64/home/kou/MINGW-packages/mingw-w64-arrow/src/apache-arrow-0.11.0/cpp/src/arrow/util/memory.h:63:72: internal compiler error: Segmentation fault
                                       left + i * chunk_size, chunk_size));
                                                                        ^

C:/msys64/home/kou/MINGW-packages/mingw-w64-arrow/src/apache-arrow-0.11.0/cpp/src/arrow/util/memory.h:63:72: internal compiler error: Aborted
g++.exe: internal compiler error: Aborted (program cc1plus)
Please submit a full bug report,
with preprocessed source if appropriate.
See <https://sourceforge.net/projects/msys2> for instructions.
```
