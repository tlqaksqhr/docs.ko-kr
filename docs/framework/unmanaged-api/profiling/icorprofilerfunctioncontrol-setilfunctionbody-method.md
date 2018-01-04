---
title: "ICorProfilerFunctionControl::SetILFunctionBody 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerFunctionControl.SetILFunctionBody
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerFunctionControl::SetILFunctionBody
helpviewer_keywords:
- ICorProfilerFunctionControl::SetILFunctionBody method [.NET Framework profiling]
- SetILFunctionBody method, ICorProfilerFunctionControl interface [.NET Framework profiling]
ms.assetid: 2c33f0f7-75b2-4c19-b2c7-c94b54997576
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 56d31b93385a087949121a76587ef6009cd9d51e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerfunctioncontrolsetilfunctionbody-method"></a>ICorProfilerFunctionControl::SetILFunctionBody 메서드
메서드의 공용 중간 언어(CIL) 본문을 바꿉니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT SetILFunctionBody(  
    [in]  ULONG   cbNewILMethodHeader,  
    [in, size_is(cbNewILMethodHeader)] LPCBYTE pbNewILMethodHeader);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `cbNewILMethodHeader`  
 [in] 헤더와 본문 다음에 오는 모든 구조를 포함한 새 CIL의 총 크기입니다.  
  
 `pbNewILMethodHeader`  
 [in] 새 CIL 헤더에 대한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 다음과 같은 특정 HRESULT를 반환합니다.  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|바꾸기에 성공했습니다.|  
  
## <a name="remarks"></a>설명  
 와 달리는 [icorprofilerinfo:: Setilfunctionbody](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilfunctionbody-method.md) 메서드는 `SetILFunctionBody` 메서드는 새 CIL 본문에 필요한 메모리를 관리 합니다. 즉, 프로파일러에서 제공 하는 CIL 본문에 없는지를 사용 하 여 할당 될 수는 [IMethodMalloc](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-interface.md) 인터페이스 또는 특정 범위 내에 할당 합니다. 어떤 힙에든 할당할 수 있습니다. 프로파일러 후 CIL 본문에 사용 되는 메모리를 확보할 수 `SetILFunctionBody` 반환 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICorProfilerFunctionControl 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-interface.md)
