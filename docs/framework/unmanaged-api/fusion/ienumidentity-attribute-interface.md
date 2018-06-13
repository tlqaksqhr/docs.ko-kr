---
title: IEnumIDENTITY_ATTRIBUTE 인터페이스
ms.date: 03/30/2017
api_name:
- IEnumIDENTITY_ATTRIBUTE
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IEnumIDENTITY_ATTRIBUTE
helpviewer_keywords:
- IEnumIDENTITY_ATTRIBUTE interface [.NET Framework fusion]
ms.assetid: c2ec2748-e9ae-4e1b-80db-6fcec5cb81a1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: da6462a320b1f090940473f566ade91d36e74780
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33431703"
---
# <a name="ienumidentityattribute-interface"></a>IEnumIDENTITY_ATTRIBUTE 인터페이스
현재 범위에 있는 코드 개체의 특성에 대 한 열거자 역할을 합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|`IEnumIDENTITY_ATTRIBUTE::Clone`|새 인터페이스 포인터를 가져옵니다 `IEnumIDENTITY_ATTRIBUTE` 이와 동일한 멤버를 포함 하는 `IEnumIDENTITY_ATTRIBUTE`합니다.|  
|`IEnumIDENTITY_ATTRIBUTE::CurrentIntoBuffer`|이 요소에 포함 된 데이터를 쓰는 `IEnumIDENTITY_ATTRIBUTE` 지정된 된 데이터 버퍼에 있습니다.|  
|`IEnumIDENTITY_ATTRIBUTE::Next`|현재 위치부터 시작 하는 특성의 지정된 된 수를 가져옵니다.|  
|`IEnumIDENTITY_ATTRIBUTE::Reset`|명령 포인터의 시작으로 이동 `IEnumIDENTITY_ATTRIBUTE`합니다.|  
|`IEnumIDENTITY_ATTRIBUTE::Skip`|명령 포인터 앞으로 요소를 현재 위치부터 지정한 수 만큼 이동 합니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** Isolation.h  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [Fusion 인터페이스](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
