Run This: \
`cls && del a.out.js && del a.out.wasm && echo delete seccessed && em++ -lembind main.c -s "EXIT_RUNTIME=1" -s "EXPORTED_RUNTIME_METHODS=['stringToNewUTF8','UTF8ToString','lengthBytesUTF8', 'getValue','setValue']" -s EXPORTED_FUNCTIONS="['_main']" -s DEFAULT_LIBRARY_FUNCS_TO_INCLUDE="['$stringToNewUTF8']" -Wno-format  -s WASM_BIGINT --pre-js lib.js && echo emcc succsessed && node a.out.js && echo node succsesss` 

Easy Copy:
```
cls && del a.out.js && del a.out.wasm && echo delete seccessed && em++ -lembind  beep.cpp -s "EXIT_RUNTIME=1" -s "EXPORTED_RUNTIME_METHODS=['stringToNewUTF8', 'UTF8ToString', 'lengthBytesUTF8','getValue' , 'setValue']" -s EXPORTED_FUNCTIONS="['_main']" -s DEFAULT_LIBRARY_FUNCS_TO_INCLUDE="['$stringToNewUTF8']" -Wno-format  -s WASM_BIGINT --pre-js lib.js && echo emcc succsessed && node a.out.js && echo node succsesss
```

Explain Each Parameter:
```
cls &&
del a.out.js && del a.out.wasm &&
echo delete seccessed &&
em++   (emcsripten)
-lembind  (enable binding)
 beep.cpp    (main file)
-s "EXIT_RUNTIME=1"   
-s "EXPORTED_RUNTIME_METHODS=['stringToNewUTF8','UTF8ToString', 'lengthBytesUTF8', 'getValue' ,'setValue']"
-s EXPORTED_FUNCTIONS="['_main']"
-s DEFAULT_LIBRARY_FUNCS_TO_INCLUDE="['$stringToNewUTF8']"
-Wno-format
 -s WASM_BIGINT
--pre-js lib.js
&& echo emcc succsessed &&
node a.out.js && echo node succsesss
```

### how to get value 
string - UTF32ToString(str) \
int* - Module.getValue(int_ptr, 'i32'));
### how to set value 
Module.setValue(ptr, value, 'i32');

### Other Things
`set EMMAKEN_CFLAGS=-fshort-wchar` -  wchar_t in emscripten defaults is 32 bit, but it can be changed to 16 bit by using EMMAKEN_CFLAGS=-fshort-wchar. 
