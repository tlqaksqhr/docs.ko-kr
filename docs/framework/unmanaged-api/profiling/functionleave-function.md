---
title: "FunctionLeave 함수"
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
- FunctionLeave
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionLeave
helpviewer_keywords:
- FunctionLeave function [.NET Framework profiling]
ms.assetid: 18e89f45-e068-426a-be16-9f53a4346860
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 14b8c1c5d36178e672bee363a192cd4eae435467
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="functionleave-function"></a>FunctionLeave 함수
호출자에 게 반환 하는 함수 인지 프로파일러에 알립니다.  
  
> [!NOTE]
>  `FunctionLeave` 함수는.NET Framework 2.0에서 사용 되지 않습니다. 작동 하도록 하는 계속 되지만 성능 저하가 발생 합니다. 사용 하 여 [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md) 함수를 대신 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
void __stdcall FunctionLeave (  
    [in] FunctionID funcID  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `funcID`  
 [in] 식별자가 반환 하는 함수입니다.  
  
## <a name="remarks"></a>설명  
 `FunctionLeave` 는 콜백 함수입니다; 구현 해야 합니다. 구현을 사용 해야 합니다는 `__declspec`(`naked`) 저장소 클래스 특성입니다.  
  
 실행 엔진은이 함수를 호출 하기 전에 레지스터를 저장 하지 않습니다.  
  
-   항목에는 부동 소수점 FPU (단위) 포함 하 여 사용 하는 모든 레지스터를 저장 해야 합니다.  
  
-   끝낼 때 호출자에 의해 밀어넣은 모든 매개 변수 팝 하 여 스택을 복원 해야 합니다.  
  
 구현 `FunctionLeave` 가비지 수집이 지연 될 수 있으므로 차단 하지 않아야 합니다. 스택 가비지 컬렉션에 적합 한 상태의 수 없을 수도 구현 가비지 수집을 시도 하지 않아야 합니다. 런타임이 될 때까지 차단 됩니다 가비지 수집을 시도 하는 경우 `FunctionLeave` 반환 합니다.  
  
 또한는 `FunctionLeave` 함수를 호출 해서는 안에서 또는 관리 코드에 관리 되는 메모리를 할당 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorProf.idl  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:** 1.0, 1.1  
  
## <a name="see-also"></a>참고 항목  
 [FunctionEnter2 함수](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)  
 [FunctionLeave2 함수](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)  
 [FunctionTailcall2 함수](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)  
 [SetEnterLeaveFunctionHooks2 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)  
 [프로파일링 전역 정적 함수](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
