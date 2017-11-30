---
title: "ICorDebugRemoteTarget 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugRemoteTarget
api_location: CorDebug.dll
api_type: COM
f1_keywords: ICorDebugRemoteTarget
helpviewer_keywords: ICorDebugRemoteTarget interface [.NET Framework debugging]
ms.assetid: bd9936a6-cc24-4869-8761-0988664464e6
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 38357072b3a6e8e8a326a16600b2d7ed56cdcb2e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugremotetarget-interface"></a>ICorDebugRemoteTarget 인터페이스
개발자가 CLR(공용 언어 런타임) 환경에서 Silverlight 기반 응용 프로그램을 디버깅하는 데 사용할 수 있는 메서드를 제공합니다.  
  
## <a name="syntax"></a>구문  
  
```  
interface ICorDebugRemoteTarget  : IUnknown  
{  
    HRESULT GetHostName (  
        [in]  ULONG32                    cchHostName,  
        [out] ULONG32*                   pcchHostName,  
        [out, size_is(cchHostName),  
              length_is(*pcchHostName)]  
                  WCHAR szHostName[]  
        );  
};  
```  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[Icordebugremotetarget:: Gethostname 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-gethostname-method.md)|원격 컴퓨터의 IP 주소나 호스트 이름을 반환합니다.|  
  
## <a name="remarks"></a>설명  
 Windows 95, Windows 98, Windows ME 또는 x86이 아닌 플랫폼(IA-64, AMD64 등)에서는 관리 코드와 네이티브 코드가 혼합된 혼합 모드에서의 디버깅이 지원되지 않습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl  
  
 **라이브러리:** : CorGuids.lib  
  
 **.NET framework 버전:** 3.5 SP1  
  
## <a name="see-also"></a>참고 항목  
 [ICorDebugRemote 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugremote-interface.md)  
 [ICorDebug 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)  
 [디버깅 인터페이스](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
