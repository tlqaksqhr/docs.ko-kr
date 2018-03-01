---
title: "WriteableMetadataUpdateMode 열거형"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- cpp
api_name:
- WriteableMetadataUpdateMode
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 6758f4d3-6bc7-4c99-8582-e9be00566784
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b32eca0bec61e6c7b6fcf83bb05650c30c2f9f16
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="writeablemetadataupdatemode-enumeration"></a>WriteableMetadataUpdateMode 열거형
[.NET Framework 4.5.2 이상 버전에서 지원됨]  
  
 메타데이터에 대한 메모리 내 업데이트가 디버거에 표시되는지 여부를 지정하는 값을 제공합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
typedef enum WriteableMetadataUpdateMode {  
   LegacyCompatPolicy,  
   AlwaysShowUpdates  
} WriteableMetadataUpdateMode;  
```  
  
## <a name="members"></a>멤버  
  
|멤버 이름|설명|  
|-----------------|-----------------|  
|`LegacyCompatPolicy`|메타데이터에 대한 메모리 내 업데이트를 표시할 때 .NET Framework 이전 버전과의 호환성을 유지합니다. 자세한 내용은 설명 부분을 참조하십시오.|  
|`AlwaysShowUpdates`|메타데이터에 대한 메모리 내 업데이트를 디버거에 표시합니다.|  
  
## <a name="remarks"></a>설명  
 멤버는 `WriteableMetadataUpdateMode` 열거형에 전달 될 수는 [SetWriteableMetadataUpdateMode](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess7-setwriteablemetadataupdatemode-method.md) 메타 데이터는 대상 프로세스의 메모리 내 업데이트가 있는지 여부를 제어 하는 메서드를 디버거에 표시 됩니다.  
  
 `LegacyCompatPolicy` 옵션은 .NET Framework 4.5.2 이전 버전에서와 같은 동작을 적용합니다. 이로 인해 업데이트의 메타데이터가 표시되지 않는 경우가 많습니다. 그러나 여러 디버깅 메서드를 호출하면 디버거가 업데이트를 표시하도록 암시적으로 강제 지정됩니다. 예를 들어, 디버거 통과 하는 경우 [icordebugilframe:: Getlocalvariable](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getlocalvariable-method.md) 모듈의 현재 상태와 일치 하는 스냅숏으로 업데이트 됩니다 메서드의 원래 메타 데이터를 모든 메타 데이터에 없는 변수의 인덱스는 프로세스입니다. 다시 말해서, `LegacyCompatPolicy` 옵션을 사용하는 경우에는 디버거가 관리되지 않는 디버깅 API의 다른 부분을 사용하는 방식에 따라 사용 가능한 메타데이터 업데이트가 표시되지 않을 수도 있고 일부 또는 모든 업데이트가 표시될 수도 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [디버깅 열거형](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)  
 [SetWriteableMetadataUpdateMode 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess7-setwriteablemetadataupdatemode-method.md)
