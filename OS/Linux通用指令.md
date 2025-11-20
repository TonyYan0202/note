| 指令                            | 動作       |
| ----------------------------- | -------- |
| reboot                        | 重新啟動     |
| shutdown -h now               | 關機       |
| /etc/init.d/[service] restart | 重啟服務     |
| ls /etc/init.d                | 查看現有服務   |
| ip                            | 查詢網路設定   |
| sudo su                       | 進入root模式 |
指令可用
&& 第一個執行成功後 執行下一個
```
<command1> && <command2>
```

; 無條件一直執行
```
<command1> ; <command2>
```

|| 前面失敗 執行下一個
```
<command1> || <command2>
```

& 背景執行
command1 丟背景 command2 終端執行
```
<command1> & <command2>
```