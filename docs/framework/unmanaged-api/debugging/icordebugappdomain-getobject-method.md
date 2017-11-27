---
title: "ICorDebugAppDomain::GetObject 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugAppDomain.GetObject
api_location: corguids.lib
api_type: COM
f1_keywords: ICorDebugAppDomain::GetObject
helpviewer_keywords:
- ICorDebugAppDomain::GetObject method [.NET Framework debugging]
- GetObject method, ICorDebugAppDomain interface [.NET Framework debugging]
ms.assetid: 78232e6f-ae18-4cfa-a6cd-e79471cf9d76
topic_type: apiref
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c4f923d8e9bf9762d5208dd6e9be527a50a688b1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugappdomaingetobject-method"></a>ICorDebugAppDomain::GetObject 메서드
공용 언어 런타임 (CLR) 응용 프로그램 도메인에 대 한 인터페이스 포인터를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetObject (  
    [out] ICorDebugValue   **ppObject  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `ppObject`  
 [out] CLR 응용 프로그램 도메인을 나타내는 ICorDebugValue 인터페이스 개체의 주소에 대 한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
 관리 되는 경우 <xref:System.AppDomain?displayProperty=nameWithType> 메서드 반환이 응용 프로그램 도메인에 대 한 개체 생성 되지 않은, `S_FALSE` 배치 `NULL` 에서 `*ppObject`합니다.  
  
## <a name="remarks"></a>설명  
 프로세스에서 각 응용 프로그램 도메인을 관리 되는 있을 수 있습니다 <xref:System.AppDomain?displayProperty=nameWithType> 런타임에서 점을 나타내는 개체입니다. 이 함수는 관리 되는에 해당 하는 ICorDebugValue 인터페이스 개체를 가져옵니다 <xref:System.AppDomain?displayProperty=nameWithType> 개체입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]
