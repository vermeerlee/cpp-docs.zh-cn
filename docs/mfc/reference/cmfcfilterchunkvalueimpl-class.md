---
title: CMFCFilterChunkValueImpl Class | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCFilterChunkValueImpl
- AFXWIN/CMFCFilterChunkValueImpl
- AFXWIN/CMFCFilterChunkValueImpl::CMFCFilterChunkValueImpl
- AFXWIN/CMFCFilterChunkValueImpl::Clear
- AFXWIN/CMFCFilterChunkValueImpl::CopyChunk
- AFXWIN/CMFCFilterChunkValueImpl::CopyFrom
- AFXWIN/CMFCFilterChunkValueImpl::GetChunkGUID
- AFXWIN/CMFCFilterChunkValueImpl::GetChunkPID
- AFXWIN/CMFCFilterChunkValueImpl::GetChunkType
- AFXWIN/CMFCFilterChunkValueImpl::GetString
- AFXWIN/CMFCFilterChunkValueImpl::GetValue
- AFXWIN/CMFCFilterChunkValueImpl::GetValueNoAlloc
- AFXWIN/CMFCFilterChunkValueImpl::IsValid
- AFXWIN/CMFCFilterChunkValueImpl::SetBoolValue
- AFXWIN/CMFCFilterChunkValueImpl::SetDwordValue
- AFXWIN/CMFCFilterChunkValueImpl::SetFileTimeValue
- AFXWIN/CMFCFilterChunkValueImpl::SetInt64Value
- AFXWIN/CMFCFilterChunkValueImpl::SetIntValue
- AFXWIN/CMFCFilterChunkValueImpl::SetLongValue
- AFXWIN/CMFCFilterChunkValueImpl::SetSystemTimeValue
- AFXWIN/CMFCFilterChunkValueImpl::SetTextValue
- AFXWIN/CMFCFilterChunkValueImpl::SetChunk
dev_langs:
- C++
helpviewer_keywords:
- CMFCFilterChunkValueImpl [MFC], CMFCFilterChunkValueImpl
- CMFCFilterChunkValueImpl [MFC], Clear
- CMFCFilterChunkValueImpl [MFC], CopyChunk
- CMFCFilterChunkValueImpl [MFC], CopyFrom
- CMFCFilterChunkValueImpl [MFC], GetChunkGUID
- CMFCFilterChunkValueImpl [MFC], GetChunkPID
- CMFCFilterChunkValueImpl [MFC], GetChunkType
- CMFCFilterChunkValueImpl [MFC], GetString
- CMFCFilterChunkValueImpl [MFC], GetValue
- CMFCFilterChunkValueImpl [MFC], GetValueNoAlloc
- CMFCFilterChunkValueImpl [MFC], IsValid
- CMFCFilterChunkValueImpl [MFC], SetBoolValue
- CMFCFilterChunkValueImpl [MFC], SetDwordValue
- CMFCFilterChunkValueImpl [MFC], SetFileTimeValue
- CMFCFilterChunkValueImpl [MFC], SetInt64Value
- CMFCFilterChunkValueImpl [MFC], SetIntValue
- CMFCFilterChunkValueImpl [MFC], SetLongValue
- CMFCFilterChunkValueImpl [MFC], SetSystemTimeValue
- CMFCFilterChunkValueImpl [MFC], SetTextValue
- CMFCFilterChunkValueImpl [MFC], SetChunk
ms.assetid: 3c833f23-5b88-4d08-9e09-ca6a8aec88bf
caps.latest.revision: 25
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
ms.openlocfilehash: df02b6a6b6ac7e0683dbd75f45a77dd6cb5bd06d
ms.contentlocale: zh-cn
ms.lasthandoff: 09/12/2017

