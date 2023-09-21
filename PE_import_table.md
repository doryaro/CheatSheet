## more accurate
![Picture2](https://github.com/doryaro/CheatSheet/assets/79984448/eeec04ce-5a2d-450b-bdfb-5063da6cc2b9) \
Image-Import-Descriptor == Import Directory Table \
Hint-Name Array == Import Lookup Table \
The structure and content of the import address table are identical to those of the import lookup table, until the file is bound 

## less accurate
![Picture1](https://github.com/doryaro/CheatSheet/assets/79984448/7dd1b870-98a1-4964-9063-7935c0d0a0c6) \
FirstThunk and OriginalFirstThunk first point to the same location


### Bounding:
`Binding Time (Post-compilation):` After compilation and possibly linking, a separate tool or process (like BIND.EXE) is used to bind the executable or DLL. This tool fills in the IAT with the actual memory addresses (or offsets) of the imported functions, based on the currently available versions of the imported DLLs. The Time/Date Stamps in the Import Directory Entries are also updated to match those of the bound DLLs.

`Load Time (Run-time):` When the executable or DLL is loaded into memory to be run, the OS loader checks if the file has been bound by comparing the Time/Date Stamps in the Import Directory Entries with those of the actual DLLs on disk. If they match, the loader can use the pre-filled addresses in the IAT directly, speeding up the load process. If they don't match, the loader needs to resolve the addresses again at load time, essentially reverting to the traditional loading method.
