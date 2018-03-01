---
title: "Silverlight용 CreateDebuggingInterfaceFromVersion 함수"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CreateDebuggingInterfaceFromVersion
helpviewer_keywords:
- CreateDebuggingInterfaceFromVersion function
- debugging API [Silverlight]
- Silverlight, debugging
ms.assetid: 35c7a18f-133a-4584-bd25-bb338568b0c6
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: c38171c5887bb207b3692e9fa92aa2be2bc72a27
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="createdebugginginterfacefromversion-function-for-silverlight"></a>Silverlight용 CreateDebuggingInterfaceFromVersion 함수
반환 되는 공용 언어 런타임 (CLR) 버전 문자열을 수락는 [CreateVersionStringFromModule 함수](../../../../docs/framework/unmanaged-api/debugging/createversionstringfrommodule-function.md), 해당 디버거 인터페이스를 반환 하 고 (일반적으로 [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)).  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT CreateDebuggingInterfaceFromVersion (  
    [in]  LPCWSTR      szDebuggeeVersion,  
    [out] IUnknown**   ppCordb,  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `szDebuggeeVersion`  
 [in] 반환 된 대상 디버기의 clr 버전 문자열의 [CreateVersionStringFromModule 함수](../../../../docs/framework/unmanaged-api/debugging/createversionstringfrommodule-function.md)합니다.  
  
 `ppCordb`  
 [out] COM 개체(`IUnknown`)에 대한 포인터의 포인터입니다. 이 개체를 캐스팅 됩니다는 [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) 반환 하기 전에 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 S_OK  
 `ppCordb`구현 하는 유효한 개체 참조는 [ICorDebug 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) 인터페이스입니다.  
  
 E_INVALIDARG  
 `szDebuggeeVersion` 또는 `ppCordb`가 null입니다.  
  
 CORDBG_E_DEBUG_COMPONENT_MISSING  
 CLR 디버깅에 필요한 구성 요소를 찾을 수 없습니다. 즉, mscordbi.dll 또는 mscordaccore.dll이 대상 CoreCLR.dll과 동일한 디렉터리에 없습니다.  
  
 CORDBG_E_INCOMPATIBLE_PROTOCOL  
 mscordbi.dll 또는 mscordaccore.dll이 대상 CoreCLR.dll과 동일한 버전이 아닙니다.  
  
 E_FAIL(또는 다른 E_ 반환 코드)  
 반환할 수 없습니다는 [ICorDebug 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)합니다.  
  
## <a name="remarks"></a>설명  
 반환된 인터페이스는 대상 프로세스의 CLR에 연결하고 CLR에서 실행 중인 관리 코드를 디버그하기 위한 기능을 제공합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** dbgshim.h  
  
 **라이브러리:** dbgshim.dll  
  
 **.NET framework 버전:** 3.5 SP1