---
# <a name="cmfcfilterchunkvalueimpl-class"></a>CMFCFilterChunkValueImpl Class
This is a class which simplifies both chunk and property value pair logic.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCFilterChunkValueImpl : public ATL::IFilterChunkValue;  
```  
  
## <a name="members"></a>Members  
  
### <a name="public-constructors"></a>Public Constructors  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCFilterChunkValueImpl::~CMFCFilterChunkValueImpl](#_dtorcmfcfilterchunkvalueimpl)|Destructs the object.|  
|[CMFCFilterChunkValueImpl::CMFCFilterChunkValueImpl](#cmfcfilterchunkvalueimpl)|Constructs the object.|  
  
### <a name="public-methods"></a>Public Methods  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCFilterChunkValueImpl::Clear](#clear)|Clears the ChunkValue.|  
|[CMFCFilterChunkValueImpl::CopyChunk](#copychunk)|Copies this chunk to a structure describing the characteristics of a chunk.|  
|[CMFCFilterChunkValueImpl::CopyFrom](#copyfrom)|Initializes this chunk value from the other value.|  
|[CMFCFilterChunkValueImpl::GetChunkGUID](#getchunkguid)|Retrieves the chunk GUID.|  
|[CMFCFilterChunkValueImpl::GetChunkPID](#getchunkpid)|Retrieves the chunk PID (property ID).|  
|[CMFCFilterChunkValueImpl::GetChunkType](#getchunktype)|Gets chunk type.|  
|[CMFCFilterChunkValueImpl::GetString](#getstring)|Retrieves the the string value.|  
|[CMFCFilterChunkValueImpl::GetValue](#getvalue)|Retrieves the value as an allocated propvariant.|  
|[CMFCFilterChunkValueImpl::GetValueNoAlloc](#getvaluenoalloc)|Returns non-allocated (internal value) value.|  
|[CMFCFilterChunkValueImpl::IsValid](#isvalid)|Checks whether this property value is valid or not.|  
|[CMFCFilterChunkValueImpl::SetBoolValue](#setboolvalue)|Overloaded. Sets the property by key to a Boolean.|  
|[CMFCFilterChunkValueImpl::SetDwordValue](#setdwordvalue)|Sets the property by key to a DWORD.|  
|[CMFCFilterChunkValueImpl::SetFileTimeValue](#setfiletimevalue)|Sets the property by key to a filetime.|  
|[CMFCFilterChunkValueImpl::SetInt64Value](#setint64value)|Sets the property by key to an int64.|  
|[CMFCFilterChunkValueImpl::SetIntValue](#setintvalue)|Sets the property by key to an int.|  
|[CMFCFilterChunkValueImpl::SetLongValue](#setlongvalue)|Sets the property by key to a LONG.|  
|[CMFCFilterChunkValueImpl::SetSystemTimeValue](#setsystemtimevalue)|Sets the property by key to a SystemTime.|  
|[CMFCFilterChunkValueImpl::SetTextValue](#settextvalue)|Sets the property by key to a Unicode string.|  
  
### <a name="protected-methods"></a>Protected Methods  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCFilterChunkValueImpl::SetChunk](#setchunk)|A helper function that sets the chunk's common properties.|  
  
## <a name="remarks"></a>Remarks  
 To use, you simply create a CMFCFilterChunkValueImpl class of the right kind  
  
 Example:  
  
 CMFCFilterChunkValueImpl chunk;  
  
 hr = chunk.SetBoolValue(PKEY_IsAttachment, true);  
  
 or  
  
 hr = chunk.SetFileTimeValue(PKEY_ItemDate, ftLastModified);  
  
## <a name="inheritance-hierarchy"></a>Inheritance Hierarchy  
 `ATL::IFilterChunkValue`  
  
 [CMFCFilterChunkValueImpl](../../mfc/reference/cmfcfilterchunkvalueimpl-class.md)  
  
## <a name="requirements"></a>Requirements  
 **Header:** afxwin.h  
  
##  <a name="clear"></a>  CMFCFilterChunkValueImpl::Clear  
 Clears the ChunkValue.  
  
```  
void Clear();
```  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="cmfcfilterchunkvalueimpl"></a>  CMFCFilterChunkValueImpl::CMFCFilterChunkValueImpl  
 Constructs the object.  
  
```  
CMFCFilterChunkValueImpl();
```  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="_dtorcmfcfilterchunkvalueimpl"></a>  CMFCFilterChunkValueImpl::~CMFCFilterChunkValueImpl  
 Destructs the object.  
  
```  
virtual ~CMFCFilterChunkValueImpl();
```  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="copychunk"></a>  CMFCFilterChunkValueImpl::CopyChunk  
 Copies this chunk to a structure describing the characteristics of a chunk.  
  
```  
HRESULT CopyChunk(STAT_CHUNK* pStatChunk);
```  
  
### <a name="parameters"></a>Parameters  
 `pStatChunk`  
 A pointer to destination value describing the characteristics of the chunk.  
  
### <a name="return-value"></a>Return Value  
 S_OK if successful; otherwise an error code.  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="copyfrom"></a>  CMFCFilterChunkValueImpl::CopyFrom  
 Initializes this chunk value from the other value.  
  
```  
void CopyFrom (IFilterChunkValue* pValue);
```  
  
### <a name="parameters"></a>Parameters  
 `pValue`  
 Specifies the source value to copy from.  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="getchunkguid"></a>  CMFCFilterChunkValueImpl::GetChunkGUID  
 Retrieves the chunk GUID.  
  
```  
REFGUID GetChunkGUID() const;  
```  
  
### <a name="return-value"></a>Return Value  
 A reference to a GUID identifying the chunk.  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="getchunkpid"></a>  CMFCFilterChunkValueImpl::GetChunkPID  
 Retrieves the chunk PID (property ID).  
  
```  
DWORD GetChunkPID() const;  
```  
  
### <a name="return-value"></a>Return Value  
 A DWORD value containing the property ID.  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="getchunktype"></a>  CMFCFilterChunkValueImpl::GetChunkType  
 Retrieves the chunk type.  
  
```  
CHUNKSTATE GetChunkType() const;  
```  
  
### <a name="return-value"></a>Return Value  
 A CHUNKSTATE enumerated value, which specifies whether the current chunk is a text-type property or a value-type property.  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="getstring"></a>  CMFCFilterChunkValueImpl::GetString  
 Retrieves the string value.  
  
```  
CString &GetString();
```  
  
### <a name="return-value"></a>Return Value  
 A string containing the chunk value.  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="getvalue"></a>  CMFCFilterChunkValueImpl::GetValue  
 Retrieves the value as an allocated propvariant.  
  
```  
HRESULT GetValue(PROPVARIANT** ppPropVariant);
```  
  
### <a name="parameters"></a>Parameters  
 `ppPropVariant`  
 When the function returns, this parameter contains the chunk value.  
  
### <a name="return-value"></a>Return Value  
 S_OK if PROPVARIANT was allocated successfully and the chunk value was successfully copied to `ppPropVariant`; otherwise an error code.  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="getvaluenoalloc"></a>  CMFCFilterChunkValueImpl::GetValueNoAlloc  
 Returns the non-allocated (internal value) value.  
  
```  
PROPVARIANT GetValueNoAlloc ();
```  
  
### <a name="return-value"></a>Return Value  
 Returns the current chunk value.  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="isvalid"></a>  CMFCFilterChunkValueImpl::IsValid  
 Checks whether this property value is valid or not.  
  
```  
BOOL IsValid() const;  
```  
  
### <a name="return-value"></a>Return Value  
 `TRUE` if the current chunk value is valid; otherwise `FALSE`.  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="setboolvalue"></a>  CMFCFilterChunkValueImpl::SetBoolValue  
 Overloaded. Sets the property by key to a Boolean.  
  
```  
HRESULT SetBoolValue(
    REFPROPERTYKEY pkey,  
    BOOL bVal,  
    CHUNKSTATE chunkType = CHUNK_VALUE,  
    LCID locale = 0,  
    DWORD cwcLenSource = 0,  
    DWORD cwcStartSource = 0,  
    CHUNK_BREAKTYPE chunkBreakType = CHUNK_NO_BREAK);

 
