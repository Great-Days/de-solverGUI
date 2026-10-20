# de-solver

Phase Line Diagram generator for Differential Equations

## Stack

- C++(20/23) & CMake

- Frontend lib TBD

- Could add in python

## Architecture

### Root

```txt
  ~/path/to/de-solver
    components
    CMakeLists.txt
   󰂺 README.md  << YOU ARE HERE
```

- `components` - contains client and engine source code and header files

- `CMakeLists.txt` - global project config file. Search it up on google if unsure

- `README.md` - global project README, does not dive into details

### Components

```txt
 components
│  client
│ │  include
│ │  src
│ └  CMakeLists.txt
│ └ 󰂺 README.md    
│  engine
│ │  include
│ │  src
│ └  CMakeLists.txt
│ └ 󰂺 README.md    
└  CMakeLists.txt    
```

- `include` - header files

- `src` - source files

- root `CMakeLists.txt` - boilerplate, includes `engine` and `client`

- `engine/ and client/ CMakeLists.txt` - per component build file

- `engine/ and client/ README.md` - per component README. More detailed
