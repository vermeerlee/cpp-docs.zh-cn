---
title: MFC DLL 向导生成的类和函数
ms.date: 11/04/2016
helpviewer_keywords:
- functions [MFC]
- functions [MFC], DLLs
- MFC DLL Wizard
- DLLs [MFC], wizard classes and functions
- classes [MFC], generated by MFC DLL wizard
- code [MFC], generated by MFC DLL wizard
ms.assetid: e69e62fe-4953-42bf-a2fc-50bbf9bdaeaf
ms.openlocfilehash: add914f18ab961ff6dbc5cb056e2f2a81c252a48
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754917"
---
# <a name="classes-and-functions-generated-by-the-mfc-dll-wizard"></a>MFC DLL 向导生成的类和函数

MFC DLL 向导生成的代码取决于要创建的 DLL 类型和您选择的选项。 MFC DLL 向导为两种形式的常规 MFC DLL 生成相同的代码。

|Kind of DLL|选项|类|函数|
|-----------------|------------|-------------|---------------|
|[扩展名](../../build/extension-dlls-overview.md)|无|无|`DllMain`|
|[定期](../../build/regular-dlls-dynamically-linked-to-mfc.md)|无|派生自`CWinApp`|无|
|[定期](../../build/regular-dlls-dynamically-linked-to-mfc.md)|自动化|派生自`CWinApp`|`DllGetClassObject` `DllCanUnloadNow` `DllRegisterServer`|
|[扩展名](../../build/extension-dlls-overview.md)|窗口套接字|无|`DllMain`|
|[定期](../../build/regular-dlls-dynamically-linked-to-mfc.md)|窗口套接字|派生自`CWinApp`|`InitInstance`包含对`AfxSocketInit`|

## <a name="see-also"></a>请参阅

[MFC DLL 向导](../../mfc/reference/mfc-dll-wizard.md)