HRESULT SetBoolValue(
    REFPROPERTYKEY pkey,  
    VARIANT_BOOL bVal,  
    CHUNKSTATE chunkType = CHUNK_VALUE,  
    LCID locale = 0,  
    DWORD cwcLenSource = 0,  
    DWORD cwcStartSource = 0,  
    CHUNK_BREAKTYPE chunkBreakType = CHUNK_NO_BREAK);
```  
  
### <a name="parameters"></a>Parameters  
 `pkey`  
 Specifies a property key.  
  
 `bVal`  
 Specifies the chunk value to set.  
  
 `chunkType`  
 Flags indicate whether this chunk contains a text-type or a value-type property. Flag values are taken from the CHUNKSTATE enumeration.  
  
 `locale`  
 The language and sublanguage associated with a chunk of text. Chunk locale is used by document indexers to perform proper word breaking of text. If the chunk is neither text-type nor a value-type with data type VT_LPWSTR, VT_LPSTR, or VT_BSTR, this field is ignored.  
  
 `cwcLenSource`  
 The length in characters of the source text from which the current chunk was derived. A zero value signifies character-by-character correspondence between the source text and the derived text. A nonzero value means that no such direct correspondence exists.  
  
 `cwcStartSource`  
 The offset from which the source text for a derived chunk starts in the source chunk.  
  
 `chunkBreakType`  
 The type of break that separates the previous chunk from the current chunk. Values are from the CHUNK_BREAKTYPE enumeration.  
  
### <a name="return-value"></a>Return Value  
 S_OK if successful; otherwise an error code.  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="setchunk"></a>  CMFCFilterChunkValueImpl::SetChunk  
 A helper function that sets the chunk's common properties.  
  
```  
HRESULT SetChunk(
    REFPROPERTYKEY pkey,  
    CHUNKSTATE chunkType=CHUNK_VALUE,  
    LCID locale=0,  
    DWORD cwcLenSource=0,  
    DWORD cwcStartSource=0,  
    CHUNK_BREAKTYPE chunkBreakType=CHUNK_NO_BREAK);
