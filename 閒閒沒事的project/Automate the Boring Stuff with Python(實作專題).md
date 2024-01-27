## 第3章 函式
> 為甚麼從第3章開始? 因為前兩張沒實作專題題目啊...

### Collatz序列
#### 設計一個名為 collatz()的函式, 且有一個傳入的number參數. 如果number是偶數, 那collatz()就印出number//2, 並返回該數值. 如果number是奇數, collatz()印出及返回 3*number + 1. 接著編寫程式, 讓使用者輸入一個整數, 然後使用迴圈呼叫 collatz(), 直到函式返回值是1才結束. (很神奇的是, 這個序列對任何整數都有效, 利用這個序列遲早會得出1, 即使數學家也不確定為什麼, 這個程式所探討就是著名的考拉茲猜想序列(Collatz seqeunce), 有時也被稱為"最簡單,最不可能的數學問題"
#### 記住要把input()取得的返回值以int()先轉換成整數型別, 不然它還是字串.
```python3
#2024/1/28
def collatz(x:int): 
    if x == 1:          #設定終點
        print(1)
    elif x % 2 == 0:    #遇到偶數判斷
        print(x//2)     
        if x//2 != 1:       #當x/2 不是1的時候再繼續
            collatz(x//2)   
    else:               #不是終點 不是偶數 那就剩奇數囉
        print(3*x+1)
        collatz(3*x+1)

enterNumber = int(input("Please enter a number: "))
print(enterNumber)  #這樣會好看點
collatz(enterNumber)
```
