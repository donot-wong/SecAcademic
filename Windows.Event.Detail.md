# Windows Event Detail
## 4624 成功登陆事件
```
{"UserName": "User793535", "EventID": 4624, "LogHost": "EnterpriseAppServer", "LogonID": "0x1c904d41", "DomainName": "Domain001", "LogonTypeDescription": "Network", "AuthenticationPackage": "Kerberos", "Time": 5356799, "LogonType": 3}
```



## 4634 退出登陆事件
```
{"UserName": "User793535", "EventID": 4634, "LogHost": "EnterpriseAppServer", "LogonID": "0x1c8c8cf3", "DomainName": "Domain001", "LogonTypeDescription": "Network", "Time": 5356799, "LogonType": 3}
```


## 



#### 
```
$ cat wls_day-62 | grep 0x283af1 | head -n 20
{"UserName": "User793535", "EventID": 4624, "LogHost": "Comp571028", "LogonID": "0x283af1", "DomainName": "Domain001", "LogonTypeDescription": "NewCredentials", "SubjectUserName": "User793535", "ProcessName": "Proc964159.exe", "AuthenticationPackage": "Negotiate", "Time": 5334799, "LogonType": 9, "SubjectLogonID": "0x29c09", "SubjectDomainName": "Domain001", "ProcessID": "0x17d0"}

{"UserName": "User793535", "EventID": 4672, "LogHost": "Comp571028", "LogonID": "0x283af1", "DomainName": "Domain001", "Time": 5334799}

{"UserName": "User793535", "EventID": 4688, "LogHost": "Comp571028", "LogonID": "0x283af1", "DomainName": "Domain001", "ParentProcessName": "Proc411423", "ParentProcessID": "0x5d0", "ProcessName": "conhost.exe", "Time": 5334799, "ProcessID": "0x1530"}

{"UserName": "User793535", "EventID": 4634, "LogHost": "Comp571028", "LogonID": "0x283af1", "DomainName": "Domain001", "LogonTypeDescription": "NewCredentials", "Time": 5335270, "LogonType": 9}

```


5335270 - 5334799


### 特征
1. 登陆类型
2. 回话持续时长
3. 创建进程名称列表向量化
4. 父进程名称列表向量化
5. 创建进程数量

6. 登陆类型描述
7. 该用户当天登陆成功次数统计
8. 该用户当天登陆失败次数统计

9. 该用户当天成功登陆不同计算机统计
10. 该用户当天尝试登陆不同计算机统计

11. 该用户当天登陆不同计算机并创建进程统计

13. 此次登陆是该用户当天第n次登陆该计算机


1. 横向移动的检测，不仅可以有效发现攻击者扩大其攻击范围，危害内网其他账户或主机，也能有效的发现最初的沦陷主机或账户
linear paths, directed acyclic graphs (DAGs), or cyclic graphs
