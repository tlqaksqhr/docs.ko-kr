---
title: ICorDebugILFrame Interface1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugILFrame
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugILFrame
helpviewer_keywords: ICorDebugILFrame interface [.NET Framework debugging]
ms.assetid: d5cf5056-da4d-4629-914d-afe42a5393df
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d8d370fa971f698eb694127c72ff96499b85143d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugilframe-interface1"></a>ICorDebugILFrame Interface1
Microsoft MSIL (intermediate language) 코드의 스택 프레임을 나타냅니다. 이 인터페이스는 ICorDebugFrame 인터페이스의 서브 클래스입니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[CanSetIP 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-cansetip-method.md)|명령 포인터 지정된 된 오프셋된 위치를 설정할 수 있는지 여부를 나타내는 값을 가져옵니다.|  
|[EnumerateArguments 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-enumeratearguments-method.md)|이 프레임에는 인수에 대 한 열거자를 가져옵니다.|  
|[EnumerateLocalVariables 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-enumeratelocalvariables-method.md)|이 프레임에서 지역 변수에 대 한 열거자를 가져옵니다.|  
|[GetArgument 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getargument-method.md)|MSIL이 스택 프레임에서 지정 된 인수 값을 가져옵니다.|  
|[GetIP 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getip-method.md)|명령 포인터의 값 및 명령 포인터의 값을 가져온 방법에 대해 설명 하는 비트 조합 값을 가져옵니다.|  
|[GetLocalVariable 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getlocalvariable-method.md)|MSIL이 스택 프레임에서 지정 된 로컬 변수의 값을 가져옵니다.|  
|[GetStackDepth 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getstackdepth-method.md)|구현되지 않았습니다.|  
|[GetStackValue 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getstackvalue-method.md)|구현되지 않았습니다.|  
|[SetIP 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md)|MSIL 코드에서 지정된 된 오프셋된 위치를 명령 포인터를 설정합니다.|  
  
## <a name="remarks"></a>설명  
 `ICorDebugILFrame` 인터페이스는 특수 한 ICorDebugFrame 인터페이스입니다. 사용 되는 프레임 컴파일된 MSIL 코드 프레임 하거나 타임 (JIT). JIT 컴파일 프레임 둘 다 구현는 `ICorDebugILFrame` 인터페이스와 ICorDebugNativeFrame 인터페이스입니다.  
  
> [!NOTE]
>  이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [디버깅 인터페이스](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
