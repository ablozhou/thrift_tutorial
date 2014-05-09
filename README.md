== thrift tutorial ==
1.go to 
https://thrift.apache.org/
download thrift-0.9.1

2.install thrift2.install thrift
zhh@andymac Downloads$ cd thrift-0.9.1
./configure
make
zhh@andymac thrift-0.9.1$ make install

3. modify share.thrift


add 
 namespace go tutorial 

modify tutorial.thrift 
add
  namespace go tutorial

find i32 calculate(1:i32 logid, 2:Work w), comment throw expression,because thrift 0.9.1 has bug to process exception for go lang:
   i32 calculate(1:i32 logid, 2:Work w),
// zhh 2014.5.9: thrift 0.9.1 has bug of exception process for go lang. so comment 
// throws (1:InvalidOperation ouch),

4.in top directory
  make server

5. in java directory
  make client
