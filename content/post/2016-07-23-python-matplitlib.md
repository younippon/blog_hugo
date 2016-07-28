+++
date = "2016-07-23T10:54:13+09:00"
draft = false
title = "python3.xでmatplitlibを入れようとしたらエラー"

+++

## 問題

```
import pylab
```

しようとすると

```
RuntimeError: Python is not installed as a framework. The Mac OS X backend will not be able to function correctly if Python is not installed as a framework. See the Python documentation for more information on installing Python as a framework on Mac OS X. Please either reinstall Python as a framework, or try one of the other backends.
```

## 解決策

~/.matplotlib/matplotlibrc

```
backend : TkAgg
```

## 原因

matplotlibの画像描画バックエンド（参考 http://matplotlib.org/faq/usage_faq.html#what-is-a-backend ）はデフォルトの設定ではCocoaのAPIを使ってレンダリングを行う"macosx"である。デフォルトではないバックエンドとしてGTKAggやQt4Aggがある。LinuxやWindowsから使うときは当然macosx以外のバックエンドを設定する？？？

