---
title: "CorErrorIfEmitOutOfOrder 열거형"
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
- CorErrorIfEmitOutOfOrder
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorErrorIfEmitOutOfOrder
helpviewer_keywords:
- CorErrorIfEmitOutOfOrder enumeration [.NET Framework metadata]
ms.assetid: 6d758aad-29a7-44fe-9481-bbff5b799a32
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 7c049d78d8ba67ec5f08fc2beb584fef4987c9e8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="corerrorifemitoutoforder-enumeration"></a>CorErrorIfEmitOutOfOrder 열거형
메타데이터를 내보내는 순서가 잘못되었을 때 오류 메시지가 생성되어야 하는 조건을 나타내는 플래그 값을 포함합니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef enum CorErrorIfEmitOutOfOrder {  
  
    MDErrorOutOfOrderDefault    = 0x00000000,  
    MDErrorOutOfOrderNone       = 0x00000000,  
    MDErrorOutOfOrderAll        = 0xffffffff,  
    MDMethodOutOfOrder          = 0x00000001,  
    MDFieldOutOfOrder           = 0x00000002,  
    MDParamOutOfOrder           = 0x00000004,  
    MDPropertyOutOfOrder        = 0x00000008,  
    MDEventOutOfOrder           = 0x00000010  
  
} CorErrorIfEmitOutOfOrder;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`MDErrorOutOfOrderDefault`|오류 메시지를 표시 하지 않는 기본 동작을 나타냅니다.|  
|`MDErrorOutOfOrderNone`|컴파일러 오류 메시지를 생성 하지 해야 함을 나타냅니다.|  
|`MDErrorOutOfOrderAll`|필드, 속성, 이벤트, 메서드 때 컴파일러에서 오류 메시지를 생성 하도록 하거나 매개 변수 순서가 내보내집니다 나타냅니다.|  
|`MDMethodOutOfOrder`|메서드에 잘못 된 순서로 경우 컴파일러에서 오류 메시지를 생성 해야 함을 나타냅니다.|  
|`MDFieldOutOfOrder`|필드는 내보내는 순서가 잘못 되었을 때 컴파일러에서 오류 메시지를 생성 해야 함을 나타냅니다.|  
|`MDParamOutOfOrder`|매개 변수가 잘못 된 순서로 경우 컴파일러에서 오류 메시지를 생성 해야 함을 나타냅니다.|  
|`MDPropertyOutOfOrder`|속성은 내보내는 순서가 잘못 되었을 때 컴파일러에서 오류 메시지를 생성 해야 함을 나타냅니다.|  
|`MDEventOutOfOrder`|이벤트가 잘못 된 순서로 발생 하는 경우 컴파일러에서 오류 메시지를 생성 해야 함을 나타냅니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorHdr.h  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [메타데이터 열거형](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
