---
title: "ISymUnmanagedWriter2::DefineGlobalVariable2 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter2.DefineGlobalVariable2
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter2::DefineGlobalVariable2
helpviewer_keywords:
- ISymUnmanagedWriter2::DefineGlobalVariable2 method [.NET Framework debugging]
- DefineGlobalVariable2 method [.NET Framework debugging]
ms.assetid: 04d569d6-a151-4957-9872-f3f694c3e4a9
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 617e3f03f4b1c126a56b47db34ec7044bea8c58b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedwriter2defineglobalvariable2-method"></a>ISymUnmanagedWriter2::DefineGlobalVariable2 메서드
단일 전역 변수를 정의 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT DefineGlobalVariable2(  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] mdSignature  sigToken,  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `name`  
 [in] 전역 변수 이름입니다.  
  
 `attributes`  
 [in] 전역 변수 특성입니다.  
  
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
  
## <a name="return-value"></a>반환 값  
 메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 기타 오류 코드입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** CorSym.idl  
  
## <a name="see-also"></a>참고 항목  
 [ISymUnmanagedWriter2 인터페이스](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-interface.md)  
 [DefineGlobalVariable 메서드](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-defineglobalvariable-method.md)
