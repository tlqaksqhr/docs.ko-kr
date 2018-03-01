---
title: "ISymUnmanagedMethod::GetRanges 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ISymUnmanagedMethod.GetRanges
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetRanges
helpviewer_keywords:
- ISymUnmanagedMethod::GetRanges method [.NET Framework debugging]
- GetRanges method [.NET Framework debugging]
ms.assetid: a85283d8-379c-417a-9736-ddeeef9bcf50
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1e17b411e39e522006092d79380566484f8fab67
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedmethodgetranges-method"></a>ISymUnmanagedMethod::GetRanges 메서드
제공 되는 위치가 문서에는 위치가이 메서드에 설명 되어 있는 Microsoft intermediate language (MSIL)의 범위에 해당 하는 시작 및 종료 오프셋된 쌍의 배열을 반환 합니다. 배열 정수 배열이 고 [시작, 끝, 시작, 끝] 형식. 범위 쌍의 수에는 2로 나눈 값 배열의 길이입니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetRanges(  
    [in]  ISymUnmanagedDocument* document,  
    [in]  ULONG32                line,  
    [in]  ULONG32                column,  
    [in]  ULONG32                cRanges,  
    [out] ULONG32                *pcRanges,  
    [out, size_is(cRanges),  
        length_is(*pcRanges)] ULONG32 ranges[]);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `document`  
 [in] 오프셋이 요청 된 문서입니다.  
  
 `line`  
 [in] 범위에 해당 하는 문서 줄.  
  
 `column`  
 [in] 범위에 해당 하는 문서 열입니다.  
  
 `cRanges`  
 [in] `ranges` 배열의 크기입니다.  
  
 `pcRanges`  
 [out] 에 대 한 포인터는 `ULONG32` 범위를 포함 하는 데 필요한 버퍼의 크기를 받는 합니다.  
  
 `ranges`  
 [out] 범위를 받는 버퍼에 대 한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
 메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 기타 오류 코드입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>참고 항목  
 [ISymUnmanagedMethod 인터페이스](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
