---
title: IAppIdAuthority 인터페이스
ms.date: 03/30/2017
api_name:
- IAppIdAuthority
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAppIdAuthority
helpviewer_keywords:
- IAppIdAuthority interface [.NET Framework fusion]
ms.assetid: ec354fa1-1efd-41b0-bc43-b90597b6e253
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 819afec2c448e5f396ab54e2dde00c01da310b12
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="iappidauthority-interface"></a>IAppIdAuthority 인터페이스
생성 하 고 응용 프로그램 id 및 참조에 대 한 키를 비교 하는 메서드를 제공 합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|`IAppIdAuthority::AreDefinitionsEqual`|지정 된 두 여부를 나타내는 값을 가져옵니다 [IDefinitionAppId](../../../../docs/framework/unmanaged-api/fusion/idefinitionappid-interface.md) 인스턴스는 같습니다. 각 버전 정보를 무시 하도록 IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION 플래그 값을 전달할 수 있습니다.|  
|`IAppIdAuthority::AreReferencesEqual`|지정 된 두 여부를 나타내는 값을 가져옵니다 [IReferenceAppId](../../../../docs/framework/unmanaged-api/fusion/ireferenceappid-interface.md) 인스턴스는 같습니다. 각 버전 정보를 무시 하도록 IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION 플래그 값을 전달할 수 있습니다.|  
|`IAppIdAuthority::AreTextualDefinitionsEqual`|두 개의 지정 된 문자열 정의 같은지 여부를 나타내는 값을 가져옵니다. 각 버전 정보를 무시 하도록 IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION 플래그 값을 전달할 수 있습니다.|  
|`IAppIdAuthority::AreTextualReferencesEqual`|두 개의 지정 된 문자열 참조 같은지 여부를 나타내는 값을 가져옵니다. 각 버전 정보를 무시 하도록 IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION 플래그 값을 전달할 수 있습니다.|  
|`IAppIdAuthority::CreateDefinition`|새로 생성 된에 대 한 인터페이스 포인터를 가져옵니다 `IDefinitionAppId` 현재 범위에 있는 어셈블리를 나타내는 인스턴스입니다.|  
|`IAppIdAuthority::CreateReference`|새로 만든 인터페이스 포인터를 가져옵니다 `IReferenceAppId` 현재 범위에 있는 어셈블리를 나타내는입니다.|  
|`IAppIdAuthority::DefinitionToText`|지정 된 문자열 버전을 가져옵니다 `IDefinitionAppId`, 지정 된 플래그 값을 사용 하 여 합니다.|  
|`IAppIdAuthority::DoesDefinitionMatchReference`|나타내는 값을 가져옵니다 있는지 여부를 지정 된 `IDefinitionAppId` 및 `IReferenceAppId` 동일한 어셈블리를 나타냅니다.|  
|`IAppIdAuthority::DoesTextualDefinitionMatchTextualReference`|지정한 정의 문자열 및 참조 문자열이 동일한 어셈블리를 나타내는 있는지 여부를 나타내는 값을 가져옵니다.|  
|`IAppIdAuthority::GenerateDefinitionKey`|나타내는 지정 된 문자열 키를 가져옵니다 `IDefinitionAppId` 인스턴스.|  
|`IAppIdAuthority::GenerateReferenceKey`|나타내는 지정 된 문자열 키를 가져옵니다 `IReferenceAppId` 인스턴스.|  
|`IAppIdAuthority::HashDefinition`|지정 된 해시 키를 가져옵니다 `IDefinitionAppId` 인스턴스.|  
|`IAppIdAuthority::HashReference`|지정 된 해시 키를 가져옵니다 `IReferenceAppId` 인스턴스.|  
|`IAppIdAuthority::ReferenceToText`|지정 된 문자열 버전을 가져옵니다 `IReferenceAppId`, 지정 된 플래그 값을 사용 하 여 합니다.|  
|`IAppIdAuthority::TextToDefinition`|한 인터페이스 포인터를 가져옵니다는 `IDefinitionAppId` 지정 된 문자열 키에서 참조 어셈블리를 나타내는 인스턴스입니다.|  
|`IAppIdAuthority::TextToReference`|한 인터페이스 포인터를 가져옵니다는 `IReferenceAppId` 지정 된 문자열 키에서 참조 어셈블리를 나타내는 인스턴스입니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** Isolation.h  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [Fusion 인터페이스](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
