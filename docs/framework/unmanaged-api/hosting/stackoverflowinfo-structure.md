---
title: "StackOverflowInfo 구조체"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: StackOverflowInfo
api_location: mscoree.dll
api_type: COM
f1_keywords: StackOverflowInfo
helpviewer_keywords: StackOverflowInfo structure [.NET Framework hosting]
ms.assetid: 519389f2-0217-436c-99d4-93a76ebce5b5
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 102f744ecc769a10161cd20767e8e49c838252a7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="stackoverflowinfo-structure"></a>StackOverflowInfo 구조체
오버플로로 인해 throw 된 예외에 발생 한 오버플로 종류 정보를 저장 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef struct _StackOverflowInfo {  
    StackOverflowType   soType;  
    EXCEPTION_POINTERS  *pExceptionInfo;  
} StackOverflowInfo;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`soType`|값은 [StackOverflowType](../../../../docs/framework/unmanaged-api/hosting/stackoverflowtype-enumeration.md) 오버플로의 유형을 지정 하는 열거형입니다.|  
|`pExceptionInfo`|Win32에 대 한 포인터 `EXCEPTION_POINTERS` 예외에 대 한 컴퓨터 독립적 설명을 예외 레코드와는 예외 발생 시의 프로세서 컨텍스트 컴퓨터 종속 설명 가진 컨텍스트 레코드를 포함 하는 개체입니다.|  
  
## <a name="remarks"></a>설명  
 A `StackOverflowInfo` 를 전달 하는 [iactiononclrevent:: Onevent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md) 방법을 `Event_StackOverflow` 이벤트입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** MSCorEE.idl  
  
 **라이브러리:** MSCorEE.dll에 리소스로 포함  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [호스팅 구조체](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
