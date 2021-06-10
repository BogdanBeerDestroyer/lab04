# Лабораторная работа 4 Шумилишский ИУ8-22

1. CMakeLists:

```
cmake_minimum_required(VERSION 2.8)
project(travis)
include_directories(hello_world_application)
include_directories(solver_application)
```

2. Конфигурационный файл *Travis CI*:

```
language: cpp

script:
- cd solver_application
- cmake .
- make
- cd ..
- cd hello_world_application
- cmake .
- make

addons:
  apt:
    sources:
      - george-edison55-precise-backports
    packages:
      - cmake
      - cmake-data
      - mingw-w64
```

3. Дальше пушим на гитхаб и получаем значок на тревисе