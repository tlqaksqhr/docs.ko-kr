---
title: "COR_PRF_FUNCTION_ARGUMENT_INFO 구조체"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_PRF_FUNCTION_ARGUMENT_INFO
api_location: mscorwks.dll
api_type: COM
f1_keywords: COR_PRF_FUNCTION_ARGUMENT_INFO
helpviewer_keywords: COR_PRF_FUNCTION_ARGUMENT_INFO structure [.NET Framework profiling]
ms.assetid: 07cf3bab-e193-4991-8205-3f41cf2d67b3
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e26377fe3c5cfbae68f90087e3fb624ae4db0dc8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="corprffunctionargumentinfo-structure"></a>COR_PRF_FUNCTION_ARGUMENT_INFO 구조체
왼쪽에서 오른쪽 순서의 함수 인수를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef struct _COR_PRF_FUNCTION_ARGUMENT_INFO {  
    ULONG numRanges;  
    ULONG totalArgumentSize;  
    COR_PRF_FUNCTION_ARGUMENT_RANGE ranges[1];  
} COR_PRF_FUNCTION_ARGUMENT_INFO;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`numRanges`|인수는 블록의 수입니다. 즉,이 값은 수가 [COR_PRF_FUNCTION_ARGUMENT_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-range-structure.md) 구조체에 `ranges` 배열입니다.|  
|`totalArgumentSize`|모든 인수의 총 크기입니다. 즉,이 값은 인수 길이 합계입니다.|  
|`ranges`|배열 `COR_PRF_FUNCTION_ARGUMENT_RANGE` 구조를 각각 한 함수 인수 블록을 나타냅니다.|  
  
## <a name="remarks"></a>설명  
 함수는 많은 인수를 지정할 수 있습니다. 메모리에 연속적으로 이러한 인수를 저장할 수 있습니다. 블록을 한 곳에 세 개의 인수, 다른 위치에서 두 개의 인수 블록 및 다른 위치에 한 인수의 마지막 블록을 할 수 있습니다. 이 인수는 모두 동일한 함수;에 대 한 방금 서로 다른 위치에 저장 합니다.  
  
 `COR_PRF_FUNCTION_ARGUMENT_INFO` 구조 단일 함수의 모든 인수를 나타냅니다. 함수 인수 블록을 모두 참조 하는 배열을 사용 합니다. 따라서 단일 있는 단일 함수에 대 한 `COR_PRF_FUNCTION_ARGUMENT_INFO` 여러 참조 하는 구조 `COR_PRF_FUNCTION_ARGUMENT_RANGE` 구조에는 각각 하나 이상의 함수 인수를 가리킵니다.  
  
 레지스터에 저장 된 인수는 구조체를 메모리로 넘어가 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorProf.idl  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [프로파일링 구조체](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
