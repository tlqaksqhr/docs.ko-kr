---
title: "ICorDebugFunction2::GetVersionNumber 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugFunction2.GetVersionNumber
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugFunction2::GetVersionNumber
helpviewer_keywords:
- ICorDebugFunction2::GetVersionNumber method [.NET Framework debugging]
- GetVersionNumber method, ICorDebugFunction2 interface [.NET Framework debugging]
ms.assetid: e3a1ce48-9bb9-4ed6-a5fe-5e1819a6333f
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 37b9e34174d88be08c92c54906ebd20977dc266a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugfunction2getversionnumber-method"></a>ICorDebugFunction2::GetVersionNumber 메서드
이 함수의 편집 하며 계속 하기 버전을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetVersionNumber (  
    [out] ULONG32   *pnVersion  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pnVersion`  
 [out] 이 ICorDebugFunction2 개체로 표시 되는 함수의 버전 번호는 정수에 대 한 포인터입니다.  
  
## <a name="remarks"></a>설명  
 런타임에서 수행 된 각 모듈에 디버그 세션 중 편집 수를 추적 합니다. 하나는 함수의 버전 번호는 함수에 적용 된 편집의 수를 초과 합니다. 함수의 원래 버전은 1입니다. 숫자는 모듈에 대 한 될 때마다 증가 [icordebugmodule2:: Applychanges](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-applychanges-method.md) 해당 모듈에서 호출 됩니다. 따라서 첫 번째 및 세 번째 호출에서 함수 본문이 바뀌었으면 `ICorDebugModule2::ApplyChanges`, `GetVersionNumber` 버전 1, 2, 또는 해당 함수에 대해 4 하지만 하지 버전 3 반환할 수 있습니다. (해당 함수 버전이 3 없는 것입니다.)  
  
 버전 번호는 각 모듈에 대해 개별적으로 추적 됩니다. 따라서 모듈 1 및 모듈 2 없음에 4 개의 편집 작업을 수행 하는 경우 다음 편집 모듈 1에는 모듈 1의 모든 편집 된 함수에 6의 버전 번호를 할당 합니다. 모듈 2를 편집 하는 동일한 모듈 2에 포함 된 함수 2의 버전 번호를 받게 됩니다.  
  
 하 여 가져온 버전 번호는 `GetVersionNumber` 메서드를 여 가져온 보다 낮을 수도 [icordebugfunction:: Getcurrentversionnumber](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getcurrentversionnumber-method.md)합니다.  
  
 [icordebugcode:: Getversionnumber](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getversionnumber-method.md) 메서드가 동일한 작업을 수행할 `ICorDebugFunction2::GetVersionNumber`합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
