---
title: __cdecl
ms.date: 10/09/2018
f1_keywords:
- __cdecl_cpp
- __cdecl
- _cdecl
- cdecl
helpviewer_keywords:
- __cdecl keyword [C++]
ms.assetid: 1ff1d03e-fb4e-4562-8be1-74f1ad6427f1
ms.openlocfilehash: 9c1483d02bcb68d902cae527eb60e3ef9987607c
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/27/2020
ms.locfileid: "87227577"
---
# <a name="__cdecl"></a>__cdecl

**`__cdecl`** 是 C 和 c + + 程序的默认调用约定。 由于堆栈由调用方清理，因此它可以执行 `vararg` 函数。 **`__cdecl`** 调用约定创建的可执行文件比[__stdcall](../cpp/stdcall.md)更大，因为它要求每个函数调用包括堆栈清理代码。 以下列表显示此调用约定的实现。 **`__cdecl`** 修饰符是 Microsoft 特定的。

|元素|实施|
|-------------|--------------------|
|参数传递顺序|从右到左。|
|堆栈维护职责|调用函数从堆栈中弹出自变量。|
|名称修饰约定|下划线字符（_）作为名称的前缀，但在 \_ 导出使用 C 链接 _cdecl 函数时除外。|
|大小写转换约定|不执行任何大小写转换。|

> [!NOTE]
> 有关相关信息，请参阅[修饰名](../build/reference/decorated-names.md)。

将 **`__cdecl`** 修饰符放置在变量或函数名称之前。 由于 C 命名和调用约定为默认值，因此，只有 **`__cdecl`** 在指定了 `/Gv` （vectorcall）、 `/Gz` （stdcall）或 `/Gr` （fastcall）编译器选项时，才能在 x86 代码中使用。 [/Gd](../build/reference/gd-gr-gv-gz-calling-convention.md)编译器选项强制执行 **`__cdecl`** 调用约定。

在 ARM 和 x64 处理器上， **`__cdecl`** 将接受，但编译器通常会将其忽略。 按照 ARM 和 x64 上的约定，自变量将尽可能传入寄存器，后续自变量传递到堆栈中。 在 x64 代码中，使用 **`__cdecl`** 重写 **/Gv**编译器选项并使用默认的 x64 调用约定。

对于非静态类函数，如果函数是超行定义的，则调用约定修饰符不必在超行定义中指定。 也就是说，对于类非静态成员方法，在定义时假定声明期间指定的调用约定。 给定此类定义：

```cpp
struct CMyClass {
   void __cdecl mymethod();
};
```

此：

```cpp
void CMyClass::mymethod() { return; }
```

等效于此：

```cpp
void __cdecl CMyClass::mymethod() { return; }
```

为了与早期版本兼容， **cdecl**和 **_cdecl**是同义词， **`__cdecl`** 除非指定编译器选项[/za \( 禁用语言扩展）](../build/reference/za-ze-disable-language-extensions.md) 。

## <a name="example"></a>示例

在下面的示例中，将指示编译器对 `system` 函数使用 C 命名和调用约定。

```cpp
// Example of the __cdecl keyword on function
int __cdecl system(const char *);
// Example of the __cdecl keyword on function pointer
typedef BOOL (__cdecl *funcname_ptr)(void * arg1, const char * arg2, DWORD flags, ...);
```

## <a name="see-also"></a>另请参阅

[参数传递和命名约定](../cpp/argument-passing-and-naming-conventions.md)<br/>
[关键字](../cpp/keywords-cpp.md)
