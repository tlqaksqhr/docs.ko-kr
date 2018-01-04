---
title: "COR_NATIVE_LINK 구조체"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_NATIVE_LINK
api_location: mscoree.dll
api_type: COM
f1_keywords: COR_NATIVE_LINK
helpviewer_keywords: COR_NATIVE_LINK structure [.NET Framework metadata]
ms.assetid: 6ef78d3c-1c69-4141-b687-dcb065b7a74d
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 63e5946e98e7c862a2502a71a02e605a38086618
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="cornativelink-structure"></a>COR_NATIVE_LINK 구조체
네이티브 코드를 연결하는 데 사용되는 정보를 포함합니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef struct   
{  
    BYTE        m_linkType;  
    BYTE        m_flags;  
    mdMemberRef m_entryPoint;  
} COR_NATIVE_LINK;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`m_linkType`|네이티브 코드에서 연결 형식입니다. 이 값은 중 하나는 [CorNativeLinkType](../../../../docs/framework/unmanaged-api/metadata/cornativelinktype-enumeration.md) 값입니다.|  
|`m_flags`|네이티브 코드를 연결할 때 링커에서 사용 하는 플래그입니다. 이 값은 중 하나는 [CorNativeLinkFlags](../../../../docs/framework/unmanaged-api/metadata/cornativelinkflags-enumeration.md) 값입니다.|  
|`m_entryPoint`|진입점을 나타내는 MemberRef 메타 데이터 토큰입니다. 형식은 `lib:entrypoint`합니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** Cor.h  
  
 **라이브러리:** MsCorEE.dll에서 리소스로 사용  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [메타데이터 구조체](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)  
 [CorNativeLinkType 열거형](../../../../docs/framework/unmanaged-api/metadata/cornativelinktype-enumeration.md)  
 [CorNativeLinkFlags 열거형](../../../../docs/framework/unmanaged-api/metadata/cornativelinkflags-enumeration.md)
