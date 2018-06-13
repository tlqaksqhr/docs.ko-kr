---
title: CorSetENC 열거형
ms.date: 03/30/2017
api_name:
- CorSetENC
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorSetENC
helpviewer_keywords:
- CorSetENC enumeration [.NET Framework metadata]
ms.assetid: fe4150e8-071d-43fb-8e06-c3c616dbeed2
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3e09bf424a41445f7e36397775d1578cdf4e7e75
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33442789"
---
# <a name="corsetenc-enumeration"></a>CorSetENC 열거형
메타데이터 생성 중의 동작에 영향을 주는 데 사용되는 값을 포함합니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef enum CorSetENC {  
  
    MDSetENCOn                  = 0x00000001,  
    MDSetENCOff                 = 0x00000002,  
  
    MDUpdateENC                 = 0x00000001,  
    MDUpdateFull                = 0x00000002,  
    MDUpdateExtension           = 0x00000003,  
    MDUpdateIncremental         = 0x00000004,  
    MDUpdateDelta               = 0x00000005,  
    MDUpdateMask                = 0x00000007  
  
} CorSetENC;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`MDSetENCOn`|사용되지 않습니다.|  
|`MDSetENCOff`|사용되지 않습니다.|  
|`MDUpdateENC`|메타 데이터, 업데이트 하는 반면 토큰은 이동할 수 없음을 나타냅니다.|  
|`MDUpdateFull`|업데이트 동안 토큰을 이동할 수 있는지를 나타냅니다.|  
|`MDUpdateExtension`|업데이트 추가만 구성 수를 나타냅니다. 토큰을 이동할 수 없습니다.|  
|`MDUpdateIncremental`|증분 컴파일을 나타냅니다.|  
|`MDUpdateDelta`|저장 해야 하는 변경 된 메타 데이터만 나타냅니다.|  
|`MDUpdateMask`|포함 `MDUpdateENC`, `MDUpdateFull` 및 `MDUpdateIncremental`합니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorHdr.h  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [메타데이터 열거형](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
