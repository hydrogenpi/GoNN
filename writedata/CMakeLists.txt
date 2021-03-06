cmake_minimum_required(VERSION 3.5)
project(writedata)

set(CMAKE_CXX_STANDARD 14)

include_directories(.)
include_directories(core)
include_directories(tclap-1.2.1)
include_directories(tclap-1.2.1/include)
include_directories(tclap-1.2.1/include/tclap)

add_executable(write
        core/config.h
        core/global.cpp
        core/global.h
        core/hash.cpp
        core/hash.h
        core/md5.cpp
        core/md5.h
        core/multithread.h
        core/rand.cpp
        core/rand.h
        core/rand_helpers.h
        core/sha2.cpp
        core/sha2.h
        core/timer.cpp
        core/timer.h
        tclap-1.2.1/include/tclap/Arg.h
        tclap-1.2.1/include/tclap/ArgException.h
        tclap-1.2.1/include/tclap/ArgTraits.h
        tclap-1.2.1/include/tclap/CmdLine.h
        tclap-1.2.1/include/tclap/CmdLineInterface.h
        tclap-1.2.1/include/tclap/CmdLineOutput.h
        tclap-1.2.1/include/tclap/Constraint.h
        tclap-1.2.1/include/tclap/DocBookOutput.h
        tclap-1.2.1/include/tclap/HelpVisitor.h
        tclap-1.2.1/include/tclap/IgnoreRestVisitor.h
        tclap-1.2.1/include/tclap/MultiArg.h
        tclap-1.2.1/include/tclap/MultiSwitchArg.h
        tclap-1.2.1/include/tclap/OptionalUnlabeledTracker.h
        tclap-1.2.1/include/tclap/StandardTraits.h
        tclap-1.2.1/include/tclap/StdOutput.h
        tclap-1.2.1/include/tclap/SwitchArg.h
        tclap-1.2.1/include/tclap/UnlabeledMultiArg.h
        tclap-1.2.1/include/tclap/UnlabeledValueArg.h
        tclap-1.2.1/include/tclap/ValueArg.h
        tclap-1.2.1/include/tclap/ValuesConstraint.h
        tclap-1.2.1/include/tclap/VersionVisitor.h
        tclap-1.2.1/include/tclap/Visitor.h
        tclap-1.2.1/include/tclap/XorHandler.h
        tclap-1.2.1/include/tclap/ZshCompletionOutput.h
        datapool.cpp
        datapool.h
        fastboard.cpp
        fastboard.h
        sgf.cpp
        sgf.h
        write.cpp)

find_package(HDF5 REQUIRED COMPONENTS C CXX)

if (HDF5_FOUND)
    include_directories(${HDF5_INCLUDE_DIRS})
    target_link_libraries (write ${HDF5_LIBRARIES})
endif (HDF5_FOUND)
