---
title: "NOTIFY_FILTER 열거형"
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
- NOTIFY_FILTER
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- NOTIFY_FILTER
helpviewer_keywords:
- NOTIFY_FILTER enumeration [.NET Framework debugging]
ms.assetid: 4789d08f-8683-45d3-ac30-73d48c61e470
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: ef72cb965bec8f424f5df35d4f66715fa11a5e46
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="notifyfilter-enumeration"></a>NOTIFY_FILTER 열거형
디버거 기능에 대 한 콜백을 식별합니다. 자세한 내용은 참조는 [inotifysource2:: Setnotifyfilter](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-setnotifyfilter-method.md) 메서드.  
  
## <a name="syntax"></a>구문  
  
```  
enum tagNOTIFY_FILTER  
{  
    NOTIFY_FILTER_ONSYNCCALLOUT    = 0x1,  
    NOTIFY_FILTER_ONSYNCCALLENTER  = 0x2,  
    NOTIFY_FILTER_ONSYNCCALLEXIT   = 0x4,  
    NOTIFY_FILTER_ONSYNCCALLRETURN = 0x8,  
    NOTIFY_FILTER_ALLSYNC = NOTIFY_FILTER_ONSYNCCALLOUT | NOTIFY_FILTER_ONSYNCCALLENTER | NOTIFY_FILTER_ONSYNCCALLEXIT | NOTIFY_FILTER_ONSYNCCALLRETURN,  
    NOTIFY_FILTER_ALL              = 0xffffffff,  
    NOTIFY_FILTER_NONE             = 0  
};  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`NOTIFY_FILTER_ONSYNCCALLOUT`|나타냅니다는 [inotifysink2:: Onsynccallout](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallout-method.md) 메서드를 호출 해야 합니다.|  
|`NOTIFY_FILTER_ONSYNCCALLENTER`|나타냅니다는 [inotifysink2:: Onsynccallenter](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallenter-method.md) 메서드를 호출 해야 합니다.|  
|`NOTIFY_FILTER_ONSYNCCALLEXIT`|나타냅니다는 [inotifysink2:: Onsynccallexit](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallexit-method.md) 메서드를 호출 해야 합니다.|  
|`NOTIFY_FILTER_ONSYNCCALLRETURN`|나타냅니다는 [inotifysink2:: Onsynccallreturn](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallreturn-method.md) 메서드를 호출 해야 합니다.|  
|`NOTIFY_FILTER_ALLSYNC`|나타내는 모든는 [INotifySink2](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md) 메서드를 호출 해야 합니다.|  
|`NOTIFY_FILTER_ALL`|모든 기존 및 차후의 알림을 활성화합니다.|  
|`NOTIFY_FILTER_NONE`|없는 알림 메서드를 호출 해야 함을 나타냅니다.|  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** ProtocolNotify2.idl  
  
## <a name="see-also"></a>참고 항목  
 [진단 기호 저장소 열거형](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)
