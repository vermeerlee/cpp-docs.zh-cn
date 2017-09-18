---
title: "_countof 宏 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_countof"
  - "countof"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_countof 宏"
  - "countof 宏"
ms.assetid: 86198767-f7e5-4beb-898d-3cbbf60350a3
caps.latest.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 15
---
# _countof 宏
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

计算静态分配的数组中元素的数量。  
  
## 语法  
  
```  
size_t _countof(   
   array  
);  
```  
  
#### 参数  
 `array`  
 数组的名称。  
  
## 返回值  
 数组中的元素数，表示为 `size_t`。  
  
## 备注  
 确保 `array` 实际上是数组，而不是指针。  在 C 中，如果 `_countof` 是指针，则 `array` 将生成错误结果。  在 C\+\+ 中，如果 `_countof` 是指针，则 `array` 将无法编译。  
  
## 要求  
  
|宏|必需的标头|  
|-------|-----------|  
|`_countof`|\<stdlib.h\>|  
  
## 示例  
  
```  
// crt_countof.cpp  
#define _UNICODE  
#include <stdio.h>  
#include <stdlib.h>  
#include <tchar.h>  
  
int main( void )  
{  
   _TCHAR arr[20], *p;  
   printf( "sizeof(arr) = %zu bytes\n", sizeof(arr) );  
   printf( "_countof(arr) = %zu elements\n", _countof(arr) );  
   // In C++, the following line would generate a compile-time error:  
   // printf( "%zu\n", _countof(p) ); // error C2784 (because p is a pointer)  
  
   _tcscpy_s( arr, _countof(arr), _T("a string") );  
   // unlike sizeof, _countof works here for both narrow- and wide-character strings  
}  
```  
  
  **sizeof\(arr\) \= 40 bytes**  
**\_countof\(arr\) \= 20 elements**   
## 请参阅  
 [sizeof 运算符](../../cpp/sizeof-operator.md)