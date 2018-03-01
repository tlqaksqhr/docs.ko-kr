---
title: "ICorDebugILFrame::CanSetIP 메서드"
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
- ICorDebugILFrame.CanSetIP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::CanSetIP
helpviewer_keywords:
- CanSetIP method, ICorDebugILFrame interface [.NET Framework debugging]
- ICorDebugILFrame::CanSetIP method [.NET Framework debugging]
ms.assetid: 16caf02f-c71e-486c-90b0-f0e54357d8f0
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 22d0df9add0a4ce35b1a590d65e30a6756fec49c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugilframecansetip-method"></a>ICorDebugILFrame::CanSetIP 메서드
명령 포인터 Microsoft MSIL (Intermediate Language) 코드에서 지정된 된 오프셋된 위치를 설정할 수 있는지 여부를 나타내는 HRESULT를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT CanSetIP (  
    [in] ULONG32   nOffset  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `nOffset`  
 [in] 명령 포인터에 대 한 원하는 설정 합니다.  
  
## <a name="remarks"></a>설명  
 사용 하 여는 `CanSetIP` 메서드 호출 하기 전에 [icordebugilframe:: Setip](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md) 메서드. 경우 `CanSetIP` HRESULT를 반환 S_OK 이외의 실행할 수 있습니다 `ICorDebugILFrame::SetIP`, 하지만 디버거에서 디버깅 중인 코드를 안전 하 고 올바르게 실행할을 계속 해 서 보장 되지 않습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug, h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
