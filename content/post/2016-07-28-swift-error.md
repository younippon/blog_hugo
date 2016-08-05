+++
date = "2016-07-28T11:51:43+09:00"
draft = false
title = "Xcodeで『a declaration cannot be both 'final' and 'dynamic'』エラー"
categories = [ "Swift" ]
tags = [ "Swift", "Xcode", "iOS" ]
+++

extensionにクラス変数を書くと出るようです。

## 解決策

`@nonobjc`という修飾子を使います。
これでobjective-Cから該当のプロパティが呼ばれなくなり、エラーが消えます。

```
class A: NSObject {}
extension A {
    @nonobjc static var hiddenCalendarIds = [""]
    }
```

