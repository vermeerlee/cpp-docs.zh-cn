---
title: CSingleLock Class | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSingleLock
- AFXMT/CSingleLock
- AFXMT/CSingleLock::CSingleLock
- AFXMT/CSingleLock::IsLocked
- AFXMT/CSingleLock::Lock
- AFXMT/CSingleLock::Unlock
dev_langs:
- C++
helpviewer_keywords:
- CSingleLock [MFC], CSingleLock
- CSingleLock [MFC], IsLocked
- CSingleLock [MFC], Lock
- CSingleLock [MFC], Unlock
ms.assetid: 7dae7288-8066-4a3e-85e0-78d28bfc6bc8
caps.latest.revision: 20
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
ms.openlocfilehash: e71c3ef486fdff44525fc178666107b4a2963fff
ms.contentlocale: zh-cn
ms.lasthandoff: 09/12/2017

---
# <a name="csinglelock-class"></a>CSingleLock Class
Represents the access-control mechanism used in controlling access to a resource in a multithreaded program.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CSingleLock  
```  
  
## <a name="members"></a>Members  
  
### <a name="public-constructors"></a>Public Constructors  
  
|Name|Description|  
|----------|-----------------|  
|[CSingleLock::CSingleLock](#csinglelock)|Constructs a `CSingleLock` object.|  
  
### <a name="public-methods"></a>Public Methods  
  
|Name|Description|  
|----------|-----------------|  
|[CSingleLock::IsLocked](#islocked)|Determines if the object is locked.|  
|[CSingleLock::Lock](#lock)|Waits on a synchronization object.|  
|[CSingleLock::Unlock](#unlock)|Releases a synchronization object.|  
  
## <a name="remarks"></a>Remarks  
 `CSingleLock` does not have a base class.  
  
 In order to use the synchronization classes [CSemaphore](../../mfc/reference/csemaphore-class.md), [CMutex](../../mfc/reference/cmutex-class.md), [CCriticalSection](../../mfc/reference/ccriticalsection-class.md), and [CEvent](../../mfc/reference/cevent-class.md), you must create either a `CSingleLock` or [CMultiLock](../../mfc/reference/cmultilock-class.md) object to wait on and release the synchronization object. Use `CSingleLock` when you only need to wait on one object at a time. Use **CMultiLock** when there are multiple objects that you could use at a particular time.  
  
 To use a `CSingleLock` object, call its constructor inside a member function in the controlled resource's class. Then call the [IsLocked](#islocked) member function to determine if the resource is available. If it is, continue with the remainder of the member function. If the resource is unavailable, either wait for a specified amount of time for the resource to be released, or return failure. After use of the resource is complete, either call the [Unlock](#unlock) function if the `CSingleLock` object is to be used again, or allow the `CSingleLock` object to be destroyed.  
  
 `CSingleLock` objects require the presence of an object derived from [CSyncObject](../../mfc/reference/csyncobject-class.md). This is usually a data member of the controlled resource's class. For more information on how to use `CSingleLock` objects, see the article [Multithreading: How to Use the Synchronization Classes](../../parallel/multithreading-how-to-use-the-synchronization-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Inheritance Hierarchy  
 `CSingleLock`  
  
## <a name="requirements"></a>Requirements  
 **Header:** afxmt.h  
  
##  <a name="csinglelock"></a>  CSingleLock::CSingleLock  
 Constructs a `CSingleLock` object.  
  
```  
explicit CSingleLock(
    CSyncObject* pObject,  
    BOOL bInitialLock = FALSE);
```  
  
### <a name="parameters"></a>Parameters  
 `pObject`  
 Points to the synchronization object to be accessed. Cannot be **NULL**.  
  
 `bInitialLock`  
 Specifies whether to initially attempt to access the supplied object.  
  
### <a name="remarks"></a>Remarks  
 This function is generally called from within an access member function of the controlled resource.  
  
### <a name="example"></a>Example  
 [!code-cpp[NVC_MFC_Utilities#19](../../mfc/codesnippet/cpp/csinglelock-class_1.h)]  
  
##  <a name="islocked"></a>  CSingleLock::IsLocked  
 Determines if the object associated with the `CSingleLock` object is nonsignaled (unavailable).  
  
```  
BOOL IsLocked();
```  
  
### <a name="return-value"></a>Return Value  
 Nonzero if the object is locked; otherwise 0.  
  
### <a name="example"></a>Example  
 [!code-cpp[NVC_MFC_Utilities#20](../../mfc/codesnippet/cpp/csinglelock-class_2.h)]  
  
##  <a name="lock"></a>  CSingleLock::Lock  
 Call this function to gain access to the resource controlled by the synchronization object supplied to the `CSingleLock` constructor.  
  
```  
BOOL Lock(DWORD dwTimeOut = INFINITE);
```  
  
### <a name="parameters"></a>Parameters  
 *dwTimeOut*  
 Specifies the amount of time to wait for the synchronization object to be available (signaled). If **INFINITE**, `Lock` will wait until the object is signaled before returning.  
  
### <a name="return-value"></a>Return Value  
 Nonzero if the function was successful; otherwise 0.  
  
### <a name="remarks"></a>Remarks  
 If the synchronization object is signaled, `Lock` will return successfully and the thread now owns the object. If the synchronization object is nonsignaled (unavailable), `Lock` will wait for the synchronization object to become signaled up to the number of milliseconds specified in the *dwTimeOut* parameter. If the synchronization object did not become signaled in the specified amount of time, `Lock` returns failure.  
  
### <a name="example"></a>Example  
 [!code-cpp[NVC_MFC_Utilities#21](../../mfc/codesnippet/cpp/csinglelock-class_3.h)]  
  
##  <a name="unlock"></a>  CSingleLock::Unlock  
 Releases the synchronization object owned by `CSingleLock`.  
  
```  
BOOL Unlock();

 
BOOL Unlock(
    LONG lCount,  
    LPLONG lPrevCount = NULL);
```  
  
### <a name="parameters"></a>Parameters  
 `lCount`  
 Number of accesses to release. Must be greater than 0. If the specified amount would cause the object's count to exceed its maximum, the count is not changed and the function returns **FALSE**.  
  
 `lPrevCount`  
 Points to a variable to receive the previous count of the synchronization object. If **NULL**, the previous count is not returned.  
  
### <a name="return-value"></a>Return Value  
 Nonzero if the function was successful; otherwise 0.  
  
### <a name="remarks"></a>Remarks  
 This function is called by `CSingleLock`'s destructor.  
  
 If you need to release more than one access count of a semaphore, use the second form of `Unlock` and specify the number of accesses to release.  
  
### <a name="example"></a>Example  
 [!code-cpp[NVC_MFC_Utilities#21](../../mfc/codesnippet/cpp/csinglelock-class_3.h)]  
  
## <a name="see-also"></a>See Also  
 [Hierarchy Chart](../../mfc/hierarchy-chart.md)   
 [CMultiLock Class](../../mfc/reference/cmultilock-class.md)
