---
title: remquo、remquof、remquol
description: 适用于 remquo、remquof 和 remquol 的 API 参考;它计算两个整数值的余数，并在参数中指定的位置存储商的符号和近似值的整数值。
ms.date: 9/1/2020
api_name:
- remquof
- remquo
- remquol
- _o_remquo
- _o_remquof
- _o_remquol
api_location:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-math-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- remquof
- remquol
- remquo
helpviewer_keywords:
- remquol function
- remquof function
- remquo function
ms.assetid: a1d3cb8b-8027-4cd3-8deb-04eb17f299fc
ms.openlocfilehash: d99204ad9a80c6320869cbb72aee905981a5224d
ms.sourcegitcommit: 4ed2d68634eb2fb77e18110a2d26bc0008be369c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/08/2020
ms.locfileid: "89554963"
---
# <a name="remquo-remquof-remquol"></a>remquo、remquof、remquol

计算两个整数值的余数，并将一个带有商的符号和近似值的整数值存储在参数中指定的位置。

## <a name="syntax"></a>语法

```C
double remquo( double numer, double denom, int* quo );
float remquof( float numer, float denom, int* quo );
long double remquol( long double numer, long double denom, int* quo );
#define remquo(X, Y, INT_PTR) // Requires C11 or higher

float remquo( float numer, float denom, int* quo ); /* C++ only */
long double remquo( long double numer, long double denom, int* quo ); /* C++ only */
```

### <a name="parameters"></a>参数

*收藏*\
分子。

*denom*\
分母。

*现状*\
指向整数值的指针，以存储带有商的符号和近似值的值。

## <a name="return-value"></a>返回值

**remquo**返回*x*  /  *y*的浮点余数。 如果 *y* 的值为0.0，则 **remquo** 将返回静默的 NaN。 有关 **printf** 系列的 quiet NaN 表示形式的信息，请参阅 [printf、_printf_l、wprintf、_wprintf_l](printf-printf-l-wprintf-wprintf-l.md)。

## <a name="remarks"></a>备注

**Remquo**函数计算*x*y 的浮点余数*f*  /  *y* ，这是*x*  =  *i* \* *y*  +  *f*，其中*i*是整数， *f*与*x*具有相同的符号， *f*的绝对值小于*y*的绝对值。

C + + 允许重载，因此你可以调用 **remquo** 的重载，该重载采用和返回 **`float`** 或 **`long double`** 值。 在 C 程序中，除非使用 \<tgmath.h> 宏来调用此函数，否则 **remquo** 始终采用两个 **`double`** 参数并返回一个 **`double`** 。

如果使用 \<tgmath.h> `remquo()` 宏，则参数的类型将决定选择哪个版本的函数。 有关详细信息，请参阅 [类型-泛型数学](../../c-runtime-library/tgmath.md) 。

默认情况下，此函数的全局状态的作用域限定为应用程序。 若要更改此项，请参阅 [CRT 中的全局状态](../global-state.md)。

## <a name="requirements"></a>要求

|函数|必需的标头 (C)|必需的标头 (C++)|
|--------------|---------------------|-|
|**remquo**、 **remquof**、 **remquol**|\<math.h>|\<cmath> 或 \<math.h>|
|**remquo** 宏 | \<tgmath.h> ||

有关兼容性信息，请参阅[兼容性](../../c-runtime-library/compatibility.md)。

## <a name="example"></a>示例

```C
// crt_remquo.c
// This program displays a floating-point remainder.

#include <math.h>
#include <stdio.h>

int main( void )
{
   double w = -10.0, x = 3.0, z;
   int quo = 0;

   z = remquo(w, x, &quo);
   printf("The remainder of %.2f / %.2f is %f\n", w, x, z);
   printf("Approximate signed quotient is %d\n", quo);
}
```

```Output
The remainder of -10.00 / 3.00 is -1.000000
Approximate signed quotient is -3
```

## <a name="see-also"></a>另请参阅

[浮点支持](../../c-runtime-library/floating-point-support.md)<br/>
[ldiv、lldiv](ldiv-lldiv.md)<br/>
[imaxdiv](imaxdiv.md)<br/>
[fmod, fmodf](fmod-fmodf.md)<br/>
[remainder、remainderf、remainderl](remainder-remainderf-remainderl.md)<br/>
