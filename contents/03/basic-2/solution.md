## 解法
二分探索を用いてr以下の要素数からl-1以下の要素数を引くことで求めることができます。Pythonでは標準ライブラリであるbisectを使うことができます。

## 計算量
ソートと各クエリに対する二分探索がボトルネックになるのでO(NlogN + QlogN)です。