---
title: ICorDebugProcess5 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5
helpviewer_keywords:
- ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: 30a39d79-1f10-4328-9c5d-094ed824e2ba
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e3aed85e989313e4778e12a6f6bb789ccef49747
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugprocess5-interface"></a>ICorDebugProcess5 인터페이스
관리 되는 개체의 가비지 수집에 대 한 정보를 제공 하는 관리 되는 힙에 대 한 액세스를 지원 하기 위해 ICorDebugProcess 인터페이스를 확장 하 고 디버거 여부를 확인 하려면 응용 프로그램의 로컬 네이티브 이미지 캐시에서 이미지를 로드 합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[EnableNGenPolicy 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enablengenpolicy-method.md)|응용 프로그램에서 관리 되는 디버거가 실행 되는 동안 네이티브 이미지를 로드 하는 방식을 결정 하는 값을 설정 합니다.|  
|[EnumerateGCReferences 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerategcreferences-method.md)|프로세스의 가비지 수집 하는 모든 개체에 대 한 열거자를 가져옵니다.|  
|[EnumerateHandles 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md)|프로세스에서 개체 핸들에 대 한 열거자를 가져옵니다.|  
|[EnumerateHeap 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheap-method.md)|관리 되는 힙의 개체에 대 한 열거자를 가져옵니다.|  
|[EnumerateHeapRegions 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheapregions-method.md)|관리 영역에 대 한 열거자를 가져옵니다.|  
|[GetArrayLayout 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getarraylayout-method.md)|메모리에 배열 레이아웃에 대 한 정보를 가져옵니다.|  
|[GetGCHeapInformation 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md)|에 대 한 포인터를 가져옵니다는 [COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) 관리 되는 힙의 가비지 수집 될 개체에 대 한 정보가 포함 된 구조체입니다.|  
|[GetObject 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getobject-method.md)|관리 되는 힙의 개체에 대 한 포인터를 가져옵니다.|  
|[GetTypeFields 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefields-method.md)|유형 식별자를 기반으로 하는 형식에 대 한 필드 정보를 포함 하는 배열에 대 한 포인터를 가져옵니다.|  
|[GetTypeForTypeID 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefortypeid-method.md)|해당 형식 식별자를 기반으로 개체에 대 한 정보를 제공 하는 형식 개체를 가져옵니다.|  
|[GetTypeID 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypeid-method.md)|지정된 된 주소에서 개체에 대 한 형식 식별자를 가져옵니다.|  
|[GetTypeLayout 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypelayout-method.md)|유형 식별자를 기반으로 메모리에 개체의 레이아웃에 대 한 정보를 가져옵니다.|  
  
## <a name="remarks"></a>설명  
 이 인터페이스 ICorDebugProcess2, ICorDebugProcess를 논리적으로 확장 하 고 [ICorDebugProcess3](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess3-interface.md) 인터페이스입니다.  
  
> [!NOTE]
>  이 인터페이스는 다른 프로세스 또는 다른 컴퓨터에서 원격 호출을 지원 하지 않습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [디버깅 인터페이스](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [디버깅](../../../../docs/framework/unmanaged-api/debugging/index.md)
