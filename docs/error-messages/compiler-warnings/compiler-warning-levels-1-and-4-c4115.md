---
title: 编译器警告（等级 1 和等级 4）C4115
ms.date: 11/04/2016
f1_keywords:
- C4115
helpviewer_keywords:
- C4115
ms.assetid: f3f94e72-fc49-4d09-b3e7-23d68e61152f
ms.openlocfilehash: 7e39e8c837d94776a804da2bf38643b453edb949
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2020
ms.locfileid: "80198037"
---
# <a name="compiler-warning-levels-1-and-4-c4115"></a>编译器警告（等级 1 和等级 4）C4115

“type”：括号中的已命名类型定义

给定的符号用于在带括号的表达式内部定义结构、联合或枚举类型。 定义范围可能并非预期。

在 C 函数调用中，定义具有全局作用域。 在 C++ 调用中，定义与调用的函数具有相同的范围。

在不是带括号表达式的括号（如原型）内，声明符也可以导致此警告。

这是在 ANSI 兼容性 (/Za) 下编译的 C++ 程序和 C 程序的 1 级警告。 否则为 3 级警告。
