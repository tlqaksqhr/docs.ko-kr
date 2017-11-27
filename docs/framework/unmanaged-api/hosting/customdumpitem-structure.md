---
title: "CustomDumpItem 구조체"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CustomDumpItem
api_location: mscoree.dll
api_type: COM
f1_keywords: CustomDumpItem
helpviewer_keywords: CustomDumpItem structure [.NET Framework hosting]
ms.assetid: fd9085ff-7beb-4c38-97f0-037cd8ba4f65
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 547204385b20d5b7e64bda9ea0a9e790f2ba3471
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="customdumpitem-structure"></a>CustomDumpItem 구조체
오류 보고에 사용자 지정 덤프에 추가할 항목에 설명 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
struct {  
    ECustomDumpItemKind itemKind;   
    union {  
        UINT_PTR pReserved;  
    }  
} CustomDumpItem;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`itemKind`|[ECustomDumpItemKind](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md) 추가 될 항목의 종류를 나타내는 값입니다.|  
|`pReserved`|현재 사용 되지 않습니다. 공용 구조체에 추가 된 모든 항목 포인터 크기 보다 더 커야 합니다. 경우는 `struct` 은 필수, 별도로 할당 하며 가리킵니다.|  
  
## <a name="remarks"></a>설명  
 [Iclrerrorreportingmanager:: Begincustomdump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md) 형식의 매개 변수 사용 `CustomDumpItem`합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** MSCorEE.idl  
  
 **라이브러리:** MSCorEE.dll에 리소스로 포함  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [호스팅 구조체](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