```  
  
### <a name="parameters"></a>Parameters  
 `pkey`  
 Specifies a property key.  
  
 `chunkType`  
 Flags indicate whether this chunk contains a text-type or a value-type property. Flag values are taken from the CHUNKSTATE enumeration.  
  
 `locale`  
 The language and sublanguage associated with a chunk of text. Chunk locale is used by document indexers to perform proper word breaking of text. If the chunk is neither text-type nor a value-type with data type VT_LPWSTR, VT_LPSTR, or VT_BSTR, this field is ignored.  
  
 `cwcLenSource`  
 The length in characters of the source text from which the current chunk was derived. A zero value signifies character-by-character correspondence between the source text and the derived text. A nonzero value means that no such direct correspondence exists.  
  
 `cwcStartSource`  
 The offset from which the source text for a derived chunk starts in the source chunk.  
  
 `chunkBreakType`  
 The type of break that separates the previous chunk from the current chunk. Values are from the CHUNK_BREAKTYPE enumeration.  
  
### <a name="return-value"></a>Return Value  
 S_OK if successful; otherwise error code.  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="setdwordvalue"></a>  CMFCFilterChunkValueImpl::SetDwordValue  
 Set the property by key to a DWORD.  
  
```  
HRESULT SetDwordValue(
    REFPROPERTYKEY pkey,  
    DWORD dwVal,  
    CHUNKSTATE chunkType = CHUNK_VALUE,  
    LCID locale = 0,  
    DWORD cwcLenSource = 0,  
    DWORD cwcStartSource = 0,  
    CHUNK_BREAKTYPE chunkBreakType = CHUNK_NO_BREAK);
