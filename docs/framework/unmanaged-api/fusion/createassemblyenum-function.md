---
title: "CreateAssemblyEnum 함수"
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
- CreateAssemblyEnum
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- CreateAssemblyEnum
helpviewer_keywords:
- CreateAssemblyEnum function [.NET Framework fusion]
ms.assetid: 3506df38-6cea-42f6-946e-4287863bcfb3
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3719da442b2c2c589772a0bc19cec3efb4e6dace
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="createassemblyenum-function"></a>CreateAssemblyEnum 함수
에 대 한 포인터를 가져옵니다는 [IAssemblyEnum](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md) 지정 된 어셈블리에 있는 개체를 열거할 수 있는 인스턴스 [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT CreateAssemblyEnum (  
    [out] IAssemblyEnum  **pEnum,  
    [in]  IUnknown       *pUnkReserved,  
    [in]  IAssemblyName  *pName,  
    [in]  DWORD          dwFlags,  
    [in]  LPVOID         pvReserved  
 );  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pEnum`  
 [out] 요청 된 포함 된 메모리 위치에 대 한 포인터 `IAssemblyEnum` 포인터입니다.  
  
 `pUnkReserved`  
 [in] 다음 버전의 확장에 대 한 예약 되어 있습니다. `pUnkReserved`null 참조 여야 합니다.  
  
 `pName`  
 [in] `IAssemblyName` 요청된 된 어셈블리의 합니다. 이 이름은 열거형 필터링 사용 됩니다. 전역 어셈블리 캐시의 모든 어셈블리를 열거 null 일 수 있습니다.  
  
 `dwFlags`  
 [in] 열거자의 동작을 수정 하기 위한 플래그입니다. 이 매개 변수에 포함에서 정확히 하나의 비트만 [ASM_CACHE_FLAGS](../../../../docs/framework/unmanaged-api/fusion/asm-cache-flags-enumeration.md) 열거 합니다.  
  
 `pvReserved`  
 [in] 다음 버전의 확장에 대 한 예약 되어 있습니다. `pvReserved`null 참조 여야 합니다.  
  
## <a name="remarks"></a>설명  
 `dwFlags` 에서 정확히 한 비트를 포함 하는 매개 변수는 `ASM_CACHE_FLAGS` 열거형입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** Fusion.h  
  
 **라이브러리:** MsCorEE.dll에 리소스로 포함  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [IAssemblyEnum 인터페이스](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md)  
 [IAssemblyName 인터페이스](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)  
 [Fusion 전역 정적 함수](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
