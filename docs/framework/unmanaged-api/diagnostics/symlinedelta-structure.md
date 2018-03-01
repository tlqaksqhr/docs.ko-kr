---
title: "SYMLINEDELTA 구조체"
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
- SYMLINEDELTA
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- SYMLINEDELTA
helpviewer_keywords:
- SYMLINEDELTA structure [.NET Framework debugging]
ms.assetid: 9634e995-d46d-4397-ab66-cc5781d11e4e
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 677b7c2858e4f3248e0d46e460b9eef09de724f0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="symlinedelta-structure"></a>SYMLINEDELTA 구조체
편집한 이동 된 방법에 대 한 기호 처리기에 대 한 정보를 제공 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef struct _SYMLINEDELTA  
    {  
        mdMethodDef  mdMethod;  
        INT32        delta;  
    } SYMLINEDELTA;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`mdMethod`|메서드의 메타 데이터 토큰입니다.|  
|`delta`|메서드가 이동 된 줄 수 있습니다.|  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** CorSym.idl  
  
## <a name="see-also"></a>참고 항목  
 [진단 기호 저장소 구조체](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-structures.md)
