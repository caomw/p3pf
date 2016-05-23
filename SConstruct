from glob import glob

env = DefaultEnvironment(
    CCFLAGS="-O2 -Wall -std=c++11 -fdiagnostics-color=auto",
    LINKFLAGS="-Wl,--unresolved-symbols=ignore-in-shared-libs -Wl,--as-needed",
    CPPPATH=['/usr/local/include'],
    LIBPATH=['/usr/local/lib', '/usr/local/lib64'],
)

env.Append(
    CXXFLAGS='',
    CPPPATH=['.', '/usr/include/eigen3'],
    LIBS=['glog', 'gflags'],
)

srcs = glob('*.cc')
srcs.remove('p3pf_example.cc')
SharedLibrary('p3pf', srcs)
StaticLibrary('p3pf_s', srcs)
Program('p3pf_example', ['p3pf_example.cc', 'libp3pf_s.a'])
