---
title: "ISymUnmanagedWriter2::DefineLocalVariable2 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter2.DefineLocalVariable2
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter2::DefineLocalVariable2
helpviewer_keywords:
- ISymUnmanagedWriter2::DefineLocalVariable2 method [.NET Framework debugging]
- DefineLocalVariable2 method [.NET Framework debugging]
ms.assetid: e774eefe-858c-4362-8d2d-28ebf2ba1a24
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1124b57bed16e349c753be872c1b709a287e6237
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedwriter2definelocalvariable2-method"></a>ISymUnmanagedWriter2::DefineLocalVariable2 메서드
현재 어휘 범위에 단일 변수를 정의합니다. 이 메서드는 범위에 걸쳐 홈이 여러 개 있는 동일한 이름의 변수에 대 한 여러 번 호출할 수 있습니다. 그러나이 경우의 값은 `startOffset` 및 `endOffset` 매개 변수는 겹치지 않아야 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT DefineLocalVariable2(  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] mdSignature  sigToken,  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3,  
    [in] ULONG32      startOffset,  
    [in] ULONG32      endOffset);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `name`  
 [in] 지역 변수 이름입니다.  
  
 `attributes`  
 [in] 지역 변수 특성입니다.  
  
 `sigToken`  
 [in] 서명의 메타 데이터 토큰입니다.  
  
 `addrKind`  
 [in] 주소 유형입니다.  
  
 `addr1`  
 [in] 매개 변수 사양에 대 한 첫 번째 주소입니다.  
  
 `addr2`  
 [in] 매개 변수 사양에 대 한 두 번째 주소입니다.  
  
 `addr3`  
 [in] 매개 변수 사양에 대 한 세 번째 주소입니다.  
  
 `startOffset`  
 [in] 변수의 시작 오프셋입니다. 이 매개 변수는 선택적 요소입니다. 0 이면이 매개 변수가 무시 되 고 변수에 전체 범위에서 정의 됩니다. 0이 아닌 값 이면 변수는 현재 범위의 오프셋 내에 속합니다.  
  
 `endOffset`  
 [in] 변수의 끝 오프셋입니다. 이 매개 변수는 선택적 요소입니다. 0 이면이 매개 변수가 무시 되 고 변수에 전체 범위에서 정의 됩니다. 0이 아닌 값 이면 변수는 현재 범위의 오프셋 내에 속합니다.  
  
## <a name="return-value"></a>반환 값  
 메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 기타 오류 코드입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** CorSym.idl  
  
## <a name="see-also"></a>참고 항목  
 [ISymUnmanagedWriter2 인터페이스](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-interface.md)  
 [DefineLocalVariable 메서드](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-definelocalvariable-method.md)
