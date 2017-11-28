---
title: "ICorDebugFunction::GetILCode 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugFunction.GetILCode
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugFunction::GetILCode
helpviewer_keywords:
- ICorDebugFunction::GetILCode method [.NET Framework debugging]
- GetILCode method [.NET Framework debugging]
ms.assetid: f794dd47-a7cd-47f6-96e9-a41a4dae8e72
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: da955f6eb8e7480fb23192e1a77341166dd40f3b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugfunctiongetilcode-method"></a>ICorDebugFunction::GetILCode 메서드
ICorDebugCode 인스턴스를이 ICorDebugFunction 개체와 연결 된 Microsoft MSIL (intermediate language) 코드를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetILCode (  
    [out] ICorDebugCode **ppCode  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `ppCode`  
 [out] 에 대 한 포인터는 `ICorDebugCode` 인스턴스에 지정 하거나 함수가 MSIL로 컴파일되지 않은 경우 null입니다.  
  
## <a name="remarks"></a>설명  
 편집 하며 계속 하기가이 함수에 허용 된 경우는 `GetILCode` 메서드는 공용 언어 런타임 (CLR)에 있는 코드의 편집 된 버전을이 함수에 해당 하는 MSIL 코드를 가져옵니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
