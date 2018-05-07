---
title: ICorDebugChain::GetActiveFrame 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetActiveFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::GetActiveFrame
helpviewer_keywords:
- ICorDebugChain::GetActiveFrame method [.NET Framework debugging]
- GetActiveFrame method, ICorDebugChain interface [.NET Framework debugging]
ms.assetid: 36887017-670b-4f21-b406-8fab956f84a3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a104d4d3cc74a6c1cb343818c9b0b3e8978b97df
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugchaingetactiveframe-method"></a>ICorDebugChain::GetActiveFrame 메서드
활성 가져옵니다 (즉, 가장 최근의) 프레임 체인에 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetActiveFrame (  
    [out] ICorDebugFrame   **ppFrame  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `ppFrame`  
 [out] 활성 나타내는 ICorDebugFrame 개체의 주소에 대 한 포인터 (즉, 가장 최근의) 프레임 체인에 있습니다.  
  
## <a name="remarks"></a>설명  
 관리 되는 스택 프레임이 사용할 수 있는 경우 `ppFrame` 설정 되어 null로 합니다.  
  
 활성 프레임을 사용할 수 없는 경우에 호출이 성공 하 고 `ppFrame` null이 됩니다. 활성 프레임 CHAIN_ENTER_UNMANAGED, 인해 시작 체인에 대해 및 CHAIN_CLASS_INIT 인해 시작 된 일부 체인에 대해 제공 됩니다. CorDebugChainReason 열거형을 참조 하십시오.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
