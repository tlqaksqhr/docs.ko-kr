---
title: "CorImportOptions 열거형"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorImportOptions
api_location: mscoree.dll
api_type: COM
f1_keywords: CorImportOptions
helpviewer_keywords: CorImportOptions enumeration [.NET Framework metadata]
ms.assetid: 4e5d03cb-97c9-4ff4-8dbd-17d94ee374d3
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e9af7bbb6dd7cfa488f72ec99f9cfd848f04e72f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="corimportoptions-enumeration"></a>CorImportOptions 열거형
현재 범위를 벗어난 어셈블리를 가져오는 중의 동작을 제어하는 플래그 값을 포함합니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef enum CorImportOptions {  
  
    MDImportOptionDefault                = 0x00000000,  
    MDImportOptionAll                    = 0xFFFFFFFF,  
    MDImportOptionAllTypeDefs            = 0x00000001,  
    MDImportOptionAllMethodDefs          = 0x00000002,  
    MDImportOptionAllFieldDefs           = 0x00000004,  
    MDImportOptionAllProperties          = 0x00000008,  
    MDImportOptionAllEvents              = 0x00000010,  
    MDImportOptionAllCustomAttributes    = 0x00000020,  
    MDImportOptionAllExportedTypes       = 0x00000040  
  
} CorImportOptions;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`MDImportOptionDefault`|삭제 된 레코드는 건너 뜁니다 하는 기본 동작을 나타냅니다.|  
|`MDImportOptionAll`|모든 메타 데이터를 열거 해야 함을 나타냅니다.|  
|`MDImportOptionAllTypeDefs`|삭제 된 항목을 포함 하 여 모든 형식 정의 열거 해야 함을 나타냅니다.|  
|`MDImportOptionAllMethodDefs`|모든 MethodDefs, 삭제 된 항목을 포함 하 여 열거 해야 함을 나타냅니다.|  
|`MDImportOptionAllFieldDefs`|삭제 된 항목을 포함 하 여 모든 Fielddef 열거 해야 함을 나타냅니다.|  
|`MDImportOptionAllProperties`|모든 PropertyDefs, 삭제 된 항목을 포함 하 여 열거 해야 함을 나타냅니다.|  
|`MDImportOptionAllEvents`|삭제 된 항목을 포함 하 여 모든 Eventdef 열거 해야 함을 나타냅니다.|  
|`MDImportOptionAllCustomAttributes`|삭제 된 항목을 포함 하 여 모든 사용자 지정 특성을 열거 해야 함을 나타냅니다.|  
|`MDImportOptionAllExportedTypes`|삭제 된 항목을 포함 하는 모든 내보낸된 형식을 열거 해야 함을 나타냅니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorHdr.h  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [메타데이터 열거형](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
