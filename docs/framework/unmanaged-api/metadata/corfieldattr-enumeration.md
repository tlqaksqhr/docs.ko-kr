---
title: "CorFieldAttr 열거형"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorFieldAttr
api_location: mscoree.dll
api_type: COM
f1_keywords: CorFieldAttr
helpviewer_keywords: CorFieldAttr enumeration [.NET Framework metadata]
ms.assetid: 6ae2c4be-212c-4e74-9288-40a11dc26522
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: b199764ea0fb2d02b01d7cf04d1fa8fad743109f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="corfieldattr-enumeration"></a>CorFieldAttr 열거형
필드에 대한 메타데이터를 설명하는 값을 포함합니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef enum CorFieldAttr {  
  
    fdFieldAccessMask           =   0x0007,  
    fdPrivateScope              =   0x0000,  
    fdPrivate                   =   0x0001,  
    fdFamANDAssem               =   0x0002,  
    fdAssembly                  =   0x0003,  
    fdFamily                    =   0x0004,  
    fdFamORAssem                =   0x0005,  
    fdPublic                    =   0x0006,  
  
    fdStatic                    =   0x0010,  
    fdInitOnly                  =   0x0020,  
    fdLiteral                   =   0x0040,  
    fdNotSerialized             =   0x0080,  
  
    fdSpecialName               =   0x0200,  
  
    fdPinvokeImpl               =   0x2000,  
  
    fdReservedMask              =   0x9500,  
    fdRTSpecialName             =   0x0400,  
    fdHasFieldMarshal           =   0x1000,  
    fdHasDefault                =   0x8000,  
    fdHasFieldRVA               =   0x0100  
  
} CorFieldAttr;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`fdFieldAccessMask`|내게 필요한 옵션 정보를 지정합니다.|  
|`fdPrivateScope`|필드는 참조할 수 없음을 지정 합니다.|  
|`fdPrivate`|필드 부모 형식의 액세스할 수 있게 임을 지정 합니다.|  
|`fdFamANDAssem`|필드에 해당 어셈블리의 파생된 클래스에서 액세스할 수 있는지를 지정 합니다.|  
|`fdAssembly`|필드에 해당 어셈블리의 모든 형식에서 액세스할 수 있는지를 지정 합니다.|  
|`fdFamily`|필드가 해당 형식을 액세스할 수 있게 되며 파생 클래스를 지정 합니다.|  
|`fdFamORAssem`|어셈블리의 모든 형식 및 파생된 클래스에서 액세스할 수 있는 필드 임을 지정 합니다.|  
|`fdPublic`|필드에이 범위의 표시 유형이 적용 된 모든 형식에서 액세스할 수 있는지를 지정 합니다.|  
|`fdStatic`|필드가 해당 형식의 멤버가 아닌 인스턴스 멤버 임을 지정 합니다.|  
|`fdInitOnly`|초기화 한 후 필드를 변경할 수를 지정 합니다.|  
|`fdLiteral`|필드 값은 컴파일 타임 상수 임을 지정 합니다.|  
|`fdNotSerialized`|해당 유형이 원격으로 연결할 때는 필드가 serialize 되지 않음을 지정 합니다.|  
|`fdSpecialName`|필드가 특수 문자이 고 해당 이름을 설명 하 고 있음을 지정 방법입니다.|  
|`fdPinvokeImpl`|필드 구현은 PInvoke를 통해 전달 되도록 지정 합니다.|  
|`fdReservedMask`|공용 언어 런타임에서 내부 용도로 예약 되어 있습니다.|  
|`fdRTSpecialName`|공용 언어 런타임 메타 데이터 내부 Api 확인 하도록 지정 합니다 이름의 인코딩을 합니다.|  
|`fdHasFieldMarshal`|필드에 마샬링 정보가 포함 되도록 지정 합니다.|  
|`fdHasDefault`|필드 기본값을 갖도록 지정 합니다.|  
|`fdHasFieldRVA`|필드의 상대 가상 주소를 지정 합니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorHdr.h  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [메타 데이터 열거형](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
