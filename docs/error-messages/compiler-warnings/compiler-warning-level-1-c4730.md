---
title: 编译器警告（等级 1）C4730
ms.date: 11/04/2016
f1_keywords:
- C4730
helpviewer_keywords:
- C4730
ms.assetid: 11303e3f-162b-4b19-970a-479686123a68
ms.openlocfilehash: a132dcc795d6055c854a5ad147940868fe4e088b
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/27/2020
ms.locfileid: "87228773"
---
# <a name="compiler-warning-level-1-c4730"></a>编译器警告（等级 1）C4730

"main"：混合 _m64 和浮点表达式可能导致不正确的代码

函数使用[__m64](../../cpp/m64.md)和 **`float`** / **`double`** 类型。 由于 MMX 和浮点寄存器共享同一物理寄存器空间（不能同时使用），因此 **`__m64`** **`float`** / **`double`** 在同一函数中使用和类型可能会导致数据损坏，并可能导致异常。

为了安全地 **`__m64`** 在同一函数中使用类型和浮点类型，使用其中一种类型的每个指令都应由 **_m_empty （）** （对于 MMX）或 **_m_femms （）** （对于3DNow！）内部函数进行分隔。

下面的示例生成 C4730：

```cpp
// C4730.cpp
// compile with: /W1
// processor: x86
#include "mmintrin.h"

void func(double)
{
}

int main(__m64 a, __m64 b)
{
   __m64 m;
   double f;
   f = 1.0;
   m = _m_paddb(a, b);
   // uncomment the next line to resolve C4730
   // _m_empty();
   func(f * 3.0);   // C4730
}
```
