---
title: "IIdentityAuthority 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IIdentityAuthority
api_location: fusion.dll
api_type: COM
f1_keywords: IIdentityAuthority
helpviewer_keywords: IIdentityAuthority interface [.NET Framework fusion]
ms.assetid: 6277f914-51a8-49be-bec6-52d6d648527d
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c3f38d932fa0376186e2c22232d21857d5fa128f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="iidentityauthority-interface"></a>IIdentityAuthority 인터페이스
코드 개체에 대 한 id 키를 관리 합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|`IIdentityAuthority::AreDefinitionsEqual`|지정 된 두 여부를 나타내는 값을 가져옵니다 [IDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md) 인스턴스는 같습니다.|  
|`IIdentityAuthority::AreReferencesEqual`|지정 된 두 여부를 나타내는 값을 가져옵니다 [IReferenceIdentity](../../../../docs/framework/unmanaged-api/fusion/ireferenceidentity-interface.md) 인스턴스는 같습니다.|  
|`IIdentityAuthority::AreTextualDefinitionsEqual`|지정 된 문자열 두 정의 id 표현이 같은지 여부를 나타내는 값을 가져옵니다.|  
|`IIdentityAuthority::AreTextualReferencesEqual`|두 개의 지정 된 문자열 참조 id 표현이 같은지 여부를 나타내는 값을 가져옵니다.|  
|`IIdentityAuthority::CreateDefinition`|새에 대 한 포인터를 가져옵니다 `IDefinitionIdentity` 현재 범위에 있는 코드 개체를 나타내는 인스턴스입니다.|  
|`IIdentityAuthority::CreateReference`|새에 대 한 포인터를 가져옵니다 `IReferenceIdentity` 현재 범위에 있는 코드 개체를 나타내는 인스턴스입니다.|  
|`IIdentityAuthority::DefinitionToText`|지정 된 서식이 지정 된 문자열 버전을 가져옵니다 `IDefinitionIdentity`합니다.|  
|`IIdentityAuthority::DefinitionToTextBuffer`|지정 된 문자열 버전으로 지정 된 와이드 문자 버퍼를 채웁니다 `IDefinitionIdentity`합니다.|  
|`IIdentityAuthority::DoesDefinitionMatchReference`|나타내는 값을 가져옵니다 있는지 여부를 지정 된 `IDefinitionIdentity` 및 `IReferenceIdentity` 인스턴스가 동일한 코드 개체를 참조 합니다.|  
|`IIdentityAuthority::DoesTextualDefinitionMatchTextualReference`|지정된 된 문자열이 동일한 코드 개체를 참조 하는지 여부를 나타내는 값을 가져옵니다.|  
|`IIdentityAuthority::GenerateDefinitionKey`|지정 된 항목에 대 한 새로 생성된 된 문자열 키에 대 한 포인터를 가져옵니다 `IDefinitionIdentity`합니다.|  
|`IIdentityAuthority::GenerateReferenceKey`|지정 된 항목에 대 한 새로 생성된 된 문자열 키에 대 한 포인터를 가져옵니다 `IReferenceIdentity`합니다.|  
|`IIdentityAuthority::HashDefinition`|지정 된 해시 값을 가져옵니다 `IDefinitionIdentity`합니다.|  
|`IIdentityAuthority::HashReference`|지정 된 해시 값을 가져옵니다 `IreferenceIdentity`합니다.|  
|`IIdentityAuthority::ReferenceToText`|지정 된 서식이 지정 된 문자열 버전을 가져옵니다 `IReferenceIdentity`합니다.|  
|`IIdentityAuthority::ReferenceToTextBuffer`|지정 된 문자열 버전으로 지정 된 와이드 문자 버퍼를 채웁니다 `IReferenceIdentity`합니다.|  
|`IIdentityAuthority::TextToDefinition`|한 인터페이스 포인터를 가져옵니다는 `IDefinitionIdentity` 형식 지정 문자열로 지정 된 위치에서 생성 합니다.|  
|`IIdentityAuthority::TextToReference`|한 인터페이스 포인터를 가져옵니다는 `IReferenceIdentity` 형식 지정 문자열로 지정 된 위치에서 생성 합니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** Isolation.h  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [Fusion 인터페이스](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
