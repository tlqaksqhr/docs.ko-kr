---
title: "CorParamAttr 열거형"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorParamAttr
api_location: mscoree.dll
api_type: COM
f1_keywords: CorParamAttr
helpviewer_keywords: CorParamAttr enumeration [.NET Framework metadata]
ms.assetid: a7ff90ad-dad8-48e8-917d-4aa9a118cbc8
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 87afe125536473f99053db7d2fd4ae61fa4017ba
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="corparamattr-enumeration"></a>CorParamAttr 열거형
메서드 매개 변수의 메타데이터를 설명하는 값을 포함합니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef enum CorParamAttr {  
  
    pdIn                        =   0x0001,  
    pdOut                       =   0x0002,  
    pdOptional                  =   0x0010,  
  
    pdReservedMask              =   0xf000,  
    pdHasDefault                =   0x1000,  
    pdHasFieldMarshal           =   0x2000,  
  
    pdUnused                    =   0xcfe0  
  
} CorParamAttr;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`pdIn`|매개 변수 메서드 호출으로 전달 되도록 지정 합니다.|  
|`pdOut`|전달 되도록 지정 매개 변수는 메서드의 반환 합니다.|  
|`pdOptional`|매개 변수가 옵션 임을 지정 합니다.|  
|`pdReservedMask`|공용 언어 런타임에서 내부 용도로 예약 되어 있습니다.|  
|`pdHasDefault`|매개 변수 기본값을 갖도록 지정 합니다.|  
|`pdHasFieldMarshal`|매개 변수 마샬링 정보 갖도록 지정 합니다.|  
|`pdUnused`|사용되지 않습니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorHdr.h  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [메타데이터 열거형](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
