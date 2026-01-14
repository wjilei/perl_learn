cmake_minimum_required(VERSION 4.0)
project("perl_learn")

add_custom_target(install_deps ALL
    COMMAND cpanm --verbose -n -L extlib --mirror https://mirrors.tuna.tsinghua.edu.cn/CPAN/ --installdeps ..
    COMMAND ${CMAKE_COMMAND} -E touch install_deps
    DEPENDS ${PROJECT_SOURCE_DIR}/cpanfile
    USES_TERMINAL
)