---
title: "CorPropertyAttr 열거형"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorPropertyAttr
api_location: mscoree.dll
api_type: COM
f1_keywords: CorPropertyAttr
helpviewer_keywords: CorPropertyAttr enumeration [.NET Framework metadata]
ms.assetid: 58ac8202-854d-4efd-acfb-d2da8b446e12
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4470cd46653dd798718e5b3413dbc021a894138b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="corpropertyattr-enumeration"></a>CorPropertyAttr 열거형
속성의 메타데이터를 설명하는 값을 포함합니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef enum CorPropertyAttr {  
  
    prSpecialName           =   0x0200,   
    prReservedMask          =   0xf400,  
    prRTSpecialName         =   0x0400,  
    prHasDefault            =   0x1000,  
    prUnused                =   0xe9ff  
  
} CorPropertyAttr;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`prSpecialName`|속성이 특수 문자이 고 해당 이름을 설명 하 고 있음을 지정 방법입니다.|  
|`prReservedMask`|공용 언어 런타임에서 내부 용도로 예약 되어 있습니다.|  
|`prRTSpecialName`|공용 언어 런타임 메타 데이터 내부 Api 확인 하도록 지정 합니다 속성 이름의 인코딩입니다.|  
|`prHasDefault`|속성이 기본값을 갖도록 지정 합니다.|  
|`prUnused`|사용되지 않습니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorHdr.h  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [메타데이터 열거형](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
