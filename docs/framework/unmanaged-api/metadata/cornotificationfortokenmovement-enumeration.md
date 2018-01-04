---
title: "CorNotificationForTokenMovement 열거형"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorNotificationForTokenMovement
api_location: mscoree.dll
api_type: COM
f1_keywords: CorNotificationForTokenMovement
helpviewer_keywords: CorNotificationForTokenMovement enumeration [.NET Framework metadata]
ms.assetid: 1edd1670-976a-4fc8-bef7-7c41e60ad989
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8e1d3ad11867dbd06dfe3f43cc31817a44cb96d4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="cornotificationfortokenmovement-enumeration"></a>CorNotificationForTokenMovement 열거형
알림을 토큰 다시 매핑 발생할 때 메타 데이터 API 클라이언트에 보낼 수를 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef enum CorNotificationForTokenMovement {  
  
    MDNotifyDefault             = 0x0000000f,  
    MDNotifyAll                 = 0xffffffff,  
    MDNotifyNone                = 0x00000000,  
    MDNotifyMethodDef           = 0x00000001,  
    MDNotifyMemberRef           = 0x00000002,  
    MDNotifyFieldDef            = 0x00000004,  
    MDNotifyTypeRef             = 0x00000008,  
  
    MDNotifyTypeDef             = 0x00000010,  
    MDNotifyParamDef            = 0x00000020,  
    MDNotifyInterfaceImpl       = 0x00000040,  
    MDNotifyProperty            = 0x00000080,  
    MDNotifyEvent               = 0x00000100,  
    MDNotifySignature           = 0x00000200,  
    MDNotifyTypeSpec            = 0x00000400,  
    MDNotifyCustomAttribute     = 0x00000800,  
    MDNotifySecurityValue       = 0x00001000,  
    MDNotifyPermission          = 0x00002000,  
    MDNotifyModuleRef           = 0x00004000,  
  
    MDNotifyNameSpace           = 0x00008000,  
  
    MDNotifyAssemblyRef         = 0x01000000,  
    MDNotifyFile                = 0x02000000,  
    MDNotifyExportedType        = 0x04000000,  
    MDNotifyResource            = 0x08000000  
  
} CorNotificationForTokenMovement;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`MDNotifyDefault`|될 경우 알림을 `mdTypeRef`, `mdMethodDef`, `mdMemberRef`, 또는 `mdFieldDef` 토큰 이동 합니다.|  
|`MDNotifyAll`|모든 토큰 이동 하면 알립니다.|  
|`MDNotifyNone`|토큰 이동에 알리지 않습니다.|  
|`MDNotifyMethodDef`|될 경우 알림을 `mdMethodDef` 토큰이 이동 합니다.|  
|`MDNotifyMemberRef`|될 경우 알림을 `mdMemberRef` 토큰이 이동 합니다.|  
|`MDNotifyFieldDef`|될 경우 알림을 `mdFieldDef` 토큰이 이동 합니다.|  
|`MDNotifyTypeRef`|될 경우 알림을 `mdTypeRef` 토큰이 이동 합니다.|  
|`MDNotifyTypeDef`|될 경우 알림을 `mdTypeDef` 토큰이 이동 합니다.|  
|`MDNotifyParamDef`|될 경우 알림을 `mdParamDef` 토큰이 이동 합니다.|  
|`MDNotifyInterfaceImpl`|될 경우 알림을 `mdInterfaceImpl` 토큰이 이동 합니다.|  
|`MDNotifyProperty`|될 경우 알림을 `mdProperty` 토큰이 이동 합니다.|  
|`MDNotifyEvent`|될 경우 알림을 `mdEvent` 토큰이 이동 합니다.|  
|`MDNotifySignature`|될 경우 알림을 `mdSignature` 토큰이 이동 합니다.|  
|`MDNotifyTypeSpec`|될 경우 알림을 `mdTypeSpec` 토큰이 이동 합니다.|  
|`MDNotifyCustomAttribute`|될 경우 알림을 `mdCustomAttribute` 토큰이 이동 합니다.|  
|`MDNotifySecurityValue`|될 경우 알림을 `mdSecurityValue` 토큰이 이동 합니다.|  
|`MDNotifyPermission`|될 경우 알림을 `mdPermission` 토큰이 이동 합니다.|  
|`MDNotifyModuleRef`|될 경우 알림을 `mdModuleRef` 토큰이 이동 합니다.|  
|`MDNotifyNameSpace`|될 경우 알림을 `mdNameSpace` 토큰이 이동 합니다.|  
|`MDNotifyAssemblyRef`|될 경우 알림을 `mdAssemblyRef` 토큰이 이동 합니다.|  
|`MDNotifyFile`|될 경우 알림을 `mdFile` 토큰이 이동 합니다.|  
|`MDNotifyExportedType`|될 경우 알림을 `mdExportedType` 토큰이 이동 합니다.|  
|`MDNotifyResource`|될 경우 알림을 `mdManifestResource` 토큰이 이동 합니다.|  
  
## <a name="remarks"></a>설명  
 토큰을 다시 매핑할 수 (이동)이 표시 된 메타 데이터를 병합 하는 동안 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorHdr.h  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [메타데이터 열거형](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
