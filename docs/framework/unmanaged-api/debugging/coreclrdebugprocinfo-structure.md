---
title: "CoreClrDebugProcInfo 구조체"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CoreClrDebugProcInfo
api_location: mscordbi_macx86.dll
api_type: COM
f1_keywords: CoreClrDebugProcInfo
helpviewer_keywords:
- remote debugging API [Silverlight]
- CoreClrDebugProcInfo structure
- Silverlight, remote debugging
ms.assetid: 4ddc37da-5c94-4beb-b61c-b54071c0e749
topic_type: apiref
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d341b875f9f64b9aa1fcdcf21668dafea0beac12
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="coreclrdebugprocinfo-structure"></a>CoreClrDebugProcInfo 구조체
원격 컴퓨터에서 실행되는 프로세스를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
struct  CoreClrDebugProcInfo {  
    DWORD m_dwPID;  
    DWORD m_dwInternalID;  
    WCHAR m_wszName[256];  
};  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`m_dwPID`|OS에서 할당한 프로세스 식별자입니다.|  
|`m_dwInternalID`|대상 컴퓨터에서 실행되는 원격 디버깅 프록시에 의해 할당된 프로세스 식별자입니다. 이 식별자는 OS 식별자만큼 자주 재활용되지 않습니다.|  
|`m_wszName`|프로세스의 명령줄입니다. 이 멤버는 잘릴 수 있습니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CoreClrRemoteDebuggingInterfaces.h  
  
 **라이브러리:** mscordbi_macx86.dll  
  
 **.NET framework 버전:** 3.5 SP1
