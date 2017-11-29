---
title: "ICorDebugController::EnumerateThreads 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugController.EnumerateThreads
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugController::EnumerateThreads
helpviewer_keywords:
- ICorDebugController::EnumerateThreads method [.NET Framework debugging]
- EnumerateThreads method [.NET Framework debugging]
ms.assetid: 73f536f6-4668-4a4a-b3e4-ac7df862d5be
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b7575bf2b50f11fab1c14f8fb28dc65e079c21de
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugcontrollerenumeratethreads-method"></a>ICorDebugController::EnumerateThreads 메서드
프로세스에서 현재 관리 되는 스레드에 대 한 열거자를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT EnumerateThreads (  
    [out] ICorDebugThreadEnum **ppThreads  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `ppThreads`  
 [out] 프로세스에서 활성화 되는 모든 관리 되는 스레드에 대 한 열거자를 나타내는 "ICorDebugThreadEnum" 개체의 주소에 대 한 포인터입니다.  
  
## <a name="remarks"></a>설명  
 스레드 후 활성 것으로 간주 되는 [icordebugmanagedcallback:: Createthread](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createthread-method.md) 콜백 처리 된 후에 하기 전에 [icordebugmanagedcallback:: Exitthread](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitthread-method.md) 콜백 처리 된 후에 . 관리 되는 스레드 반드시 없을 수도 있는 관리 되는 프레임 스택에. 스레드 이전에 열거할 수는 [icordebugmanagedcallback:: Createprocess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) 콜백 합니다. 열거형은 자연스럽 게 비어 있게 됩니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 
