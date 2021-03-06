---
title: 装箱（C++/CLI 和 C++/CX）
ms.date: 10/12/2018
ms.topic: reference
helpviewer_keywords:
- boxing, C++
ms.assetid: b5fd2c98-c578-4f83-8257-6dd663478665
ms.openlocfilehash: 709754e8609406f635444937af93488060167ba9
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2020
ms.locfileid: "80172602"
---
# <a name="boxing--ccli-and-ccx"></a>装箱（C++/CLI 和 C++/CX）

将值类型转换为对象称为“装箱”，而将对象转换为值类型则称为“取消装箱”。

## <a name="all-runtimes"></a>所有运行时

（此语言功能没有适用于所有运行时的备注。）

## <a name="windows-runtime"></a>Windows 运行时

C++/CX 支持用于装箱值类型和取消装箱引用类型的简写语法。 值类型在分配给类型为 `Object` 的变量时装箱。 在将 `Object` 变量分配给值类型变量，并且在括号中指定了未装箱的类型时（即，当对象变量强制转换为值类型时），该变量将取消装箱。

```cpp
  Platform::Object^
  object_variable  = value_variable;
value_variable = (value_type) object_variable;
```

### <a name="requirements"></a>要求

编译器选项：`/ZW`

### <a name="examples"></a>示例

下面的代码示例装箱和取消装箱 `DateTime` 值。 此示例先获取表示当前日期和时间的 `DateTime` 值，并将它分配给 `DateTime` 变量。 然后，通过将 `DateTime` 分配到 `Object` 变量，对它进行装箱。 最后，通过将装箱值分配到另一个 `DateTime` 变量，对它取消装箱。

若要测试示例，请创建 `BlankApplication` 项目，替换 `BlankPage::OnNavigatedTo()` 方法，然后在右括号处指定断点并对变量 `str1` 赋值。 当示例到达右括号时，检查 `str1`。

```cpp
void BlankPage::OnNavigatedTo(NavigationEventArgs^ e)
{
    using namespace Windows::Globalization::DateTimeFormatting;

    Windows::Foundation::DateTime dt, dtAnother;
    Platform::Object^ obj1;

    Windows::Globalization::Calendar^ c =
        ref new Windows::Globalization::Calendar;
    c->SetToNow();
    dt = c->GetDateTime();
    auto dtf = ref new DateTimeFormatter(
                           YearFormat::Full,
                           MonthFormat::Numeric,
                           DayFormat::Default,
                           DayOfWeekFormat::None);
    String^ str1 = dtf->Format(dt);
    OutputDebugString(str1->Data());
    OutputDebugString(L"\r\n");

    // Box the value type and assign to a reference type.
    obj1 = dt;
    // Unbox the reference type and assign to a value type.
    dtAnother = (Windows::Foundation::DateTime) obj1;

    // Format the DateTime for display.
    String^ str2 = dtf->Format(dtAnother);
    OutputDebugString(str2->Data());
}
```

有关详细信息，请参阅[装箱 (C++/CX)](../cppcx/boxing-c-cx.md)。

## <a name="common-language-runtime"></a>公共语言运行时

编译器将值类型装箱到 <xref:System.Object>。 这可能是因为存在将值类型转换为 <xref:System.Object> 的编译器定义的转换。

装箱和取消装箱使值类型能够被视为对象。 值类型（包括结构类型和内置类型，如 int）与 <xref:System.Object> 类型可相互转换。

有关详细信息，请参阅：

- [如何：显式请求装箱](../dotnet/how-to-explicitly-request-boxing.md)

- [如何：使用 gcnew 创建值类型和使用隐式装箱](../dotnet/how-to-use-gcnew-to-create-value-types-and-use-implicit-boxing.md)

- [如何：取消装箱](../dotnet/how-to-unbox.md)

- [标准转换和隐式装箱](../dotnet/standard-conversions-and-implicit-boxing.md)

### <a name="requirements"></a>要求

编译器选项：`/clr`

### <a name="examples"></a>示例

下面的示例说明了隐式装箱的工作方式。

```cpp
// vcmcppv2_explicit_boxing2.cpp
// compile with: /clr
using namespace System;

ref class A {
public:
   void func(System::Object^ o){Console::WriteLine("in A");}
};

value class V {};

interface struct IFace {
   void func();
};

value class V1 : public IFace {
public:
   virtual void func() {
      Console::WriteLine("Interface function");
   }
};

value struct V2 {
   // conversion operator to System::Object
   static operator System::Object^(V2 v2) {
      Console::WriteLine("operator System::Object^");
      return (V2^)v2;
   }
};

void func1(System::Object^){Console::WriteLine("in void func1(System::Object^)");}
void func1(V2^){Console::WriteLine("in func1(V2^)");}

void func2(System::ValueType^){Console::WriteLine("in func2(System::ValueType^)");}
void func2(System::Object^){Console::WriteLine("in func2(System::Object^)");}

int main() {
   // example 1 simple implicit boxing
   Int32^ bi = 1;
   Console::WriteLine(bi);

   // example 2 calling a member with implicit boxing
   Int32 n = 10;
   Console::WriteLine("xx = {0}", n.ToString());

   // example 3 implicit boxing for function calls
   A^ a = gcnew A;
   a->func(n);

   // example 4 implicit boxing for WriteLine function call
   V v;
   Console::WriteLine("Class {0} passed using implicit boxing", v);
   Console::WriteLine("Class {0} passed with forced boxing", (V^)(v));   // force boxing

   // example 5 casting to a base with implicit boxing
   V1 v1;
   IFace ^ iface = v1;
   iface->func();

   // example 6 user-defined conversion preferred over implicit boxing for function-call parameter matching
   V2 v2;
   func1(v2);   // user defined conversion from V2 to System::Object preferred over implicit boxing
                // Will call void func1(System::Object^);

   func2(v2);   // OK: Calls "static V2::operator System::Object^(V2 v2)"
   func2((V2^)v2);   // Using explicit boxing: calls func2(System::ValueType^)
}
```

```Output
1

xx = 10

in A

Class V passed using implicit boxing

Class V passed with forced boxing

Interface function

in func1(V2^)

in func2(System::ValueType^)

in func2(System::ValueType^)
```

## <a name="see-also"></a>另请参阅

[ .NET 和 UWP 的组件扩展](component-extensions-for-runtime-platforms.md)
