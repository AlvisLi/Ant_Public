# 编译openvpn3
1.下载vcpkg代码，执行目录下bootstrap-vcpkg.bat脚本生成vcpkg.exe  
2.下载openvpn3代码：git clone -b release/x.x.x https://xx.x.x x.x.x  
3.使用vcpkg.exe安装相关库：vcpkg.exe install asio:x86-windows，需要什么库可以参考openvpn3内的vcpkg.json文件内容  
4.使用cmake选择openvpn3源码目录，执行configure，选择win32编译，openvpn3可以使用ssl或者tls，默认ssl  
5.遇到编译不通过，填入vcpkg/installed/x86-windows/share目录或者lib或者include目录即可，需要处理GTest、LZ4、jsoncpp  
6.【如果不使用默认的ssl，使用tls】，勾选USE_MBEDTLS，使用vcpkg安装MBEDTLS，编译时需添加mebedtls相关的库和引用，库需加mbedtls、mbedx509、mbedcrypto  
  mbedtls的version.h文件需新建文件夹mbedtls，放入此目录，mbedtls/mbedtls/version.h
6.完成，执行generate生成工程目录  
