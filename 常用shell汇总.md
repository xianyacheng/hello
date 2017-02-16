## 1. 改变指定目录以及其子目录下的所有文件的拥有者和群组 
　　命令：chown -R -v root:root test6
	-R 处理指定目录以及其子目录下的所有文件
　　-v 显示详细的处理信息

## 2. Ubuntu 12.04 静态ip的设置方法        
	1.配置静态ip地址        
		命令：sudo vi /etc/network/interfaces      
		原有内容只有如下两行：
		auto lo
		iface lo inet loopback                     
		向末尾追加以下内容：
		auto eth0
		iface eth0 inet static
		address 192.168.0.33
		gateway 192.168.0.1
		netmask 255.255.255.0
		network 192.168.0.0
		broadcast 192.168.0.255
		然后保存退出；
	2.手动配置 dns
		sudo vi /etc/resolv.conf
		想末尾追加如下内容：
		nameserver 192.168.0.10
		search openstacklocal
		然后保存退出。
	3、重启网卡：
		sudo /etc/init.d/network restart          

## 3. 循环远程复制.shh目录到download group notify labhub2 sql1 sql2 be服务器上
for i in download group notify labhub2 sql1 sql2 be;do scp -r .ssh $i:/home/git;done 
