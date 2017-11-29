---
title: "ISymUnmanagedReader::GetMethodsFromDocumentPosition 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedReader.GetMethodsFromDocumentPosition
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedReader::GetMethodsFromDocumentPosition
helpviewer_keywords:
- GetMethodsFromDocumentPosition method [.NET Framework debugging]
- ISymUnmanagedReader::GetMethodsFromDocumentPosition method [.NET Framework debugging]
ms.assetid: 83605f1e-e4f3-49e6-859b-f13cad68bb54
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 7f82cf213e9bcc83055cfaa42b9acab9d395d405
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedreadergetmethodsfromdocumentposition-method"></a>ISymUnmanagedReader::GetMethodsFromDocumentPosition 메서드
문서에서 지정된 된 위치에 중단점을 포함 하며 각 방법의 배열을 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetMethodsFromDocumentPosition (  
    [in]  ISymUnmanagedDocument* document,  
    [in]  ULONG32 line,  
    [in]  ULONG32 column,  
    [in]  ULONG32 cMethod,  
    [out] ULONG32* pcMethod,  
    [out, size_is (cMethod),  
        length_is (*pcMethod)] ISymUnmanagedMethod* pRetVal[]);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `document`  
 [in] 지정 된 문서입니다.  
  
 `line`  
 [in] 지정된 된 문서 줄입니다.  
  
 `column`  
 [in] 지정된 된 문서 열입니다.  
  
 `cMethod`  
 [in] `pRetVal` 배열의 크기입니다.  
  
 `pcMethod`  
 [out] 반환 되는 요소 수를 받는 변수에 대 한 포인터는 `pRetVal` 배열입니다.  
  
 `pRetVal`  
 [out] 각각 가리키는 포인터의 배열은 [ISymUnmanagedMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md) 중단점을 포함 하는 메서드를 나타내는 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 기타 오류 코드입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>참고 항목  
 [ISymUnmanagedReader 인터페이스](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
