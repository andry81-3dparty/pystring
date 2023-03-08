* README_EN.txt
* 2023.03.08
* pystring

1. DESCRIPTION
2. SOURCES
3. PATCHES
4. DEPENDENCIES
5. EXTERNALS
6. AUTHOR

-------------------------------------------------------------------------------
1. DESCRIPTION
-------------------------------------------------------------------------------
`pystring` library fork

-------------------------------------------------------------------------------
2. SOURCES
-------------------------------------------------------------------------------
https://github.com/imageworks/pystring

-------------------------------------------------------------------------------
3. PATCHES
-------------------------------------------------------------------------------
The original library patched to fix these issues:

1. Use std::basic_string instead of single std::string (unable to use functions
   in unicode contexts because of that reason).
2. Compilation warnings in the Microsoft Visual Studio 2015 Update 3.

-------------------------------------------------------------------------------
4. DEPENDENCIES
-------------------------------------------------------------------------------
`CMakeLists.txt`:

* `tacklelib`

-------------------------------------------------------------------------------
5. EXTERNALS
-------------------------------------------------------------------------------
To checkout externals you must use the
[vcstool](https://github.com/dirk-thomas/vcstool) python module.

NOTE:
  To install the module from the git repository:

  >
  python -m pip install git+https://github.com/dirk-thomas/vcstool

-------------------------------------------------------------------------------
6. AUTHOR
-------------------------------------------------------------------------------
Andrey Dibrov (andry at inbox dot ru)
