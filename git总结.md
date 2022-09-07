## 本地新建分支远程同分支一致
> 可以理解为远程强制覆盖本地代码，网上是这三部。
感觉主要是第二部在起作用。（暂时记录到这，没时间尝试仅用第二部的情况）
```
git fetch --all
git reset --hard origin/<branch>
git pull
```