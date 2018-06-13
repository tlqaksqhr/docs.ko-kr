---
title: ICorProfilerInfo7::GetInMemorySymbolsLength 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo7.GetInMemorySymbolsLength
api_location:
- mscorwks.dll
- icorprof.idl
api_type:
- COM
ms.assetid: d62c4a4c-8a62-45aa-8f01-a8387cf36159
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5e662270fc8db3fb85e058e8d4f3346f58f79bb8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33457963"
---
# <a name="icorprofilerinfo7getinmemorysymbolslength-method"></a>ICorProfilerInfo7::GetInMemorySymbolsLength 메서드
[.NET Framework 4.6.1 이상 버전에서 지원됨]  
  
 메모리 내 기호 스트림의 길이 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetInMemorySymbolsLength(  
        [in] ModuleID moduleId,  
        [out] DWORD* pCountSymbolBytes  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `moduleId`  
 [in] 메모리 스트림을 포함 하는 모듈의 식별자입니다.  
  
 pCountSymbolBytes  
 [out] 에 대 한 포인터는 `DWORD` 메서드가 반환 될 때 바이트에서 스트림의 길이 포함 하는 값입니다.  
  
## <a name="return-value"></a>반환 값  
 메서드가 반환 `S_OK` 경우 메모리 스트림의 길이 확인할 수 없는 경우에 영 (0).  
  
 메서드가 반환 `CORPROF_E_MODULE_IS_DYNAMIC` 메서드를 사용 하 여 만들어진 경우 <xref:System.Reflection.Emit?displayProperty=nameWithType>합니다.  
  
## <a name="remarks"></a>설명  
 스트림의 길이에 위치한 모듈에 있는 경우 메모리 기호, `pCountSymbolBytes`합니다. 모듈에는 메모리에 기호, 없는 경우 `*pCountSymbolBytes = 0`합니다.  
  
> [!NOTE]
>  현재 구현에서는 Reflection.Emit를 지원 하지 않습니다. 메서드가 반환 하는 경우 모듈 Reflection.Emit를 사용 하 여 만든, `CORPROF_E_MODULE_IS_DYNAMIC`합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICorProfilerInfo7 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md)
