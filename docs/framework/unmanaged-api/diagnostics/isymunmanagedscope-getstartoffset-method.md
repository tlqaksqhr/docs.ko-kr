---
title: ISymUnmanagedScope::GetStartOffset 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetStartOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetStartOffset
helpviewer_keywords:
- GetStartOffset method, ISymUnmanagedScope interface [.NET Framework debugging]
- ISymUnmanagedScope::GetStartOffset method [.NET Framework debugging]
ms.assetid: da6bbc75-94d1-4354-9722-0d455b4428fb
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 19d116825efc4eb2ec1de22f232f46f8fb0fdf18
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="isymunmanagedscopegetstartoffset-method"></a>ISymUnmanagedScope::GetStartOffset 메서드
이 범위에 대 한 시작 오프셋을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetStartOffset(  
    [out, retval] ULONG32* pRetVal);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pRetVal`  
 [out] 에 대 한 포인터는 `ULONG32` 시작 오프셋을 포함 하는 합니다.  
  
## <a name="return-value"></a>반환 값  
 메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 기타 오류 코드입니다.  
  
## <a name="requirements"></a>요구 사항  
 **Header:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>참고 항목  
 [ISymUnmanagedScope 인터페이스](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)  
 [GetEndOffset 메서드](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getendoffset-method.md)
