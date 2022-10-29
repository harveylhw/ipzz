# 利用iptables设置端口转发的shell脚本

## 项目作用

1. 便捷地设置iptables流量转发规则
2. 当域名解析的地址发生变化时，自动更新流量转发规则，不需要手动变更（适用于ddns域名）

## 用法


```shell
wget --no-check-certificate -qO natcfg.sh https://raw.githubusercontent.com/harvey202210/-iptablesUtils/main/natcfg.sh && bash natcfg.sh
```

输出如下：

```
#############################################################
# Usage: setup iptables nat rules for domian/ip             #
#                        万海云涛                            #
# Author: Harvey                                            #
# Github: https://github.com/harvey202210/-iptablesUtils    #
#############################################################

你要做什么呢（请输入数字）？Ctrl+C 退出本脚本
1) 增加转发规则          3) 列出所有转发规则
2) 删除转发规则          4) 查看当前iptables配置
#?
```

此时按照需要，输入1-4中的任意数字，然后按照提示即可

## 卸载

```shell
wget --no-check-certificate -qO uninstall.sh https://raw.githubusercontent.com/harvey202210/-iptablesUtils/main/dnat-uninstall.sh && bash uninstall.sh
```

## 查看日志

```shell
journalctl -exu dnat
```

## 配置文件备份和导入导出

配置文件在

```shell
/etc/dnat/conf
```

## trojan转发

总是有人说，不能转发trojan，这么说的人大部分是证书配置不对。最简单的解决方案是：客户端选择不验证证书。复杂一点是自己把证书和中转机的域名搭配好。

小白记住一句话就好：客户端不验证证书。

-----------------------------------------------------------------------------

