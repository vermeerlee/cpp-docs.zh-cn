---
title: "函数调用转换 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- function calls, converting
- function calls, argument type conversions
- functions [C], argument conversions
ms.assetid: 04ea0f81-509a-4913-8b12-0937a81babcf
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: 35eee1be7c509d1d4bb6267164ec90e48c94d1d1
ms.contentlocale: zh-cn
ms.lasthandoff: 05/18/2017

---
# <a name="function-call-conversions"></a>函数调用转换
对函数调用中的自变量执行的转换的类型取决于是否存在具有调用的函数的声明自变量类型的函数原型（前向声明）。  
  
 如果函数原型存在并包含声明的参数类型，编译器将执行类型检查（请参阅[函数](../c-language/functions-c.md)）。  
  
 如果函数原型不存在，则只对函数调用中的自变量执行常用算术转换。 这些转换独立于调用中的每个自变量执行。 这意味着 float 值被转换为 double； `char` 或 short 值被转换为 `int`；并且 `unsigned char` 或 unsigned short 被转换为 `unsigned int`。  
  
## <a name="see-also"></a>另请参阅  
 [类型转换](../c-language/type-conversions-c.md)