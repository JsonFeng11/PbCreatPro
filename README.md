# PbCreatPro
一个goole的protocolbuffuer的使用
  最近公司要改变弹幕的解析方式,也为了更高效.我做了大量工作,也是第一次使用谷歌的protocolbuffer.下面介绍一下我的使用(环境:MAC):
  
   准备工作:                                                  
    安装homebrew,自行百度.                                     
    
    然后
    brew install automake
    brew install libtool
    brew install protobuf
                                                              
                                                                                                          
    
  下载依赖库:          
  git clone https://github.com/alexeyxo/protobuf-objc.git     
  完成之后,执行下面的代码:
  	    
  	    cd ~/protobuf-objc
		./autogen.sh
		./configure
  	    
 你可能会遇到错误.不要急,试一下这行代码,
 	    
 	    ./configure CXXFLAGS=-I/usr/local/include LDFLAGS=-L/usr/local/lib

#####	    运行完全ok之后
	    
	    make
		make install
最终生成的插件名字为protoc-gen-objc，会被安装到/usr/local/bin/目录下。你可以去看一下:
	    
	    cd /usr/local/bin/ 
		ls -a

准备就绪之后,就可以创建test.proto文件了,然后cd进去,执行如下代码:
	   
	   protoc --plugin=/usr/local/bin/protoc-gen-objc person.proto --objc_out=./
会生成 test.pb.h 与 test.pb.m文件,到时候直接调用就可以了

本文参考链接:<http://blog.csdn.net/u014202635/article/details/46531329>    	     	    
 	     	     	    
    
 	     	     	    
 	     	     	    
 	     	     	    
 	     	     	    
 	     	     	    
 	     	     	    