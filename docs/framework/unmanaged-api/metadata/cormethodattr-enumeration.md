---
title: "CorMethodAttr 열거형"
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
- CorMethodAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorMethodAttr
helpviewer_keywords:
- CorMethodAttr enumeration [.NET Framework metadata]
ms.assetid: 4e0c3521-e54d-43c1-9857-cc76b49b8ffc
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e4e144b64664a149115f3047b98267c2f218a76e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="cormethodattr-enumeration"></a>CorMethodAttr 열거형
메서드의 기능을 설명 하는 값을 포함 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef enum CorMethodAttr {  
  
    mdMemberAccessMask          =   0x0007,  
    mdPrivateScope              =   0x0000,  
    mdPrivate                   =   0x0001,  
    mdFamANDAssem               =   0x0002,  
    mdAssem                     =   0x0003,  
    mdFamily                    =   0x0004,  
    mdFamORAssem                =   0x0005,  
    mdPublic                    =   0x0006,  
  
    mdStatic                    =   0x0010,  
    mdFinal                     =   0x0020,  
    mdVirtual                   =   0x0040,  
    mdHideBySig                 =   0x0080,  
  
    mdVtableLayoutMask          =   0x0100,  
    mdReuseSlot                 =   0x0000,  
    mdNewSlot                   =   0x0100,  
  
    mdCheckAccessOnOverride     =   0x0200,  
    mdAbstract                  =   0x0400,  
    mdSpecialName               =   0x0800,  
  
    mdPinvokeImpl               =   0x2000,  
    mdUnmanagedExport           =   0x0008,  
  
    mdReservedMask              =   0xd000,  
    mdRTSpecialName             =   0x1000,  
    mdHasSecurity               =   0x4000,  
    mdRequireSecObject          =   0x8000,  
  
} CorMethodAttr;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`mdMemberAccessMask`|멤버 액세스를 지정합니다.|  
|`mdPrivateScope`|멤버를 참조할 수 없음을 지정 합니다.|  
|`mdPrivate`|멤버를 부모 형식에 의해서만 액세스할 수 있는지를 지정 합니다.|  
|`mdFamANDAssem`|멤버에만이 어셈블리의에서 하위 형식에서 액세스할 수 있는지를 지정 합니다.|  
|`mdAssem`|멤버는 어셈블리의 다른 사용자가 액세스할 수 있습니다 임을 지정 합니다.|  
|`mdFamily`|멤버 유형 및 하위 유형 에서만 액세스할 수 임을 지정 합니다.|  
|`mdFamORAssem`|어셈블리의 다른 형식 및 파생된 클래스에서 액세스할 수 있는 멤버 임을 지정 합니다.|  
|`mdPublic`|멤버를 범위에 액세스할 수 있는 모든 형식에서 액세스할 수 있는지를 지정 합니다.|  
|`mdStatic`|인스턴스 멤버 아니라 형식의 일부로 멤버 정의 되도록 지정 합니다.|  
|`mdFinal`|메서드를 재정의할 수 없음을 지정 합니다.|  
|`mdVirtual`|메서드를 재정의할 수 있는지를 지정 합니다.|  
|`mdHideBySig`|메서드 이름 대신 방금 이름과 시그니처를 여는 숨깁니다 지정 합니다.|  
|`mdVtableLayoutMask`|가상 테이블 레이아웃을 지정합니다.|  
|`mdReuseSlot`|가상 테이블에서이 메서드에 대 한 사용 되는 슬롯 다시 사용할 수를 지정 합니다. 이 값이 기본값입니다.|  
|`mdNewSlot`|메서드가 가상 테이블에서 새 슬롯을 항상 가져오도록 지정 합니다.|  
|`mdCheckAccessOnOverride`|가 표시 되는 동일한 형식에서 메서드를 재정의할 수 있는지를 지정 합니다.|  
|`mdAbstract`|메서드가 구현 되지 않았음을 지정 합니다.|  
|`mdSpecialName`|메서드가 특수 문자이 고 해당 이름을 설명 하 고 있음을 지정 방법입니다.|  
|`mdPinvokeImpl`|메서드 구현 PInvoke를 사용 하 여 전달 되도록 지정 합니다.|  
|`mdUnmanagedExport`|비관리 코드로 내보낼 관리 되는 메서드는 메서드가 임을 지정 합니다.|  
|`mdReservedMask`|공용 언어 런타임에서 내부 용도로 예약 되어 있습니다.|  
|`mdRTSpecialName`|공용 언어 런타임 메서드 이름의 인코딩을 확인 하도록 지정 합니다.|  
|`mdHasSecurity`|메서드가 연결 된 보안 갖도록 지정 합니다.|  
|`mdRequireSecObject`|메서드가 보안 코드를 포함 하는 다른 메서드를 호출을 지정 합니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorHdr.h  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [메타데이터 열거형](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
