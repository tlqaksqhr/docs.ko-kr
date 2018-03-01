---
title: "ICoreClrDebugTarget 인터페이스"
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
- ICoreClrDebugTarget
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- ICoreClrDebugTarget
helpviewer_keywords:
- remote debugging API [Silverlight]
- ICorClrDebugTarget interface
- Silverlight, remote debugging
ms.assetid: 7cfaee76-e284-4a66-a431-8e33f0f60038
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 62d43121efbc039b8fad0b78bed7ec4a655efabb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icoreclrdebugtarget-interface"></a>ICoreClrDebugTarget 인터페이스
참조 횟수를 제어, 프로세스, 열거 및 Macintosh Silverlight의 원격 대상에 연결 된 디버거에 연결 된 메모리를 해제 하는 메서드를 제공 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class ICoreClrDebugTarget {  
      HRESULT EnumProcesses (  
          [out] DWORD*                    pcProcs,  
          [out] CoreClrDebugProcInfo**    ppProcs  
      );  
  
      HRESULT EnumRuntimes (  
      [in]  DWORD                      dwInternalProcessID,  
      [out] DWORD*                     pcRuntimes,  
      [out] CoreClrDebugRuntimeInfo**  ppRuntimes  
      );  
  
      void FreeMemory (  
      [in] void*      pMemory  
    );  
};  
```  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[ICoreClrDebugTarget::EnumProcesses 메서드](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-enumprocesses-method.md)|원격 컴퓨터에서 실행 중인 프로세스를 열거합니다.|  
|[ICoreClrDebugTarget::EnumRuntimes 메서드](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-enumruntimes-method.md)|원격 컴퓨터에서 지정된 된 프로세스의 공용 언어 런타임 (Clr)를 열거합니다.|  
|[ICoreClrDebugTarget::FreeMemory 메서드](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-freememory-method.md)|이 클래스에서 열거형 메서드에 의해 할당 되는 메모리를 해제 합니다.|  
  
## <a name="remarks"></a>설명  
 현재이 기능은 원격 Macintosh 컴퓨터에서 실행 되는 Silverlight 기반 응용 프로그램 대상 디버깅에 대해서만 지원 됩니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CoreClrRemoteDebuggingInterfaces.h  
  
 **라이브러리:** mscordbi_macx86.dll  
  
 **.NET framework 버전:** 3.5 SP1  
  
## <a name="see-also"></a>참고 항목  
 [ICorDebugRemoteTarget 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md)  
 [ICorDebug 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)  
    
 [디버깅 인터페이스](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