```  
  
### <a name="parameters"></a>Parameters  
 `pkey`  
 Specifies a property key.  
  
 `dwVal`  
 Specifies the chunk value to set.  
  
 `chunkType`  
 Flags indicate whether this chunk contains a text-type or a value-type property. Flag values are taken from the CHUNKSTATE enumeration.  
  
 `locale`  
 The language and sublanguage associated with a chunk of text. Chunk locale is used by document indexers to perform proper word breaking of text. If the chunk is neither text-type nor a value-type with data type VT_LPWSTR, VT_LPSTR, or VT_BSTR, this field is ignored.  
  
 `cwcLenSource`  
 The length in characters of the source text from which the current chunk was derived. A zero value signifies character-by-character correspondence between the source text and the derived text. A nonzero value means that no such direct correspondence exists.  
  
 `cwcStartSource`  
 The offset from which the source text for a derived chunk starts in the source chunk.  
  
 `chunkBreakType`  
 The type of break that separates the previous chunk from the current chunk. Values are from the CHUNK_BREAKTYPE enumeration.  
  
### <a name="return-value"></a>Return Value  
 S_OK if successful; otherwise an error code.  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="setfiletimevalue"></a>  CMFCFilterChunkValueImpl::SetFileTimeValue  
 Set the property by key to a filetime.  
  
```  
HRESULT SetFileTimeValue(
    REFPROPERTYKEY pkey,  
    FILETIME dtVal,  
    CHUNKSTATE chunkType = CHUNK_VALUE,  
    LCID locale = 0,  
    DWORD cwcLenSource = 0,  
    DWORD cwcStartSource = 0,  
    CHUNK_BREAKTYPE chunkBreakType = CHUNK_NO_BREAK);
```  
  
### <a name="parameters"></a>Parameters  
 `pkey`  
 Specifies a property key.  
  
 `dtVal`  
 Specifies the chunk value to set.  
  
 `chunkType`  
 Flags indicate whether this chunk contains a text-type or a value-type property. Flag values are taken from the CHUNKSTATE enumeration.  
  
 `locale`  
 The language and sublanguage associated with a chunk of text. Chunk locale is used by document indexers to perform proper word breaking of text. If the chunk is neither text-type nor a value-type with data type VT_LPWSTR, VT_LPSTR, or VT_BSTR, this field is ignored.  
  
 `cwcLenSource`  
 The length in characters of the source text from which the current chunk was derived. A zero value signifies character-by-character correspondence between the source text and the derived text. A nonzero value means that no such direct correspondence exists.  
  
 `cwcStartSource`  
 The offset from which the source text for a derived chunk starts in the source chunk.  
  
 `chunkBreakType`  
 The type of break that separates the previous chunk from the current chunk. Values are from the CHUNK_BREAKTYPE enumeration.  
  
### <a name="return-value"></a>Return Value  
 S_OK if successful; otherwise an error code.  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="setint64value"></a>  CMFCFilterChunkValueImpl::SetInt64Value  
 Set the property by key to an int64.  
  
```  
HRESULT SetInt64Value(
    REFPROPERTYKEY pkey,  
    __int64 nVal,  
    CHUNKSTATE chunkType = CHUNK_VALUE,  
    LCID locale = 0,  
    DWORD cwcLenSource = 0,  
    DWORD cwcStartSource = 0,  
    CHUNK_BREAKTYPE chunkBreakType = CHUNK_NO_BREAK);
