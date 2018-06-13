---
title: IReferenceIdentity 인터페이스
ms.date: 03/30/2017
api_name:
- IReferenceIdentity
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IReferenceIdentity
helpviewer_keywords:
- IReferenceIdentity interface [.NET Framework fusion]
ms.assetid: 9180ac5a-7019-4716-9f83-8a91d157239a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4708fa173725e4c91a13f5b92cdbb1fdf8a8a4d1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33432105"
---
# <a name="ireferenceidentity-interface"></a>IReferenceIdentity 인터페이스
코드 개체의 고유 서명에 대 한 참조를 나타냅니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|`IReferenceIdentity::Clone`|새 인터페이스 포인터를 가져옵니다 `IReferenceIdentity` 이 동일한 인스턴스 `IReferenceIdentity`, 지정 된 특성 변경을 제외 하 고 있습니다.|  
|`IReferenceIdentity::EnumAttributes`|한 인터페이스 포인터를 가져옵니다는 `IEnumIDENTITY_ATTRIBUTE` 이 연관 된 특성을 포함 하는 인스턴스 `IReferenceIdentity`합니다.|  
|`IReferenceIdentity::GetAttribute`|지정 된 이름의 지정된 된 네임 스페이스에는 특성의 값을 가져옵니다.|  
|`IReferenceIdentity::SetAttribute`|지정된 된 네임 스페이스와 지정된 된 값으로 지정 된 이름을 가진 특성을 설정 합니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** Isolation.h  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [Fusion 인터페이스](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)  
 [IEnumIDENTITY_ATTRIBUTE 인터페이스](../../../../docs/framework/unmanaged-api/fusion/ienumidentity-attribute-interface.md)
