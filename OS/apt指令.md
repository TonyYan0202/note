#### 快速取用

更新
```
sudo apt update && sudo apt upgrade -y
```

| 軟體      | 指令                             |
| ------- | ------------------------------ |
| Nginx   | ```sudo apt install nginx```   |
| Apache2 | ```sudo apt install apache2``` |
| UFW     | ???                            |
|         |                                |



#### 更新

更新軟體清單
```
sudo apt update
```

更新所有軟體(`-y` 自動接受全部Y/N)
```
sudo apt upgrade -y
```

完整升級（會移除或安裝額外套件）
```
sudo apt full-upgrade
```

#### 安裝

安裝套件
```
sudo apt install <name>
```

同時安裝多個
```
sudo apt install <name1> <name2> <name3>
```

#### 移除

移除套件(保留設定檔)
```
sudo apt remove <name>
```

移除套件(全部)
```
sudo apt purge <name>
```

移除不必要套件(常在`purge`執行後執行)
```
sudo apt autoremove
```

#### 查看

搜尋
```
apt search <name>
```

查看套件資訊
```
apt show <name>
```

查看已安裝版本
```
apt list --installed | grep <name>
```

列出可升級套件
```
apt list --upgradable
```
#### 重新下載與修復

修復錯誤時
```
sudo apt --fix-broken install
```

清除下載快取
```
sudo apt clean
```

