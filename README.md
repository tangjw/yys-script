# yys-script
阴阳师按键精灵脚本
## 魂十一
```
// 查找阴阳师窗口
执行次数 = 50
HwndEx = Plugin.Window.Search("阴阳师-网易游戏")
YYSArr = Split(HwndEx, "|")
Call Plugin.Window.Size(YYSArr(0), 800, 0)
Delay 2000
Call Plugin.Window.Size(YYSArr(1), 800, 0)
sRect1 = Plugin.Window.GetClientRect(YYSArr(0))
sRect2 = Plugin.Window.GetClientRect(YYSArr(1))
OriginArr1 = Split(sRect1, "|")
tOx1 = Clng(OriginArr1(0))
tOy1 = Clng(OriginArr1(1))
OriginArr2 = Split(sRect2, "|")
tOx2 = Clng(OriginArr2(0))
tOy2 = Clng(OriginArr2(1))
If tOy1 - tOy2 < 0 Then 
    Ox1 = tOx1
    Oy1 = tOy1
    Ox2 = tOx2
    Oy2 = tOy2
Else 
    Ox1 = tOx2
    Oy1 = tOy2
    Ox2 = tOx1
    Oy2 = tOy1
End If
TracePrint Ox1 & "," & Oy1
TracePrint Ox2 & "," & Oy2
Randomize //初始化随机数生成器
TEMPx = int(Rnd() * 10)
TEMPy =  int(Rnd() * 10)
While TEMPx = TEMPy
    TEMPy = int(Rnd() * 10)
    Delay 500
Wend
TracePrint TEMPx * 6 & "," & TEMPy * 2
For i = 1 To 执行次数
    // 关闭可能的协作任务弹窗
    If i Mod 5 = 3 Then 
        MoveTo Ox + 468 + TEMPx * 5, Oy + 65 + TEMPy * 2
        LeftDown 1
        Delay 200 + TEMPy * 10
        LeftUp 1
        Delay 1000 + TEMPy * 100 
    End If
    MoveTo Ox1 + 585 + TEMPx * 9, Oy1 + 353 + TEMPy * 2
    LeftDown 1
    Delay 200 + TEMPx * 10
    LeftUp 1
    // 等待随机时间 110s以上
    Delay 61*1000 + TEMPx * 200
    TracePrint "xxxxxx"
    If i Mod 2 = 1 Then 
        // 点击右边
        MoveTo Ox1 + 700 + TEMPx * 2, Oy1 + 95 + TEMPy * 19
        LeftDown 1
        Delay 200 + TEMPx * 14
        LeftUp 1
        Delay 1000 + TEMPx * 100
        MoveTo Ox2 + 50 + TEMPy * 2, Oy2 + 95 + TEMPx * 21
        LeftDown 1
        Delay 200 + TEMPy * 14
        LeftUp 1
        // 点击左边
        Delay 5000 + TEMPx * 100
        MoveTo Ox1 + 50 + TEMPy * 3, Oy1 + 95 + TEMPx * 21
        LeftDown 1
        Delay 200 + TEMPy * 14
        LeftUp 1
        Delay 1000 + TEMPy * 100
        MoveTo Ox2 + 700 + TEMPx * 3, Oy2 + 95 + TEMPy * 21
        LeftDown 1
        Delay 200 + TEMPx * 16
        LeftUp 1
    Else 
        // 点击右边
        MoveTo Ox1 + 50 + TEMPx * 2, Oy1 + 95 + TEMPy * 19
        LeftDown 1
        Delay 200 + TEMPx * 14
        LeftUp 1
        Delay 1000 + TEMPx * 100
        MoveTo Ox2 + 700 + TEMPy * 2, Oy2 + 95 + TEMPx * 21
        LeftDown 1
        Delay 200 + TEMPy * 14
        LeftUp 1
        // 点击左边
        Delay 5000 + TEMPx * 100
        MoveTo Ox1 + 700 + TEMPy * 3, Oy1 + 95 + TEMPx * 21
        LeftDown 1
        Delay 200 + TEMPy * 14
        LeftUp 1
        Delay 1000 + TEMPy * 100
        MoveTo Ox2 + 50 + TEMPx * 3, Oy2 + 95 + TEMPy * 21
        LeftDown 1
        Delay 200 + TEMPx * 16
        LeftUp 1
    End If
    Delay 4000 + TEMPy * 120
Next

dim Obj,UserName,NowTime,LenS,Num
Set Obj = createobject("WScript.Shell")
Obj.Run "shutdown -s -t 60"

EndScript
```
## 业火原
```
// 查找阴阳师窗口
执行次数 = 15
Hwnd = Plugin.Window.Find(0, "阴阳师-网易游戏")
Call Plugin.Window.Size(Hwnd, 800, 0)
Delay 1000
sRect = Plugin.Window.GetClientRect(Hwnd)
// 坐标原点
OriginArr = Split(sRect, "|")
Ox = Clng(OriginArr(0))
Oy = Clng(OriginArr(1))
// MoveTo +582,Clng(OriginArr(1))+302
Delay 500
// 挑战按钮  746-194,362-69 Dx = 60 Dy = 20 
For i = 1 To 执行次数
    Randomize //初始化随机数生成器
    TEMPx = int(Rnd() * 10)
    TEMPy =  int(Rnd() * 10)
    While TEMPx = TEMPy
        TEMPy = int(Rnd() * 10)
        Delay 500
    Wend
    TracePrint TEMPx * 6 & "," & TEMPy * 2
    // 关闭可能的协作任务弹窗
    If i Mod 5 = 4 Then 
        MoveTo Ox + 468 + TEMPx * 5, Oy + 65 + TEMPy * 2
        LeftDown 1
        Delay 200 + TEMPy * 10
        LeftUp 1
        // 点击右边
        Delay 1000 + TEMPy * 100 
    End If
    MoveTo Ox + 552 + TEMPx * 6, Oy + 293 + TEMPy * 2
    LeftDown 1
    Delay 200 + TEMPx * 10
    LeftUp 1
    // 等待随机时间 110s以上
    Delay 30000 + TEMPx * 5
    MoveTo 800,900
    Delay 40000+ TEMPx * 15
    MoveTo 1080,1280
    Delay 50000 + TEMPx * 1000
    If i Mod 2 = 1 Then 
        // 点击右边
        MoveTo Ox + 700 + TEMPx * 2, Oy + 95 + TEMPy * 19
        LeftDown 1
        Delay 200 + TEMPx * 14
        LeftUp 1
    Else 
        // 点击左边
        Delay 2000 + TEMPy * 110 
        MoveTo Ox + 50 + TEMPy * 3, Oy + 95 + TEMPx * 21
        LeftDown 1
        Delay 200 + TEMPy * 14
        LeftUp 1
    End If
    Delay 2000 + TEMPy * 80
Next
```
