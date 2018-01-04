---
title: "ISymUnmanagedENCUpdate::UpdateMethodLines 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedENCUpdate.UpdateMethodLines
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedENCUpdate::UpdateMethodLines
helpviewer_keywords:
- UpdateMethodLines method [.NET Framework debugging]
- ISymUnmanagedENCUpdate::UpdateMethodLines method [.NET Framework debugging]
ms.assetid: 275ef87b-0b53-49f9-af6b-58506335dc06
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2e8ffecba62b6531c852e6510013ba56b9258b64
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedencupdateupdatemethodlines-method"></a>ISymUnmanagedENCUpdate::UpdateMethodLines 메서드
다시 컴파일되지 않은, 하지만 해당 줄 독립적으로 이동 하는 방법에 대 한 줄 정보를 업데이트할 수 있습니다. 각 문에 대 한 델타 허용 됩니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT UpdateMethodLines(  
    [in]  mdMethodDef  mdMethodToken,  
    [in, size_is(cDeltas)] INT32*  pDeltas,  
    [in]  ULONG        cDeltas);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `mdMethodToken`  
 [in] 메타 데이터 메서드 토큰입니다.  
  
 `pDeltas`  
 [in] 배열 `INT32` 델타 메서드가 각 시퀀스 요소를 나타내는 값입니다.  
  
 `cDeltas`  
 [in] A `ULONG` 크기를 포함 하는 `pDeltas` 매개 변수입니다.  
  
## <a name="return-value"></a>반환 값  
 메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 기타 오류 코드입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>참고 항목  
 [ISymUnmanagedENCUpdate 인터페이스](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-interface.md)
