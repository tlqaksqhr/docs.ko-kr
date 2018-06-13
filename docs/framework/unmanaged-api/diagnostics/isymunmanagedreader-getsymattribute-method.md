---
title: ISymUnmanagedReader::GetSymAttribute 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetSymAttribute
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetSymAttribute
helpviewer_keywords:
- GetSymAttribute method [.NET Framework debugging]
- ISymUnmanagedReader::GetSymAttribute method [.NET Framework debugging]
ms.assetid: c675ce7e-76e7-45ff-8273-3b6489a2767c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c9f22f23835f01022d5d62596b2cf63425759193
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33426065"
---
# <a name="isymunmanagedreadergetsymattribute-method"></a>ISymUnmanagedReader::GetSymAttribute 메서드
이름을 기반으로 사용자 지정 특성을 가져옵니다. 사용자 지정 특성 메타 데이터와는 달리 이러한 사용자 지정 특성 기호 저장소에 보관 됩니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetSymAttribute (  
    [in]  mdToken  parent,  
    [in]  WCHAR    *name,  
    [in]  ULONG32  cBuffer,  
    [out] ULONG32  *pcBuffer,  
    [out, size_is (cBuffer),  
        length_is (*pcBuffer)] BYTE buffer[]);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `parent`  
 [in] 특성이 요청 된 개체에 대 한 메타 데이터 토큰입니다.  
  
 `name`  
 [in] 검색할 특성을 나타내는 변수에 대 한 포인터입니다.  
  
 `cBuffer`  
 [in] `buffer` 배열의 크기입니다.  
  
 `pcBuffer`  
 [out] 특성 데이터의 길이 받는 변수에 대 한 포인터입니다.  
  
 `buffer`  
 [out] 특성 데이터를 수신 하는 변수에 대 한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
 메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 기타 오류 코드입니다.  
  
## <a name="requirements"></a>요구 사항  
 **Header:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>참고 항목  
 [ISymUnmanagedReader 인터페이스](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