```  
  
### <a name="parameters"></a>Parameters  
 `pkey`  
 Specifies a property key.  
  
 `nVal`  
 Specifies the chunk value to set.  
  
 `chunkType`  
 Flags indicate whether this chunk contains a text-type or a value-type property. Flag values are taken from the CHUNKSTATE enumeration.  
  
 `locale`  
 The language and sublanguage associated with a chunk of text. Chunk locale is used by document indexers to perform proper word breaking of text. If the chunk is neither text-type nor a value-type with data type VT_LPWSTR, VT_LPSTR, or VT_BSTR, this field is ignored.  
  
 `cwcLenSource`  
 The length in characters of the source text from which the current chunk was derived. A zero value signifies character-by-character correspondence between the source text and the derived text. A nonzero value means that no such direct correspondence exists.  
  
 `cwcStartSource`  
 The offset from which the source text for a derived chunk starts in the source chunk.  
  
 `chunkBreakType`  
 The type of break that separates the previous chunk from the current chunk. Values are from the CHUNK_BREAKTYPE enumeration.  
  
### <a name="return-value"></a>Return Value  
 S_OK if successful; otherwise an error code.  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="setintvalue"></a>  CMFCFilterChunkValueImpl::SetIntValue  
 Set the property by key to an int.  
  
```  
HRESULT SetIntValue(
    REFPROPERTYKEY pkey,  
    int nVal,  
    CHUNKSTATE chunkType = CHUNK_VALUE,  
    LCID locale = 0,  
    DWORD cwcLenSource = 0,  
    DWORD cwcStartSource = 0,  
    CHUNK_BREAKTYPE chunkBreakType = CHUNK_NO_BREAK);
```  
  
### <a name="parameters"></a>Parameters  
 `pkey`  
 Specifies a property key.  
  
 `nVal`  
 Specifies the chunk value to set.  
  
 `chunkType`  
 Flags indicate whether this chunk contains a text-type or a value-type property. Flag values are taken from the CHUNKSTATE enumeration.  
  
 `locale`  
 The language and sublanguage associated with a chunk of text. Chunk locale is used by document indexers to perform proper word breaking of text. If the chunk is neither text-type nor a value-type with data type VT_LPWSTR, VT_LPSTR, or VT_BSTR, this field is ignored.  
  
 `cwcLenSource`  
 The length in characters of the source text from which the current chunk was derived. A zero value signifies character-by-character correspondence between the source text and the derived text. A nonzero value means that no such direct correspondence exists.  
  
 `cwcStartSource`  
 The offset from which the source text for a derived chunk starts in the source chunk.  
  
 `chunkBreakType`  
 The type of break that separates the previous chunk from the current chunk. Values are from the CHUNK_BREAKTYPE enumeration.  
  
### <a name="return-value"></a>Return Value  
 S_OK if successful; otherwise an error code.  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="setlongvalue"></a>  CMFCFilterChunkValueImpl::SetLongValue  
 Set the property by key to a LONG.  
  
```  
HRESULT SetLongValue(
    REFPROPERTYKEY pkey,  
    long lVal,  
    CHUNKSTATE chunkType = CHUNK_VALUE,  
    LCID locale = 0,  
    DWORD cwcLenSource = 0,  
    DWORD cwcStartSource = 0,  
    CHUNK_BREAKTYPE chunkBreakType = CHUNK_NO_BREAK);
```  
  
### <a name="parameters"></a>Parameters  
 `pkey`  
 Specifies a property key.  
  
 `lVal`  
 Specifies the chunk value to set.  
  
 `chunkType`  
 Flags indicate whether this chunk contains a text-type or a value-type property. Flag values are taken from the CHUNKSTATE enumeration.  
  
 `locale`  
 The language and sublanguage associated with a chunk of text. Chunk locale is used by document indexers to perform proper word breaking of text. If the chunk is neither text-type nor a value-type with data type VT_LPWSTR, VT_LPSTR, or VT_BSTR, this field is ignored.  
  
 `cwcLenSource`  
 The length in characters of the source text from which the current chunk was derived. A zero value signifies character-by-character correspondence between the source text and the derived text. A nonzero value means that no such direct correspondence exists.  
  
 `cwcStartSource`  
 The offset from which the source text for a derived chunk starts in the source chunk.  
  
 `chunkBreakType`  
 The type of break that separates the previous chunk from the current chunk. Values are from the CHUNK_BREAKTYPE enumeration.  
  
### <a name="return-value"></a>Return Value  
 S_OK if successful; otherwise an error code.  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="setsystemtimevalue"></a>  CMFCFilterChunkValueImpl::SetSystemTimeValue  
 Sets the property by key to a SystemTime.  
  
```  
HRESULT SetSystemTimeValue(
    REFPROPERTYKEY pkey,  
    const SYSTEMTIME& systemTime,  
    CHUNKSTATE chunkType = CHUNK_VALUE,  
    LCID locale=0,  
    DWORD cwcLenSource=0,  
    DWORD cwcStartSource=0,  
    CHUNK_BREAKTYPE chunkBreakType=CHUNK_NO_BREAK);
