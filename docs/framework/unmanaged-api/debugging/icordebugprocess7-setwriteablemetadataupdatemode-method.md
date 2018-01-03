---
title: "ICorDebugProcess7::SetWriteableMetadataUpdateMode 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: cpp
api_name: ICorDebugProcess7.SetWriteableMetadataUpdateMode
api_location: mscordbi.dll
api_type: COM
ms.assetid: 8589bba7-7304-45ba-9e31-7bf43dfd5c19
topic_type: apiref
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e901fd623893b9c03e1b5835adc72c6bd225ead4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocess7setwriteablemetadataupdatemode-method"></a>ICorDebugProcess7::SetWriteableMetadataUpdateMode 메서드
[.NET Framework 4.5.2 이상 버전에서 지원됨]  
  
 대상 프로세스 내에서 디버거가 메타데이터에 대한 메모리 내 업데이트를 처리하는 방법을 구성합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
HRESULT SetWriteableMetadataUpdateMode(  
   WriteableMetadataUpdateMode flags  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `flags`  
 A [WriteableMetadataUpdateMode](../../../../docs/framework/unmanaged-api/debugging/writeablemetadataupdatemode-enumeration.md) 대상 프로세스의 메타 데이터에 대 한 메모리 내 업데이트 표시 되는지 여부를 지정 하는 열거형 값 (`WriteableMetadataUpdateMode::AlwaysShowUpdates`) 않거나 표시 되지 않는 (`WriteableMetadataUpdateMode::LegacyCompatPolicy`)을 디버거에 합니다.  
  
## <a name="remarks"></a>설명  
 대상 프로세스의 메타데이터는 편집하며 계속하기, 프로파일러 또는 <xref:System.Reflection.Emit?displayProperty=nameWithType>에 의해 업데이트될 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICorDebugProcess7 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess7-interface.md)  
 [디버깅 인터페이스](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
