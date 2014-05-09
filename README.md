# thrift tutorial 
## 1. download thrift
https://thrift.apache.org/

download thrift-0.9.1

## 2.install thrift2.install thrift
<pre>
zhh@andymac Downloads$ cd thrift-0.9.1
./configure
make
zhh@andymac thrift-0.9.1$ make install
</pre>
## 3. difference of thrift file from thrift.apache.com
<pre>
for share.thrift

add 
 namespace go tutorial 

for tutorial.thrift 
add
  namespace go tutorial

find i32 calculate(1:i32 logid, 2:Work w), comment throw expression,because thrift 0.9.1 has bug to process exception for go lang:
   i32 calculate(1:i32 logid, 2:Work w),
// zhh 2014.5.9: thrift 0.9.1 has bug of exception process for go lang. so comment 
// throws (1:InvalidOperation ouch),
</pre>

## 4. make go lang server
<pre>
  in top directory,generate source file
  $ thrift --gen go -out src share.thrift
  $ thrift --gen go -out src tutorial.thrift
  $ thrift --gen java -o java src share.thrift
  $ thrift --gen java -o java tutorial.thrift
  $ make server
</pre>
## 5. make java client client
<pre>
  in java directory
  $ make client
</pre>

