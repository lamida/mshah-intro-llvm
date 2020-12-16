# Step 1

Build hello.cpp
```
clang++ hello.cpp -o hello
```

Generate IR
```
clang++ -S -emit-llvm hello.cpp
```

-S -- only run preprocessor and compilation steps
-emit-llvm -- Use the LLVM Representation for assembler and object files

See IR
```
cat hello.ll
```

You can use lli to run IR
```
lli hello.ll
```

Convert IR to bitcode
```
llsvm-as hello.ll
```

See bitcode
```
cat hello.bc
```

We can run using lli to
```
lli hello.bc
```

Take IR or bitcode to generate assembly
```
llc hello.ll 
or
llc hello.bc
```

See assembly
```
cat hello.s
```