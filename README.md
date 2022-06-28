# Zxj-Blog
ESXI 6.7 网卡问题不可安装
1.进入esxi官网https://customerconnect.vmware.com/en/downloads/details?downloadGroup=ESXI67U3B&productId=742&rPId=89946
下载zip离线包文件
查看电脑主机网卡驱动：可以直接下载鲁大师~hh~
进入驱动下载https://vibsdepot.v-front.de/wiki/index.php/List_of_currently_available_ESXi_packages
选择Net55-r8168的驱动（net55-r8168驱动支持网卡型号（Realtek RTL8111B / RTL8168B / RTL8111/RTL8168 / RTL8111C / RTL8111CP / RTL8111D(L) / RTL8168C / RTL8111DP / RTL8111E / RTL8168E / RTL8111F / RTL8411 / RTL8111G / RTL8111GUS / RTL8411B(N) / RTL8118AS / D-Link DGE-528T））

到页面最下面Direct Download links的VIB File of version 8.045a下载
下载VMware-PowerCLI-6.5.0和ESXi-Customizer-PS封装工具https://www.v-front.de/p/esxi-customizer-ps.html#download

安装完成后电脑桌面会生成一个VMware PowerCLI，以管理员方式运行后如果看到以下报错（不管是否报错都要执行Set-ExecutionPolicy Unrestricted）
执行Set-ExecutionPolicy Unrestricted
重启后用管理员方式运行
c盘根目录下放：ESXi-Customizer-PS-v2.6.0.ps1和ESXi670-201912001.zip
然后在c盘创建一个whsir文件夹中放网卡驱动net55-r8168-8.045a-napi.x86_64.vib
执行.\ESXi-Customizer-PS-v2.6.0.ps1 -izip .\ESXi670-201912001.zip -pkgDir c:\whsir\
镜像会在C盘根目录中
https://blog.csdn.net/u014427391/article/details/102785219
