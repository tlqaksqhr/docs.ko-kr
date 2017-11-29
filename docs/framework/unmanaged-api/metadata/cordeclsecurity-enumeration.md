---
title: "CorDeclSecurity 열거형"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDeclSecurity
api_location: mscoree.dll
api_type: COM
f1_keywords: CorDeclSecurity
helpviewer_keywords: CorDeclSecurity enumeration [.NET Framework metadata]
ms.assetid: 864f1267-d267-4696-8df7-1f83f8444d6f
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: e5ba8de0a8db315e5c06586ad2248cfea241653b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="cordeclsecurity-enumeration"></a>CorDeclSecurity 열거형
선언적 보안을 사용하여 수행할 수 있는 보안 작업을 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef enum CorDeclSecurity {  
  
    dclActionMask               =   0x001f,  
    dclActionNil                =   0x0000,  
    dclRequest                  =   0x0001,  
    dclDemand                   =   0x0002,  
    dclAssert                   =   0x0003,  
    dclDeny                     =   0x0004,  
    dclPermitOnly               =   0x0005,  
    dclLinktimeCheck            =   0x0006,  
    dclInheritanceCheck         =   0x0007,  
    dclRequestMinimum           =   0x0008,  
    dclRequestOptional          =   0x0009,  
    dclRequestRefuse            =   0x000a,  
    dclPrejitGrant              =   0x000b,  
    dclPrejitDenied             =   0x000c,  
    dclNonCasDemand             =   0x000d,  
    dclNonCasLinkDemand         =   0x000e,  
    dclNonCasInheritance        =   0x000f,  
    dclLinkDemandChoice         =   0x0010,  
    dclInheritanceDemandChoice  =   0x0011,  
    dclDemandChoice             =   0x0012,  
    dclMaximumValue             =   0x0012  
  
} CorDeclSecurity;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`dclActionMask`|예약됨.|  
|`dclActionNil`|예약됨.|  
|`dclRequest`|예약됨.|  
|`dclDemand`|호출 스택의 상위에 있는 모든 호출자에게 현재 사용 권한 개체가 지정한 사용 권한이 부여되었어야 합니다.|  
|`dclAssert`|스택의 상위 호출자가 리소스에 액세스할 수 있는 권한이 부여 되지 않았습니다 않더라도 호출 코드에서 현재 사용 권한 개체로 식별 되는 리소스를 액세스할 수 있습니다.|  
|`dclDeny`|현재 사용 권한 개체가 지정한 리소스에 액세스 하는 기능에 액세스할 권한이 하는 경우에 호출자에 게 액세스가 거부 되었습니다.|  
|`dclPermitOnly`|코드에 다른 리소스에 액세스할 수 있는 권한이 부여되더라도 이 권한 개체가 지정한 리소스에만 액세스할 수 있습니다.|  
|`dclLinktimeCheck`|직접 실행 호출자는 지정된 된 기간 동안에 대해 지정한 사용 권한을 부여 합니다.|  
|`dclInheritanceCheck`|다른 클래스를 상속 하거나 메서드를 재정의 하는 파생된 클래스는 지정 된 권한이 부여 된 해야 합니다.|  
|`dclRequestMinimum`|호출자에 게 코드를 실행 하는 데 필요한 최소 사용 권한을 요청할 수 있습니다. 이 작업은 어셈블리 범위 내에서만 사용할 수 있습니다.|  
|`dclRequestOptional`|호출자에 게는 선택 사항 (실행 하려면 필요 없음) 하는 추가 권한을 요청할 수 있습니다. 이 요청은 특별히 요청되지 않은 다른 모든 사용 권한을 암시적으로 거부합니다. 이 작업은 어셈블리 범위 내에서만 사용할 수 있습니다.|  
|`dclRequestRefuse`|잘못 사용 될 수 있는 사용 권한에 대 한 호출자의 요청을 부여 되지 않습니다. 이 작업은 어셈블리 범위 내에서만 사용할 수 있습니다.|  
|`dclPrejitGrant`|예약됨.|  
|`dclPrejitDenied`|예약됨.|  
|`dclNonCasDemand`|예약됨.|  
|`dclNonCasLinkDemand`|직접 실행 호출자에게 지정된 사용 권한이 부여되었어야 합니다.|  
|`dclNonCasInheritance`|예약됨.|  
|`dclLinkDemandChoice`|예약됨.|  
|`dclInheritanceDemandChoice`|예약됨.|  
|`dclDemandChoice`|예약됨.|  
|`dclMaximumValue`|예약됨.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorHdr.h  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [메타 데이터 열거형](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
