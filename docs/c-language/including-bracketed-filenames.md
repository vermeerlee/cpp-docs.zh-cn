---
title: 包含用括号括起来的文件名
ms.date: 11/04/2016
ms.assetid: 6a4e5411-c35e-48b8-90ef-b37ac324ed94
ms.openlocfilehash: 87de00814f58ed86ee33abdcf96dd210f418c5ba
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62233094"
---
# <a name="including-bracketed-filenames"></a>包含用括号括起来的文件名

**ANSI 3.8.2** 查找可包含源文件的方法

对于用尖括号括起的文件规范，预处理器不会搜索父文件的目录。 “父级”文件是其中包含 [#include](../preprocessor/hash-include-directive-c-cpp.md) 指令的文件。 相反，它首先会通过 /I 后面的编译器命令行上指定的目录中搜索文件。 如果 /I 选项不存在或失败，预处理器会使用 INCLUDE 环境变量在尖括号中查找包含文件。 INCLUDE 环境变量可以包含使用分号 (;  ) 分隔的多个路径。 如果多个目录显示为 /I 选项的一部分或在 INCLUDE 环境变量中，预处理器会按它们的出现顺序搜索它们。

## <a name="see-also"></a>请参阅

[预处理指令](../c-language/preprocessing-directives.md)
