# 编译openvpn3
1.下载vcpkg代码，执行里面的bootstrap-vcpkg.bat脚本生成vcpkg.exe程序  
2.下载openvpn3特定版本到本地:git clone -b release/x.x.x https://xx.x.x x.x.x  
3.使用vcpkg.exe程序安装相关库文件，需要什么库可以参考openvpn3内的vcpkg.json文件内容：vcpkg.exe install asio:x86-windows  
4.使用cmake选择openvpn3源码目录，执行configure，选择win32编译，openvpn3可以使用ssl或者tls，默认ssl  
5.遇到编译不通过，GTest DIR-NOTFOUND选择vcpkg/installed/x86-windows/share对应的GTest目录继续  
6.处理LZ4，处理LZO（可不处理），处理jsoncpp  
7.完成，执行generate生成工程目录  
