---
title: "ISymUnmanagedReader2::GetSymAttributePreRemap 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedReader2.GetSymAttributePreRemap
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedReader2::GetSymAttributePreRemap
helpviewer_keywords:
- GetSymAttributePreRemap method [.NET Framework debugging]
- ISymUnmanagedReader2::GetSymAttributePreRemap method [.NET Framework debugging]
ms.assetid: 7580d546-a709-40c5-ad02-aa70d774fd0b
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4a9e2304e746578fbe0e7a5c4d1b0ef1f1c8a1b1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedreader2getsymattributepreremap-method"></a>ISymUnmanagedReader2::GetSymAttributePreRemap 메서드
이름을 기반으로 사용자 지정 특성을 가져옵니다. 이러한 특성은 메타 데이터 사용자 지정 특성과 달리 기호 저장소에 보관 됩니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetSymAttributePreRemap(  
    [in]  mdToken  parent,  
    [in]  WCHAR    *name,  
    [in]  ULONG32  cBuffer,  
    [out] ULONG32  *pcBuffer,  
    [out, size_is(cBuffer),  
        length_is(*pcBuffer)] BYTE buffer[]);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `parent`  
 [in] 부모 메타 데이터 토큰입니다.  
  
 `name`  
 [in] 에 대 한 포인터는 `WCHAR` 이름이 들어 있는입니다.  
  
 `cBuffer`  
 [in] A `ULONG32` 크기를 표시 하는 `buffer` 배열입니다.  
  
 `pcBuffer`  
 [out] 에 대 한 포인터는 `ULONG32` 특성 바이트를 포함 하는 데 필요한 버퍼의 크기를 받는입니다.  
  
 `buffer`  
 [out] 특성 바이트를 수신 하는 버퍼에 대 한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
 메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 기타 오류 코드입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>참고 항목  
 [ISymUnmanagedReader2 인터페이스](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-interface.md)
