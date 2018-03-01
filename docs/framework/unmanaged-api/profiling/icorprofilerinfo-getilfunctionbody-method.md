---
title: "ICorProfilerInfo::GetILFunctionBody 메서드"
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
- ICorProfilerInfo.GetILFunctionBody
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetILFunctionBody
helpviewer_keywords:
- GetILFunctionBody method [.NET Framework profiling]
- ICorProfilerInfo::GetILFunctionBody method [.NET Framework profiling]
ms.assetid: e29b46bc-5fdc-4894-b0c2-619df4b65ded
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 035c2a1926d80b4aaea57523b4ecdd3da6873efe
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfogetilfunctionbody-method"></a>ICorProfilerInfo::GetILFunctionBody 메서드
헤더에서 시작 되는 Microsoft MSIL (intermediate language) 코드에서 메서드 본문에 대 한 포인터를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetILFunctionBody(  
    [in]  ModuleID    moduleId,  
    [in]  mdMethodDef methodId,  
    [out] LPCBYTE     *ppMethodHeader,  
    [out] ULONG       *pcbMethodSize);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `moduleId`  
 [in] 함수가 상주 하는 모듈의 ID입니다.  
  
 `methodId`  
 [in] 메서드에 대 한 메타 데이터 토큰입니다.  
  
 `ppMethodHeader`  
 [out] 메서드 헤더에 대 한 포인터입니다.  
  
 `pcbMethodSize`  
 [out] 크기의 메서드를 지정 하는 정수입니다.  
  
## <a name="remarks"></a>설명  
 메서드는 현재 모듈에 의해 범위가 지정 됩니다. 때문에 `GetILFunctionBody` 메서드 전에 공용 언어 런타임 (CLR)에서 로드 된 MSIL 코드에 대 한 도구 액세스를 제공 하도록 설계 되었습니다, 메서드의 메타 데이터 토큰을 사용 하 여 원하는 인스턴스를 찾으려고 합니다.  
  
 `GetILFunctionBody`경우에 CORPROF_E_FUNCTION_NOT_IL HRESULT를 반환할 수 있습니다는 `methodId` 모든 MSIL 코드 (추상 메서드 또는 플랫폼 호출 (PInvoke) 메서드 같은) 없이 메서드를 가리킵니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICorProfilerInfo 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
