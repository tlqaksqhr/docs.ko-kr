---
title: "IEnumDefinitionIdentity 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IEnumDefinitionIdentity
api_location: fusion.dll
api_type: COM
f1_keywords: IEnumDefinitionIdentity
helpviewer_keywords: IEnumDefinitionIdentity interface [.NET Framework fusion]
ms.assetid: 8263e75d-251b-4abc-8a1a-c62884142232
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 79e2a35a455407715a05e826d31c5d5ab05a02ad
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ienumdefinitionidentity-interface"></a>IEnumDefinitionIdentity 인터페이스
컬렉션의 열거자 역할을 `IDefinitionIdentity` 개체입니다.  
  
## <a name="syntax"></a>구문  
  
```  
IEnumDefinitionIdentity : IUnknown {  
  
    HRESULT Clone (  
        [out] IEnumDefinitionIdentity **ppIEnumDefinitionIdentity  
    );  
  
    HRESULT Next (  
        [in]  ULONG               celt,  
        [out, length_is(celt), size_is(*pceltWritten)]  
              IDefinitionIdentity *rgpIDefinitionIdentity[],  
        [out] ULONG               *pceltWritten  
    );  
  
    HRESULT Reset ();  
  
    HRESULT Skip (  
        [in] ULONG celt  
    );  
  
};  
```  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|`IEnumDefinitionIdentity::Clone`|새 인터페이스 포인터를 가져옵니다 `IEnumDefinitionIdentity` 이와 동일한 멤버를 포함 하는 개체 `IEnumDefinitionIdentity`합니다.|  
|`IEnumDefinitionIdentity::Next`|지정된 된 수의 가져옵니다 `IDefinitionIdentity` 개체를 현재 위치부터 시작 합니다.|  
|`IEnumDefinitionIdentity::Reset`|명령 포인터의 시작으로 이동 `IEnumDefinitionIdentity`합니다.|  
|`IEnumDefinitionIdentity::Skip`|명령 포인터 앞으로 요소를 현재 위치부터 지정한 수 만큼 이동 합니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** Isolation.h  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [Fusion 인터페이스](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)  
 [IDefinitionIdentity 인터페이스](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md)
