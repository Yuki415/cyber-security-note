**标签**：`#预备知识` `#进攻性安全` `#2025-03-28` `#第一课`
# FakeBank 渗透测试记录
**日期**：2025-03-28  
**关联知识点**：`#Gobuster` `#权限提升` 
## 🎯 实验目标
1. 使用Gobuster命令行程序暴力破解网站
2. 查找隐藏目录或凭证
3. 进入有转账权限的页面
4. 转入2000USD

## 🔍 攻击过程
### 1.打开终端Terminal
### 2. 使用Gobuster命令行工具
**暴力查找**

gobuster是一个免费的开源目录和文件枚举工具。渗透测试人员和安全专业人员使用它来查找 Web 服务器上的隐藏目录和文件。
```
gobuster -u http://fakebank.thm -w wordlist.txt dir
```
u是指我们要使用gobuster扫描的网站。
w是指提供的单词列表。gobuster会根据这个单词列表中的单词一一扫描存在的页面。
我们通过遍历wordlist.txt文件中的单词，暴力破解网站，找出隐藏页面。

**获取数据**：

<img width="909" alt="image" src="https://github.com/user-attachments/assets/b2e8bffb-16fc-4afd-a43e-5baa689b9b7f" />
得到的status200对应的 网站/bank-transfer 是网站隐藏的页面。
这个隐藏的页面极有可能是-由于人为错误或疏忽导致未被设为私有的-具有转账权限的-页面
### 3. 破解银行

**访问隐藏页面**：

直接访问得到的隐藏页面http://fakebank.thm/bank-transfer
<img width="775" alt="image" src="https://github.com/user-attachments/assets/6d247b34-4b5f-4409-9ea0-ddc091051fd2" />
拥有转账权限！

## 🛡️ 防御建议
1. 
## 📌 关联知识
- []()
- [[]]（）
