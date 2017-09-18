---
title: CDialogEx Class | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDialogEx
- AFXDIALOGEX/CDialogEx
- AFXDIALOGEX/CDialogEx::CDialogEx
- AFXDIALOGEX/CDialogEx::SetBackgroundColor
- AFXDIALOGEX/CDialogEx::SetBackgroundImage
dev_langs:
- C++
helpviewer_keywords:
- CDialogEx [MFC], CDialogEx
- CDialogEx [MFC], SetBackgroundColor
- CDialogEx [MFC], SetBackgroundImage
ms.assetid: a6ed3b1f-aef8-4b66-ac78-2160faf63c13
caps.latest.revision: 27
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
ms.translationtype: MT
ms.sourcegitcommit: 4e0027c345e4d414e28e8232f9e9ced2b73f0add
ms.openlocfilehash: 63da5d8ae72d64020ee336dc4d8b3b0bceb428ff
ms.contentlocale: zh-cn
ms.lasthandoff: 09/12/2017

---
# <a name="cdialogex-class"></a>CDialogEx Class
The `CDialogEx` class specifies the background color and background image of a dialog box.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CDialogEx : public CDialog  
```  
  
## <a name="members"></a>Members  
  
### <a name="public-constructors"></a>Public Constructors  
  
|Name|Description|  
|----------|-----------------|  
|[CDialogEx::CDialogEx](#cdialogex)|Constructs a `CDialogEx` object.|  
|`CDialogEx::~CDialogEx`|Destructor.|  
  
### <a name="public-methods"></a>Public Methods  
  
|Name|Description|  
|----------|-----------------|  
|[CDialogEx::SetBackgroundColor](#setbackgroundcolor)|Sets the background color of the dialog box.|  
|[CDialogEx::SetBackgroundImage](#setbackgroundimage)|Sets the background image of the dialog box.|  
  
## <a name="remarks"></a>Remarks  
 To use the `CDialogEx` class, derive your dialog box class from the `CDialogEx` class instead of the `CDialog` class.  
  
 Dialog box images are stored in a resource file. The framework automatically deletes any image that is loaded from the resource file. To programmatically delete the current background image, call the [CDialogEx::SetBackgroundImage](#setbackgroundimage) method or implement an `OnDestroy` event handler. When you call the [CDialogEx::SetBackgroundImage](#setbackgroundimage) method, pass in an `HBITMAP` parameter as the image handle. The `CDialogEx` object will take ownership of the image and delete it if the `m_bAutoDestroyBmp` flag is `TRUE`.  
  
 A `CDialogEx` object can be a parent of a [CMFCPopupMenu Class](../../mfc/reference/cmfcpopupmenu-class.md) object. The [CMFCPopupMenu Class](../../mfc/reference/cmfcpopupmenu-class.md) object calls the `CDialogEx::SetActiveMenu` method when the [CMFCPopupMenu Class](../../mfc/reference/cmfcpopupmenu-class.md) object opens. Afterward, the `CDialogEx` object handles any menu event until the [CMFCPopupMenu Class](../../mfc/reference/cmfcpopupmenu-class.md) object is closed.  
  
## <a name="inheritance-hierarchy"></a>Inheritance Hierarchy  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CDialogEx](../../mfc/reference/cdialogex-class.md)  
  
## <a name="requirements"></a>Requirements  
 **Header:** afxdialogex.h  
  
##  <a name="cdialogex"></a>  CDialogEx::CDialogEx  
 Constructs a `CDialogEx` object.  
  
```  
CDialogEx(
    UINT nIDTemplate,  
    CWnd* pParent=NULL);

 
CDialogEx(
    LPCTSTR lpszTemplateName,  
    CWnd* pParentWnd=NULL);
```  
  
### <a name="parameters"></a>Parameters  
 [in] `nIDTemplate`  
 The resource ID of a dialog box template.  
  
 [in] `lpszTemplateName`  
 The resource name of a dialog box template.  
  
 [in] `pParent`  
 A pointer to the parent window. The default value is `NULL`.  
  
 [in] `pParentWnd`  
 A pointer to the parent window. The default value is `NULL`.  
  
### <a name="return-value"></a>Return Value  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="setbackgroundcolor"></a>  CDialogEx::SetBackgroundColor  
 Sets the background color of the dialog box.  
  
```  
void SetBackgroundColor(
    COLORREF color,  
    BOOL bRepaint=TRUE);
```  
  
### <a name="parameters"></a>Parameters  
 [in] `color`  
 An RGB color value.  
  
 [in] `bRepaint`  
 `TRUE` to immediately update the screen; otherwise, `FALSE`. The default value is `TRUE`.  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="setbackgroundimage"></a>  CDialogEx::SetBackgroundImage  
 Sets the background image of the dialog box.  
  
```  
void SetBackgroundImage(
    HBITMAP hBitmap,  
    BackgroundLocation location=BACKGR_TILE,  
    BOOL bAutoDestroy=TRUE,  
    BOOL bRepaint=TRUE);

 
BOOL SetBackgroundImage(
    UINT uiBmpResId,  
    BackgroundLocation location=BACKGR_TILE,  
    BOOL bRepaint=TRUE);
```  
  
### <a name="parameters"></a>Parameters  
 [in] `hBitmap`  
 A handle to the background image.  
  
 [in] `uiBmpResId`  
 The resource ID of the background image.  
  
 [in] `location`  
 One of the `CDialogEx::BackgroundLocation` values that specify the location of the image. Valid values include BACKGR_TILE, BACKGR_TOPLEFT, BACKGR_TOPRIGHT, BACKGR_BOTTOMLEFT, and BACKGR_BOTTOMRIGHT. The default value is BACKGR_TILE.  
  
 [in] `bAutoDestroy`  
 `TRUE` to automatically destroy the background image; otherwise, `FALSE`.  
  
 [in] `bRepaint`  
 `TRUE` to immediately redraw the dialog box; otherwise, `FALSE`.  
  
### <a name="return-value"></a>Return Value  
 In the second method overload syntax, `TRUE` if the method is successful; otherwise, `FALSE`.  
  
### <a name="remarks"></a>Remarks  
 The image that you specify is not stretched to fit the dialog box client area.  
  
## <a name="see-also"></a>See Also  
 [Hierarchy Chart](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CMFCPopupMenu Class](../../mfc/reference/cmfcpopupmenu-class.md)   
 [CContextMenuManager Class](../../mfc/reference/ccontextmenumanager-class.md)