```  
  
### <a name="parameters"></a>Parameters  
 `pkey`  
 Specifies a property key.  
  
 `systemTime`  
 Specifies the chunk value to set.  
  
 `chunkType`  
 Flags indicate whether this chunk contains a text-type or a value-type property. Flag values are taken from the CHUNKSTATE enumeration.  
  
 `locale`  
 The language and sublanguage associated with a chunk of text. Chunk locale is used by document indexers to perform proper word breaking of text. If the chunk is neither text-type nor a value-type with data type VT_LPWSTR, VT_LPSTR, or VT_BSTR, this field is ignored.  
  
 `cwcLenSource`  
 The length in characters of the source text from which the current chunk was derived. A zero value signifies character-by-character correspondence between the source text and the derived text. A nonzero value means that no such direct correspondence exists.  
  
 `cwcStartSource`  
 The offset from which the source text for a derived chunk starts in the source chunk.  
  
 `chunkBreakType`  
 The type of break that separates the previous chunk from the current chunk. Values are from the CHUNK_BREAKTYPE enumeration.  
  
### <a name="return-value"></a>Return Value  
 S_OK if successful; otherwise an error code.  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="settextvalue"></a>  CMFCFilterChunkValueImpl::SetTextValue  
 Sets the property by key to a Unicode string.  
  
```  
HRESULT SetTextValue(
    REFPROPERTYKEY pkey,  
    LPCTSTR pszValue,  
    CHUNKSTATE chunkType = CHUNK_VALUE,  
    LCID locale = 0,  
    DWORD cwcLenSource = 0,  
    DWORD cwcStartSource = 0,  
    CHUNK_BREAKTYPE chunkBreakType = CHUNK_NO_BREAK);
```  
  
### <a name="parameters"></a>Parameters  
 `pkey`  
 Specifies a property key.  
  
 `pszValue`  
 Specifies the chunk value to set.  
  
 `chunkType`  
 Flags indicate whether this chunk contains a text-type or a value-type property. Flag values are taken from the CHUNKSTATE enumeration.  
  
 `locale`  
 The language and sublanguage associated with a chunk of text. Chunk locale is used by document indexers to perform proper word breaking of text. If the chunk is neither text-type nor a value-type with data type VT_LPWSTR, VT_LPSTR, or VT_BSTR, this field is ignored.  
  
 `cwcLenSource`  
 The length in characters of the source text from which the current chunk was derived. A zero value signifies character-by-character correspondence between the source text and the derived text. A nonzero value means that no such direct correspondence exists.  
  
 `cwcStartSource`  
 The offset from which the source text for a derived chunk starts in the source chunk.  
  
 `chunkBreakType`  
 The type of break that separates the previous chunk from the current chunk. Values are from the CHUNK_BREAKTYPE enumeration.  
  
### <a name="return-value"></a>Return Value  
 S_OK if successful; otherwise an error code.  
  
### <a name="remarks"></a>Remarks  
  
## <a name="see-also"></a>See Also  
 [Classes](../../mfc/reference/mfc-classes.md)
