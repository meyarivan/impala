This is a lazy attempt to get Impala to build under Ubuntu 12.04

Pre-requisites
---------------

### To download & unpack under impala/thirdparty/

http://archive.cloudera.com/cdh4/cdh/4/hive-0.9.0-cdh4.1.0.tar.gz
http://archive.cloudera.com/cdh4/cdh/4/hadoop-2.0.0-cdh4.1.0.tar.gz
http://archive.cloudera.com/cdh4/cdh/4/hbase-0.92.1-cdh4.1.0.tar.gz

https://googletest.googlecode.com/files/gtest-1.6.0.zip
https://gperftools.googlecode.com/files/gperftools-2.0.tar.gz
https://google-glog.googlecode.com/files/glog-0.3.1.tar.gz
https://gflags.googlecode.com/files/gflags-1.5.tar.gz

https://snappy.googlecode.com/files/snappy-1.0.5.tar.gz
ftp://ftp.andrew.cmu.edu/pub/cyrus-mail/cyrus-sasl-2.1.23.tar.gz
https://mongoose.googlecode.com/files/mongoose-3.0.tgz

- compile mongoose
- compile other deps using "impala/bin/build_thirdparty.sh -noclean"

### Thrift

- compile and install apache-thrift-0.7.0 (specify "--with-pic") (ensure that install_dir/bin is in $PATH)
- copy python thrift libs to impala/thrift/python-thrift-0.7.0
- compile and install apache-thrift-0.7.0/contrib/fb303
- set THRIFT_CONTRIB\_DIR to fb303 install\_dir

### LLVM 3.0

- install llvm-3.0, clang using native pkg mgmt tools (apt)
- ln somedir/llvm-config -> llvm-config-3.0
- ln somedir/opt -> opt-3.0
- ensure somedir is in $PATH such that somedir/llvm-config is the first available llvm-config in $PATH

Building
---------

- cd impala; ./buildall.sh -codecoverage_release (watch logs & fix errors (if any))



Impala documentation can be found here:
https://ccp.cloudera.com/display/IMPALA10BETADOC/Cloudera+Impala+1.0+Beta+Documentation

