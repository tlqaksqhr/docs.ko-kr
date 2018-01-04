---
title: "ICorProfilerInfo4::GetCodeInfo3 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo4.GetCodeInfo3
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo4::GetCodeInfo3
helpviewer_keywords:
- GetCodeInfo3 method, ICorProfilerInfo4 interface [.NET Framework profiling]
- ICorProfilerInfo4::GetCodeInfo3 method [.NET Framework profiling]
ms.assetid: bb8c105e-4d9a-4684-8c05-ed6909cc1b8c
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b669714774ecfccad436f064350569d27ef13883
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfo4getcodeinfo3-method"></a>ICorProfilerInfo4::GetCodeInfo3 메서드
지정된 함수의 JIT 다시 컴파일된 버전과 연결된 네이티브 코드의 범위를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetCodeInfo3(  
    [in]  FunctionID functionID,  
    [in]  ReJITID reJitId,  
    [in]  ULONG32 cCodeInfos,  
    [out] ULONG32 *pcCodeInfos,  
    [out, size_is(cCodeInfos), length_is(*pcCodeInfos)]  
    COR_PRF_CODE_INFO codeInfos[]);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `functionID`  
 [in] 네이티브 코드가 연결된 함수의 ID입니다.  
  
 `reJitId`  
 [in] JIT 다시 컴파일된 함수의 ID입니다.  
  
 `cCodeInfos`  
 [in] `codeInfos` 배열의 크기입니다.  
  
 `pcCodeInfos`  
 [out] 총 수에 대 한 포인터 [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) 사용할 수 있는 구조입니다.  
  
 `codeInfos`  
 [out] 호출자가 제공한 버퍼입니다. 메서드가 반환된 후에는 각각 네이티브 코드 블록을 설명하는 `COR_PRF_CODE_INFO` 구조체의 배열을 포함합니다.  
  
## <a name="remarks"></a>설명  
 `GetCodeInfo3` 메서드는 [GetCodeInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getcodeinfo2-method.md)제외 하 고 지정 된 IP 주소를 포함 하는 함수의 JIT 다시 컴파일된 ID를 가져오게 됩니다.  
  
> [!NOTE]
>  `GetCodeInfo3`가비지 수집을 트리거할 수 있는 반면 [GetCodeInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getcodeinfo2-method.md) 되지 것입니다. 자세한 내용은 참조는 [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE](../../../../docs/framework/unmanaged-api/profiling/corprof-e-unsupported-call-sequence-hresult.md) HRESULT입니다.  
  
 범위는 CIL(Common Intermediate Language) 오프셋의 오름차순으로 정렬됩니다.  
  
 후 `GetCodeInfo3` 반환 되어 있는지 확인 해야 합니다는 `codeInfos` 버퍼가 포함 모두 만큼 충분히 큰지는 [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) 구조입니다. 이렇게 하려면 `cCodeInfos` 값을 `cchName` 매개 변수의 값과 비교합니다. 경우 `cCodeInfos` 의 크기로 나눈는 [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) 구조 보다 작으면 `pcCodeInfos`, 더 큰 할당 `codeInfos` 버퍼를 업데이트 `cCodeInfos` 더 큰 새 크기로 및 호출 `GetCodeInfo3` 다시 실행 합니다.  
  
 또는 길이가 0인 `codeInfos` 버퍼로 `GetCodeInfo3`을 먼저 호출하여 올바른 버퍼 크기를 구합니다. 설정할 수 있습니다는 `codeInfos` 버퍼 크기에 반환 된 값을 `pcCodeInfos`를 곱한 값으로 크기는 [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) 구조 및 호출 `GetCodeInfo3` 다시 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [GetCodeInfo2 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getcodeinfo2-method.md)  
 [ICorProfilerInfo4 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)  
 [프로파일링 인터페이스](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [프로파일링](../../../../docs/framework/unmanaged-api/profiling/index.md)
