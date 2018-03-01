---
title: "IMethodMalloc::Alloc 메서드"
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
- IMethodMalloc.Alloc
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- IMethodMalloc::Alloc
helpviewer_keywords:
- IMethodMalloc::Alloc method [.NET Framework profiling]
- Alloc method, IMethodMalloc interface [.NET Framework profiling]
ms.assetid: 8653bd4c-2290-43d2-a3e1-cbbd50033f4f
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 26998e8b2e8648b4fb175f188540e7bc33c580c2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="imethodmallocalloc-method"></a>IMethodMalloc::Alloc 메서드
새 Microsoft MSIL (intermediate language) 함수 본문에 지정된 된 양의 메모리를 할당 하려고 시도 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
PVOID Alloc (  
    [in] ULONG   cb  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `cb`  
 [in] 메서드 본문에 할당할 바이트 수입니다.  
  
## <a name="remarks"></a>설명  
 할당 된 메모리가이 할당자와 연결 된 모듈의 기준 주소 보다 큰 주소에서 시작 됩니다. 즉, 각 할당자는 특정 모듈에 대 한 만들어지고 해당 기준 주소에서 양수 오프셋에서 메모리 할당을 시도 합니다. 경우 `Alloc` 모듈의 기준 주소 보다 큰 주소에서 바이트 수가 요청 된 할당에 실패 e_outofmemory가 실제 사용 가능한 메모리 공간의 크기에 관계 없이 반환 합니다.  
  
 `Alloc` 와 함께에서 사용할지 메서드는 [icorprofilerinfo:: Setilfunctionbody](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilfunctionbody-method.md) 메서드.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** WindSee [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [IMethodMalloc 인터페이스](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-interface.md)
