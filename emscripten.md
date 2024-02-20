`set EMMAKEN_CFLAGS=-fshort-wchar` - I understand wchar_t in emscripten defaults to 32 bit, but it can be changed to 16 bit by using EMMAKEN_CFLAGS=-fshort-wchar. 

```
cls &&
del a.out.js && del a.out.wasm &&
echo delete seccessed &&
em++   (emcsripten)
-lembind  (enable binding)
 beep.cpp    (main file)
-s "EXIT_RUNTIME=1"   
-s "EXPORTED_RUNTIME_METHODS=['stringToNewUTF8','lengthBytesUTF8', 'setValue']"
-s EXPORTED_FUNCTIONS="['_main']"
-s DEFAULT_LIBRARY_FUNCS_TO_INCLUDE="['$stringToNewUTF8']"
-Wno-format
 -s WASM_BIGINT
--pre-js lib.js
&& echo emcc succsessed &&
node a.out.js && echo node succsesss
```
`cls && del a.out.js && del a.out.wasm && echo delete seccessed && em++ -lembind  beep.cpp -s "EXIT_RUNTIME=1" -s "EXPORTED_RUNTIME_METHODS=['stringToNewUTF8','lengthBytesUTF8', 'setValue']" -s EXPORTED_FUNCTIONS="['_main']" -s DEFAULT_LIBRARY_FUNCS_TO_INCLUDE="['$stringToNewUTF8']" -Wno-format  -s WASM_BIGINT --pre-js lib.js && echo emcc succsessed && node a.out.js && echo node succsesss `
