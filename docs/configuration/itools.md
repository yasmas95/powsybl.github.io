---
title: itools.conf
layout: default
---

The `POWSYBL_HOME/etc/itools.conf` file is a [properties](https://en.wikipedia.org/wiki/.properties) file that contains
system properties to configure the framework. It is generated by the [itools-packager](../install/itools-packager.html)
maven plugin.

# Properties

## java_xmx
The `java_xmx` property is an optional property that defines the amout of the Java Heap memory. The default value is 8 Gb.

## mpi_hosts
The `mpi_hosts` property is a required property to run parallel command with MPI that defines the list of hosts of the MPI
cluster. The hosts are separated by a comma.

## mpi_tasks
The `mpi_tasks` property is a required property to run parallel command wih MPI that defines the maximum number of parallel
tasks.

## powsybl_config_dirs
The `itools_config_dir` property is an optional property that defines the configuration folders. The default
value is `$HOME/.itools`. The folders are separated by a colon.

## powsybl_config_name
The `powsybl_config_name` property is an optional property that defines the basename of the configuration file. The default
value is `config`.

At startup, powsybl looks in the configuration directories defined in the `powsybl_config_dirs` for a YAML configuration
file first, for a XML configuration file then and finally for properties files.

All the configuration files are stacked to allow an user to partially or totally overload the system configuration of a
module.

# Deprecated properties

## itools_cache_dir
The `itools_cache_dir` property is deprecated since V2.2.0. The `itools_cache_dir` property was an optional property that
defined the path to the cache folder used by modules that required cache functionalities. The default value was
`$HOME/.cache/itools`.

## itools_config_dir
The `itools_config_dir` property is deprecated since V2.2.0. Use the `powsybl_config_dirs` property instead.

## itools_config_name
The `itools_config_name` property is deprecated since V2.2.0. Use the `powsybl_config_name` property instead. 

# Example
```properties
# Configuration's directories
powsybl_config_dirs=$HOME/powsybl/etc:$HOME/.itools

# Configuration's file basename
powsybl_config_name=config

# Java maximum heap memory
java_xmx=8G

# MPI maximum parallel tasks count
mpi_tasks=2

# MPI comma sperated hosts list
mpi_hosts=localhost
```