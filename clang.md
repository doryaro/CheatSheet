# Clang (frontend of llvm) Cheatsheet

------------
### Tutorials

- [Clang-tutorial](https://github.com/loarabia/Clang-tutorial) good examples that not exist on the internet
- [AST matches and clang-query refactoring](https://eli.thegreenplace.net/2014/07/29/ast-matchers-and-clang-refactoring-tools)

### Build

- [building Clang on Windows using Visual Studio](https://clang.llvm.org/get_started.html)
- `properties -> linker` to use in visual studio
- `properties -> c++ -> addithinal include libaries` to use in visual studio
- `properties -> linker -> input-> addithinal include libaries` to use in visual studio
- `check which LNK2001 is not working check where in the code is belong and then check the file.lib and import that as well
- `` to use in visual studio
- `` to use in visual studio
- 


#### components

- **Preprocessor (PP)**: each .cpp file given to clang's compiler is being processed first.  The output of the PP is a translation unit, which is the input file where all directives were handled, e.g., replaced, expanded, etc. The translation unit include all the relevant code and information for a successful compilation. 
- **Lexer**: The component which extracts tokens (i.e., strings, key words, names, parentheses, brackets, etc.) from the translation unit's source. Each token is a valid word, or element, which is part of the language's syntax.
- **Parser**: The parser takes a bunch of the tokens created by the lexer and build expressions out of them. At this part, the Abstract syntax tree (AST) is being constructed. The AST is just a structured tree representation of the source code, which can be used for different purposes such as creating a symbol table, performing type checking and finally generating code. Each node in the tree represent some element in the source code. 
- **Sema**: The component that checks the semantic validity of the created expressions which are part the constructed AST. For example, "int a = "abc;" is of course not a valid expression.

### Docs

- [docs](https://clang.llvm.org/docs/)
- [docs](https://clang.llvm.org/docs/)
- [understanding-the-clang-ast](https://jonasdevlieghere.com/understanding-the-clang-ast/)

### Commands

- `clang-check -ast-dump -ast-dump-filter=func1 Source.cpp` dump AST and only one function
- `clang -fsyntax-only -Xclang -ast-view min.c` to see the dot files go to [GraphvizOnline](https://dreampuf.github.io/GraphvizOnline/)
- `clang -fsyntax-only -Xclang -ast-view min.c`
- `clang -fsyntax-only -Xclang -ast-view min.c`
- `clang -fsyntax-only -Xclang -ast-view min.c`
- `    "command": "\"C:/Users/toorr/Downloads/llvm-project/build/Release/bin/clang++.exe\" -x c++ \"C:/Users/toorr/Desktop/PlayGround/testapp/ConsoleApplication1/Cdor.cpp\" -std=c++14 -Wall -fms-compatibility-version=19.10 -Wmicrosoft -Wno-invalid-token-paste -Wno-unknown-pragmas -Wno-unused-value -fsyntax-only \"-DUNICODE\" \"-D_UNICODE\" \"-D_MT\" \"-D_DLL\" \"-D_AFXDLL\" \"-D_DEBUG\" \"-D_CONSOLE\" \"-D_DEBUG_FUNCTIONAL_MACHINERY\" -isystem\"C:/Program Files (x86)/Microsoft Visual Studio/2019/BuildTools/VC/Tools/MSVC/14.29.30133/include\" -isystem\"C:/Program Files (x86)/Microsoft Visual Studio/2019/BuildTools/VC/Tools/MSVC/14.29.30133/atlmfc/include\" -isystem\"C:/Program Files (x86)/Microsoft Visual Studio/2019/BuildTools/VC/Auxiliary/VS/include\" -isystem\"C:/Program Files (x86)/Windows Kits/10/Include/10.0.20348.0/ucrt\" -isystem\"C:/Program Files (x86)/Windows Kits/10/Include/10.0.20348.0/um\" -isystem\"C:/Program Files (x86)/Windows Kits/10/Include/10.0.20348.0/shared\" -isystem\"C:/Program Files (x86)/Windows Kits/10/Include/10.0.20348.0/winrt\" -isystem\"C:/Program Files (x86)/Windows Kits/10/Include/10.0.20348.0/cppwinrt\"",	`

### clang

- `clang -Xclang -### hello.c` show clang config
- `clang -Xclang -ast-dump hello.c` print the Abstract Syntax Tree (AST)
- `clang -Xclang -ast-dump -std=<version> hello.c` print the Abstract Syntax Tree (AST) according to version [implementation status for all c++ version](https://clang.llvm.org/cxx_status.html)
    - `-std=c++11` for C++ 11
    - `-std=c++14` for C++ 14  (use `-std=c++1y` in Clang 3.4 and earlier).
    - `-std=c++17` for C++ 17  (use `-std=c++1z` in Clang 4 and earlier).
    - `-std=c++20` for C++ 20  (use `-std=c++2a` in Clang 9 and earlier).
    - `-std=c++2b` for C++ 23  (use `-std=c++1z` in Clang 4 and earlier).
- 
- 


#### Classes 

- `FunctionDecl` Represents a function declaration or definition.
- `CompoundStmt` This represents a group of statements like { stmt stmt }.
- `DeclStmt` Adaptor class for mixing declarations with statements and expressions..
- `VarDecl` Represents a variable declaration or definition.
- `IntegerLiteral` explantion.
- `command` explantion.
- `command` explantion.
- `command` explantion.
- `command` explantion.
- `command` explantion.


#### Links

- [Clang docs](https://clang.llvm.org/doxygen/).
- `command` explantion.
- `command` explantion.


An AST node represents declarations, statements, and types. Hence, there are three
core classes to represent AST nodes: Decl, Stmt, and Type. Each C or C++ language 
construct is represented in Clang by a C++ class, which must inherit from one of 
these core classes. The following diagram illustrates part of the class hierarchy. For 
example, the IfStmt class (representing a complete if statement body) directly 
inherits from the Stmt class. On the other hand, the FunctionDecl and VarDecl
classes—used to hold function and variable declarations or definitions—inherits 
from more than one class and only reaches Decl indirectl

#### category

- `command` explantion.
- `command` explantion.
- `command` explantion.
#### category

- `command` explantion.
- `command` explantion.
- `command` explantion.
#### category

- `command` explantion.
- `command` explantion.
- `command` explantion.
#### category

- `command` explantion.
- `command` explantion.
- `command` explantion.

#### category


- `command` explantion.
- `command` explantion.
- `command` explantion.

#### category


- `command` explantion.
- `command` explantion.
- `command` explantion.

#### category


- `command` explantion.
- `command` explantion.
- `command` explantion.

#### category


-  []() explantion.
-  []() explantion.
-  []() explantion.


#### category


- `command` explantion.
- `command` explantion.
- `command` explantion.



#### category


1. `command` explantion.
2. `command` explantion.
3. `command` explantion.
4. `command` explantion.
5. `command` explantion.




#### category


1. `command` explantion.
2. `command` explantion.
3. `command` explantion.
4. `command` explantion.
5. `command` explantion.
