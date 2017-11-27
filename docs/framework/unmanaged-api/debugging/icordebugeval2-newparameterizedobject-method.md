---
title: "ICorDebugEval2::NewParameterizedObject 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugEval2.NewParameterizedObject
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugEval2::NewParameterizedObject
helpviewer_keywords:
- NewParameterizedObject method [.NET Framework debugging]
- ICorDebugEval2::NewParameterizedObject method [.NET Framework debugging]
ms.assetid: 3d705463-e640-4249-8036-4e8206d03cfe
topic_type: apiref
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 29b2470f50e96307ad91428fe1c712e7340baa32
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugeval2newparameterizedobject-method"></a>ICorDebugEval2::NewParameterizedObject 메서드
새 매개 변수가 있는 형식 개체를 인스턴스화하고 개체의 생성자 메서드를 호출 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT NewParameterizedObject (  
    [in] ICorDebugFunction     *pConstructor,  
    [in] ULONG32               nTypeArgs,  
    [in, size_is(nTypeArgs)] ICorDebugType *ppTypeArgs[],  
    [in] ULONG32               nArgs,  
    [in, size_is(nArgs)] ICorDebugValue *ppArgs[]  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pConstructor`  
 [in] 인스턴스화할 수 개체의 생성자를 나타내는 ICorDebugFunction 개체에 대 한 포인터입니다.  
  
 `nTypeArgs`  
 [in] 형식 인수 수가 전달 합니다.  
  
 `ppTypeArgs`  
 [in] 포인터의 배열을, 각 인스턴스화 중인 개체에 대 한 형식 인수를 나타내는 ICorDebugType 개체를 가리킵니다.  
  
 `nArgs`  
 [in] 인수 개수가 생성자에 전달 합니다.  
  
 `ppArgs`  
 [in] 생성자에 전달 되는 인수 값을 나타내는 ICorDebugValue 개체를 가리키는 각각 포인터의 배열입니다.  
  
## <a name="remarks"></a>설명  
 개체의 생성자 걸릴 수 있습니다 <xref:System.Type> 매개 변수입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
