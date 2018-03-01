---
title: "ICorDebugEval::NewObject 메서드"
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
- ICorDebugEval.NewObject
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::NewObject
helpviewer_keywords:
- NewObject method [.NET Framework debugging]
- ICorDebugEval::NewObject method [.NET Framework debugging]
ms.assetid: ce3025e8-defa-4c5e-8298-f49d71fa5736
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 98c885e7ffd4b35bcc3af34757509910c78c0c90
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugevalnewobject-method"></a>ICorDebugEval::NewObject 메서드
새 개체 인스턴스를 할당 하 고 지정된 된 생성자 메서드를 호출 합니다.  
  
 이 메서드는.NET Framework 버전 2.0에서에서 사용 되지 않습니다. 사용 하 여 [icordebugeval2:: Newparameterizedobject](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobject-method.md) 대신 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT NewObject (  
    [in] ICorDebugFunction  *pConstructor,  
    [in] ULONG32            nArgs,  
    [in, size_is(nArgs)] ICorDebugValue *ppArgs[]  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pConstructor`  
 [in] 생성자가 호출 됩니다.  
  
 `nArgs`  
 [in] `ppArgs` 배열의 크기입니다.  
  
 `ppArgs`  
 [in] ICorDebugValue 개체의 생성자에 전달 될 인수를 나타내는 각각의 배열입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:** 1.0, 1.1  
  
## <a name="see-also"></a>참고 항목  
 [NewParameterizedObject 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobject-method.md)
