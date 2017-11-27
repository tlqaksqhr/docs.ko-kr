---
title: ICorDebugArrayValue Interface1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugArrayValue
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugArrayValue interface
helpviewer_keywords: ICorDebugArrayValue interface [.NET Framework debugging]
ms.assetid: dc437751-7093-44e2-bfdc-191d9ce3c192
topic_type: apiref
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 13e226ccdcd6becc98d524c429b5cadae8d19c3e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugarrayvalue-interface1"></a>ICorDebugArrayValue Interface1
ICorDebugHeapValue 차원 배열이 나 다차원 배열을 나타내는의 하위 클래스입니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[GetBaseIndicies 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getbaseindicies-method.md)|배열의 각 차원에 대 한 기본 인덱스를 가져옵니다.|  
|[GetCount 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getcount-method.md)|배열에 있는 요소의 총 수를 가져옵니다.|  
|[GetDimensions 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getdimensions-method.md)|배열의 크기를 가져옵니다.|  
|[GetElement 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getelement-method.md)|배열에서 지정 된 요소를 나타내는 값을 가져옵니다.|  
|[GetElementAtPosition 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getelementatposition-method.md)|배열의 0부터 시작 하는 단일 차원 배열로 처리 하는 방법, 지정된 된 위치에 요소를 가져옵니다.|  
|[GetElementType 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getelementtype-method.md)|배열에 단순 유형의 요소를 가져옵니다.|  
|[GetRank 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getrank-method.md)|배열의 차수를 가져옵니다.|  
|[HasBaseIndicies 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-hasbaseindicies-method.md)|배열에 기본 인덱스가 있는지 여부를 결정 합니다.|  
  
## <a name="remarks"></a>설명  
 `ICorDebugArrayValue`1 차원 및 다차원 배열을 지원합니다.  
  
> [!NOTE]
>  이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [디버깅 인터페이스](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
