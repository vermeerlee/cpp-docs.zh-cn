---
title: 编译器错误 C2216
ms.date: 11/04/2016
f1_keywords:
- C2216
helpviewer_keywords:
- C2216
ms.assetid: 250f6bdc-a5e1-495f-a1e8-6e8e7021ad9d
ms.openlocfilehash: 7da1816fbd8196501b043f09c6bf7da201b3de18
ms.sourcegitcommit: 72161bcd21d1ad9cc3f12261aa84a5b026884afa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/17/2020
ms.locfileid: "90742640"
---
# <a name="compiler-error-c2216"></a>编译器错误 C2216

“keyword1”不能和“keyword2”一起使用

一起使用两个互相排斥的关键字。

## <a name="examples"></a>示例

下面的示例生成 C2216。

```cpp
// C2216.cpp
// compile with: /clr /c
ref struct Y1 {
   literal
   static int staticConst2 = 10;   // C2216
};
```

下面的示例生成 C2216。

```cpp
// C2216b.cpp
// compile with: /clr /c
public ref class X {
   extern property int i { int get(); }   // C2216 extern not allowed on property
   typedef property int i2;   // C2216 typedef not allowed on property
};
```

下面的示例生成 C2216。

```cpp
// C2216c.cpp
// compile with: /clr /c
public interface struct I {
   double f();
   double g();
   double h();
};

public ref struct R : I {
   virtual double f() new override { return 0.0; }   // C2216
   virtual double g() new { return 0.0; }   // OK
   virtual double h() override { return 0.0; }   // OK
};
```
