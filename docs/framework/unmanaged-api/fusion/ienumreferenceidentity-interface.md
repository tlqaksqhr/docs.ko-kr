---
title: "IEnumReferenceIdentity 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IEnumReferenceIdentity
api_location: fusion.dll
api_type: COM
f1_keywords: IEnumReferenceIdentity
helpviewer_keywords: IEnumReferenceIdentity interface [.NET Framework fusion]
ms.assetid: a17b3155-7216-4e16-8c9f-abce21f549e7
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d1af31c72770947c33f358a9689bac6fd95ef53c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ienumreferenceidentity-interface"></a>IEnumReferenceIdentity 인터페이스
컬렉션의 열거자 역할을 `IReferenceIdentity` 개체입니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|`IEnumReferenceIdentity::Clone`|새 인터페이스 포인터를 가져옵니다 `IEnumReferenceIdentity` 이와 동일한 멤버를 포함 하는 `IEnumReferenceIdentity`합니다.|  
|`IEnumReferenceIdentity::Next`|지정된 된 수의 가져옵니다 `IReferenceIdentity` 개체를 현재 위치부터 시작 합니다.|  
|`IEnumReferenceIdentity::Reset`|명령 포인터의 시작으로 이동 `IEnumReferenceIdentity`합니다.|  
|`IEnumReferenceIdentity::Skip`|명령 포인터 앞으로 요소를 현재 위치부터 지정한 수 만큼 이동 합니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** Isolation.h  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [Fusion 인터페이스](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)  
 [IReferenceIdentity 인터페이스](../../../../docs/framework/unmanaged-api/fusion/ireferenceidentity-interface.md)
