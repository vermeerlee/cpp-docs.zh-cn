---
title: '&lt;forward_list&gt; 函数'
ms.date: 11/04/2016
f1_keywords:
- forward_list/std::swap
ms.assetid: 0d6bc656-7049-4651-a4bd-c9a805e47756
ms.openlocfilehash: 78b1eaa44ed464de67d8ec45fab3241179bb94b9
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/16/2020
ms.locfileid: "79424799"
---
# <a name="ltforward_listgt-functions"></a>&lt;forward_list&gt; 函数

## <a name="swap"></a>购

交换两个转发列表的元素。

```cpp
void swap(forward_list <Type, Allocator>& left, forward_list <Type, Allocator>& right);
```

### <a name="parameters"></a>parameters

*左*\
一个 `forward_list` 类型的对象。

*right*\
一个 `forward_list` 类型的对象。

### <a name="remarks"></a>备注

该模板函数执行 `left.swap(right)`。
