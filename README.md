Default spell strategy:

1) insert jhalfs script into sorcery INSTALL file
2) stub BUILD and PRE_BUILD files


Spells that differ from default:

GLIBC
1) insert jhalfs script into BUILD file
    1a) LD_PRELOAD for installwatch interferes with glibc linking
2) split BUILD and INSTALL tasks
3) in BUILD file do DESTDIR install 
    3a) link /lib64 libs to DESTDIR
    3b) LD_CONFIG in DESTDIR /usr/lib
4) in INSTALL file cp -a DESTDIR files to INSTALL_ROOT
    4a) complete jhalfs script
5) in FINAL relink /lib64 to ../../
    5a) LD_CONFIG in INSTALL_ROOT /usr/lib
