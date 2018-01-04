---
title: "COR_PRF_EX_CLAUSE_INFO 구조체"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_PRF_EX_CLAUSE_INFO
api_location: mscorwks.dll
api_type: COM
f1_keywords: COR_PRF_EX_CLAUSE_INFO
helpviewer_keywords: COR_PRF_EX_CLAUSE_INFO structure [.NET Framework profiling]
ms.assetid: 7d0d6fb7-bc9d-40f0-8163-c0d162eaba7d
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 65025384aa94ac363336bae7f37f8ea88a3bab67
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="corprfexclauseinfo-structure"></a>COR_PRF_EX_CLAUSE_INFO 구조체
특정 예외 절 인스턴스 및 관련 프레임에 대한 정보를 저장합니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef struct COR_PRF_EX_CLAUSE_INFO {  
    COR_PRF_CLAUSE_TYPE clauseType;  
    UINT_PTR programCounter;  
    UINT_PTR framePointer;  
    UINT_PTR shadowStackPointer;  
} COR_PRF_EX_CLAUSE_INFO;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`clauseType`|값은 [COR_PRF_CLAUSE_TYPE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-clause-type-enumeration.md) 되거나 끝난 예외 절 방금 입력 한 코드의 형식을 지정 하는 열거형입니다.|  
|`programCounter`|절 처리기의 기본 진입점-X86 EIP 레지스터의 내용을 예를 들어 있습니다.|  
|`framePointer`|절 처리기에 대 한 논리 프레임에 대 한 포인터-X86 EBP 레지스터의 내용을 예를 들어 있습니다.|  
|`shadowStackPointer`|섀도 스택 포인터입니다. 이 값 BSP 레지스터의 내용을 이며 IA64에만 적용 됩니다.|  
  
## <a name="remarks"></a>설명  
 예외 알림이 수신 되 면 [icorprofilerinfo2:: Getnotifiedexceptionclauseinfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getnotifiedexceptionclauseinfo-method.md) 예외 절에 대 한 기본 주소 및 프레임 정보를 가져오는 데 사용할 수 있습니다 (`catch` / `finally`/필터) 방금 실행 되거나 실행 하 려 하 합니다.  
  
 Exception 절의 실행에는 공용 언어 런타임 (CLR)에서 이러한 콜백을 포함 됩니다.  
  
-   [Icorprofilercallback:: Exceptioncatcherenter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherenter-method.md)  
  
-   [Icorprofilercallback:: Exceptionunwindfinallyenter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyenter-method.md)  
  
-   [Icorprofilercallback:: Exceptionsearchfilterenter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterenter-method.md)  
  
-   [Icorprofilercallback:: Exceptioncatcherleave](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherleave-method.md)  
  
-   [Icorprofilercallback:: Exceptionunwindfinallyleave](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyleave-method.md)  
  
-   [Icorprofilercallback:: Exceptionsearchfilterleave](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterleave-method.md)  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorProf.idl  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [프로파일링 구조체](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
