---
title: "ICorDebugILFrame3::GetReturnValueForILOffset 메서드"
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
- csharp
- vb
api_name:
- ICorDebugILFrame3.GetReturnValueForILOffset
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 06522727-5f64-4391-9331-11386883c352
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: c58319de99bdd8d7cce0ea55ccb3140a31a39bd0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugilframe3getreturnvalueforiloffset-method"></a>ICorDebugILFrame3::GetReturnValueForILOffset 메서드
함수의 반환 값을 캡슐화 하는 "ICorDebugValue" 개체를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
HRESULT GetReturnValueForILOffset(  
    ULONG32 ILoffset,   
    [out] ICorDebugValue **ppReturnValue  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `ILOffset`  
 IL 오프셋입니다. 설명 부분을 참조하세요.  
  
 `ppReturnValue`  
 함수 호출의 반환 값에 대 한 정보를 제공 하는 "ICorDebugValue" 인터페이스 개체의 주소에 대 한 포인터입니다.  
  
## <a name="remarks"></a>설명  
 이 메서드는와 함께 사용 되는 [icordebugcode3:: Getreturnvalueliveoffset](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md) 메서드의 반환 값을 가져오는 메서드를 합니다. 다음 두 코드 예제와 같이 반환 값은 무시 되는 메서드의 경우 특히 유용 합니다. 첫 번째 호출에서 <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> 메서드, 하지만 메서드의 반환 값을 무시 합니다.  
  
 [!code-csharp[Unmanaged.Debugging.MRV#1](../../../../samples/snippets/csharp/VS_Snippets_CLR/unmanaged.debugging.mrv/cs/mrv1.cs#1)]
 [!code-vb[Unmanaged.Debugging.MRV#1](../../../../samples/snippets/visualbasic/VS_Snippets_CLR/unmanaged.debugging.mrv/vb/mrv1.vb#1)]  
  
 두 번째 예에서는 디버깅에 훨씬 더 일반적인 문제를 보여 줍니다. 메서드를 메서드 호출에서 인수로 사용 때문에 디버거는 호출된 된 메서드가 단계별로 실행할 때에 해당 반환 값은 액세스할 수 있습니다. 대부분의 경우에서 특히 호출된 된 메서드에 외부 라이브러리에 정의 된 경우는 불가능 합니다.  
  
 [!code-csharp[Unmanaged.Debugging.MRV#2](../../../../samples/snippets/csharp/VS_Snippets_CLR/unmanaged.debugging.mrv/cs/mrv2.cs#2)]
 [!code-vb[Unmanaged.Debugging.MRV#2](../../../../samples/snippets/visualbasic/VS_Snippets_CLR/unmanaged.debugging.mrv/vb/mrv2.vb#2)]  
  
 전달 하는 경우는 [icordebugcode3:: Getreturnvalueliveoffset](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md) 메서드 IL 오프셋 함수 호출 사이트에는 하나 이상의 네이티브 오프셋 간의 반환 합니다. 다음 디버거 함수에서 네이티브 이러한 오프셋에서 중단점을 설정할 수 있습니다. 디버거는 중단점에 도달 하는 경우 반환 값을이 메서드에 전달 된 동일한 IL 오프셋에 전달할 수 있습니다. 디버거는 모든 중단점을 설정 하는 것을 선택을 취소 한 다음 됩니다.  
  
> [!WARNING]
>  [icordebugcode3:: Getreturnvalueliveoffset 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md) 및 `ICorDebugILFrame3::GetReturnValueForILOffset` 방법을 사용 하는 참조 형식만 대 한 반환 값 정보를 얻을 수 있습니다. 값 형식에서의 반환 값 정보 검색 (에서 파생 되는 모든 형식 즉, <xref:System.ValueType>) 지원 되지 않습니다.  
  
 지정 된 IL 오프셋은 `ILOffset` 매개 변수는 함수 호출 사이트에 있어야 하 고 디버기를 중지 하 여 반환한 네이티브 오프셋에 중단점을 설정한에서 해야는 [icordebugcode3:: Getreturnvalueliveoffset](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md) 메서드 에 대 한 동일한 IL 오프셋입니다. 지정된 된 IL 오프셋에 대 한 올바른 위치에 중지 되지 않으면 디버기 API 실패 합니다.  
  
 함수 호출 값을 반환 하지 않는 경우 API가 실패 합니다.  
  
 `ICorDebugILFrame3::GetReturnValueForILOffset` 메서드는 x86 기반에 대해서만 사용할 수 및 AMD64 시스템.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [GetReturnValueLiveOffset 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md)  
 [ICorDebugILFrame3 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-interface.md)
