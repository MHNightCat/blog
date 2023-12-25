---
title: 簡單設置出好看的 Gnome Ternimal Zsh
author: Night Cat
pubDatetime: 2023-12-25T06:30:00Z
postSlug: how-to-custom-gnome-ternimal
featured: true
draft: false
tags:
  - ubuntu
  - terminal
  - theme
  - step-by-step
description: 將ubuntu gnome terminal打造成有個性的樣子，將使用zsh跟oh my zsh
---

如果你希望有非常好看的terminal比如:
![](https://i.imgur.com/6F8Lizy.png)
那們這篇文章會非常適合你!

## 前情提要

- 系統採用ubuntu 22.10 理論上在其他的系統應該都差不多
- 使用VrtualBox進行演示
- 以下的每個指令如果你不是管理員都有可能叫你輸入系統密碼
- 如果有遇到錯誤可以到最下面的錯誤處理逛逛

# 安裝zsh以及自訂oh my zsh

## Step 1:更新整個系統

> 如果你因為安裝其他軟體已經執行過這個指令可以直接跳到Step 2

更新系統的package讓程式保持最新，請輸入下面的指令

```bash
sudo apt install
```

完成應該看到類似的東西

![](https://i.imgur.com/JgCcicT.png)

## Step 2: 安裝zsh

安裝zsh到你的ubuntu

```bash
sudo apt install zsh
```

如果遇到有詢問(y/n)的話直接輸入y按enter就好了

### 驗證zsh是否安裝

為了檢查zsh是否被正確安裝請輸入

```bash
zsh --version
```

![](https://i.imgur.com/xyN5XY2.png)

## Step 3:安裝curl與git

為了能夠獲取oh my zsh的安裝檔，你需要先安裝curl跟git，要安裝curl跟git請輸入以下指令:

```bash
sudo apt install curl git
```

## Step 4:安裝oh-my-zsh

oh my zsh是一個將zsh進行更好看的套件，輸入以下指令進行安裝

```bash
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

出現(y/n)一樣按y就對了

如果安裝成功應該出現下圖

![](https://i.imgur.com/zP8EMvC.png)

## Step 5:訂製你的zsh

現在你已經成功安裝你的zsh了 可以開始訂製了!

[**你可以在這裡找到oh my zsh的官方主題列表**](https://github.com/ohmyzsh/ohmyzsh/wiki/Themes)

> 你也可以去找非官方的 不過安裝上較為複雜 本文就不贅述了

找到你喜歡的主題之後將他的名稱記下來比如我喜歡這個，那麼我要記得的就是cloud

![](https://i.imgur.com/mORlwfs.png)

接下來輸入以下指令

```bash
nano ~/.zshrc
```

你會看到這個有點艱深的畫面 不過其實不難!

![](https://i.imgur.com/EI2mg4F.png)

首先找到`ZSH_THEME="rubbyrussell"`街著把它替換為你要的名字

這邊以cloud主題舉例的話就是

`ZSH_THEME="cloud"`

改完成之後鍵盤按下`ctrl` + `x` + `y` + `enter`這樣就成功儲存了喔!

要重新載入zsh可以輸入

```bash
source ~/.zshrc
```

完成後你就可以看到它配合你的主題了!

# terminal顏色主題

## Step 6:安裝必要package

接著可以開始自訂你的顏色了，這邊建議你用別人已經幫你調整好的主題

> [這邊將使用這個主題包](https://github.com/Gogh-Co/Gogh)

為了進行必要的package安裝，首先輸入以下指令進行安裝

```bash
sudo apt-get install dconf-cli uuid-runtime
```

## Step 7:安裝主題包

安裝主題包請輸入

```bash
bash -c "$(wget -qO- https://git.io/vQgMr)"
```

接著它會跑出各種的符號以及英文，一個符號以及英文代表一個主題，你可以上網找尋你要的主題名稱是否有在上面 或者自己摸索

這邊假設我要使用`Tokyo Night`當作我的主題

![](https://i.imgur.com/HPqe3j2.png)

那麼我就輸入`230`(如圖)

![](https://i.imgur.com/xBbMqnr.png)

接著按下`enter`即可

> 如果出現這個錯誤請往下滑看錯誤處理 ![](https://i.imgur.com/AVFdyQ6.png)

## Step 8:套用主題

首先請對terminal按右鍵 點擊Preferences

![](https://i.imgur.com/Ninvspx.png)

接著對你剛剛選擇的主題名稱旁邊的下鍵按下`Set as default`

![](https://i.imgur.com/r63e1TY.png)

接著關閉terminal 在開啟一次就會發現主題生效了喔

但你可以會發現zsh的主題怎麼消失了?這是因為zsh不是你的默認`shell`，可以到下一個章節查看如何設置為默認`Shell`

![](https://i.imgur.com/r63e1TY.png)

## Step 9:將zsh設置為默認

首先前往Preferences，點擊你剛剛設定的主題

![](https://i.imgur.com/SEiDkEm.png)

接著點擊位於上方的`command`，將`Run a custom command instead of my shell`打勾，並且在下方的輸入欄位輸入`zsh`（如下圖所見）

![](https://i.imgur.com/xLvSk4n.png)

# 結尾

這樣就完成你的gnome terminal主題設置了!

要達成我開頭圖的那樣子的話需要設定gnome theme（可能會在未來寫一篇!）

# 錯誤處理

## 安裝主題包時出現錯誤

請對terminal按右鍵 點擊Prefereences

![](https://i.imgur.com/Ninvspx.png)

開啟視窗之後在`Profiles`旁邊的`+`號鍵按下後輸入`Default`(內容皆不用動)

![](https://i.imgur.com/R5hCUNc.png)
完成之後重複進行`Step 7`即可
