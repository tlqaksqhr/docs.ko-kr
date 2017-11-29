---
title: "ISymUnmanagedAsyncMethodPropertiesWriter 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: caa71820-8058-4b6a-93a2-25ee757d92d3
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: dd84ea5ee00df3e59d4907cdf97bc36b7f06d993
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedasyncmethodpropertieswriter-interface"></a>ISymUnmanagedAsyncMethodPropertiesWriter 인터페이스
각 메서드 기호에 대 한 선택적 async 메서드 정보를 정의할 수 있습니다. 항상 열려 있는 메서드를 함께 사용 즉, 호출 하는 사이 [OpenMethod 메서드](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md) 및 [CloseMethod 메서드](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closemethod-method.md)합니다.  
  
## <a name="syntax"></a>구문  
  
```idl  
[object,uuid(FC073774-1739-4232-BD56-A027294BEC15),pointer_default(unique)]interface ISymUnmanagedAsyncMethodPropertiesWriter : IUnknown  
```  
  
## <a name="methods"></a>메서드  
 이 인터페이스에는 다음과 같은 메서드가 있습니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[DefineAsyncStepInfo 메서드](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md)|비동기의 그룹을 정의 현재 메서드에 대 한 작업을 기다립니다.<br /><br /> 각 yield 오프셋 잠재적인 yield 식별 하는 await 반환 명령을 찾습니다. 각 `breakpointMethod` / `breakpointOffset` 쌍 식별 비동기 작업은 다시 시작, 다른 방법을에 있을 수 있습니다.|  
|[DefineCatchHandlerILOffset 메서드](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md)|IL 비동기 메서드를 래핑하는 컴파일러에서 생성 된 catch 처리기에 대 한 오프셋을 설정 합니다.<br /><br /> 생성 된 catch의 IL 오프셋 사용자 코드 메서드에서 발생할 수 있는 경우에 사용자가 아닌 코드 처럼 catch를 처리 하는 디버거에서 사용 됩니다. 특히 사용에 대 한 응답을 **CatchHandlerFound** 예외 이벤트입니다.|  
|[DefineKickoffMethod 메서드](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md)|비동기 작업을 시작 하는 시작 메서드를 설정 합니다.|  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>참고 항목  
 [진단 기호 저장소 인터페이스](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
