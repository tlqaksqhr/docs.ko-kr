---
title: "ICorDebugGCReferenceEnum 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugGCReferenceEnum
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugGCReferenceEnum
helpviewer_keywords: ICorDebugGCReferenceEnum interface [.NET Framework debugging]
ms.assetid: 5f3c91c9-c035-454f-96cc-011cab1ea06b
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 89e516bba3d9dd8a13e1beb2bdc231b0a639dbf0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebuggcreferenceenum-interface"></a>ICorDebugGCReferenceEnum 인터페이스
가비지 수집되는 개체에 대한 열거자를 제공합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[Next 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-next-method.md)|지정된 된 수의 가져옵니다 [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) 가비지 수집 되는 개체에 대 한 정보가 포함 된 인스턴스.|  
  
## <a name="remarks"></a>설명  
 `ICorDebugGCReferenceEnum` "ICorDebugEnum" 인터페이스를 구현 하는 인터페이스입니다.  
  
 `ICorDebugGCReferenceEnum` 인스턴스 채워집니다 [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) 호출 하 여 인스턴스는 [icordebugprocess5:: Enumerategcreferences](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerategcreferences-method.md) 메서드. [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) 호출 하 여 개체를 열거할 수는 [ICorDebugGCReference::Next](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-next-method.md) 메서드.  
  
 [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) 이 메서드에 의해 채워진 컬렉션에 개체 세 가지 종류의 개체를 나타냅니다.  
  
-   모든 관리 되는 스택 개체입니다. 여기 공용 언어 런타임에서 생성 된 개체를 비롯 하 여 관리 코드에 대 한 라이브 참조가 포함 됩니다.  
  
-   핸들 테이블의 개체입니다. 이 강력한 참조를 포함 (`HNDTYPE_STRONG` 및 `HNDTYPE_REFCOUNT`) 및 모듈의 정적 변수.  
  
-   종료자 큐의 개체입니다. 종료자 큐는 종료 자가 실행 될 때까지 개체 루트입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [디버깅 인터페이스](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
