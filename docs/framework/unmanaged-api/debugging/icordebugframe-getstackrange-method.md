---
title: "ICorDebugFrame::GetStackRange 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugFrame.GetStackRange
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugFrame::GetStackRange
helpviewer_keywords:
- GetStackRange method, ICorDebugFrame interface [.NET Framework debugging]
- ICorDebugFrame::GetStackRange method [.NET Framework debugging]
ms.assetid: fab037cb-fda6-40fb-9367-921e435dd5a0
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f1db7617d52e07489ade339b76023e21816835ee
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugframegetstackrange-method"></a>ICorDebugFrame::GetStackRange 메서드
이 스택 프레임의 절대 주소 범위를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetStackRange (  
    [out] CORDB_ADDRESS      *pStart,   
    [out] CORDB_ADDRESS      *pEnd  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pStart`  
 [out] 에 대 한 포인터는 `CORDB_ADDRESS` 이 표시 되는 스택 프레임의 시작 주소를 지정 하는 `ICorDebugFrame` 개체입니다.  
  
 `pEnd`  
 [out] 에 대 한 포인터는 `CORDB_ADDRESS` 이 표시 되는 스택 프레임의 끝 주소를 지정 하는 `ICorDebugFrame` 개체입니다.  
  
## <a name="remarks"></a>설명  
 스택의 주소 범위는 정보를 결합 인터리브 스택 추적 여러 디버깅 엔진에서 수집 하는 데 유용 합니다. 숫자 범위는 스택 프레임의 내용 관련 정보를 제공합니다. 스택 프레임 위치를 비교 하기 위해 됩니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
