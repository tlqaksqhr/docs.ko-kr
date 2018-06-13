---
title: ICorDebugChain::GetCaller 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetCaller
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::GetCaller
helpviewer_keywords:
- ICorDebugChain::GetCaller method [.NET Framework debugging]
- GetCaller method, ICorDebugChain interface [.NET Framework debugging]
ms.assetid: d0b8ab4b-d7d2-4fa0-945f-3d2b87e7e991
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1a0b5d702e9718ce6ac537beae67fc190b152b9f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33405145"
---
# <a name="icordebugchaingetcaller-method"></a>ICorDebugChain::GetCaller 메서드
이 체인을 호출한 체인을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetCaller (  
    [out] ICorDebugChain      **ppChain  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `ppChain`  
 [out] 호출 체인을 나타내는 ICorDebugChain 개체의 주소에 대 한 포인터입니다.  
  
 이 체인 이라고 자연스럽 게 (처럼의 경우가이 체인이 나 디버거가 호출 스택을 초기화 하는 경우), `ppChain` null이 됩니다.  
  
## <a name="remarks"></a>설명  
 호출 체인은 호출 스레드 간에 마샬링된 경우 다른 스레드에서 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
