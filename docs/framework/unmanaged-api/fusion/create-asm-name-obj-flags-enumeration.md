---
title: "CREATE_ASM_NAME_OBJ_FLAGS 열거형"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CREATE_ASM_NAME_OBJ_FLAGS
api_location: fusion.dll
api_type: COM
f1_keywords: CREATE_ASM_NAME_OBJ_FLAGS
helpviewer_keywords: CREATE_ASM_NAME_OBJ_FLAGS enumeration [.NET Framework fusion]
ms.assetid: a5ed2fd0-c7d2-4603-aaca-5d0caad92675
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 61e9bea623e38b1416721773d8739bc6e6748909
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="createasmnameobjflags-enumeration"></a>CREATE_ASM_NAME_OBJ_FLAGS 열거형
특성을 지정 하는 [IAssemblyName 인터페이스](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) 하 여 생성 될 때 개체는 [CreateAssemblyNameObject](../../../../docs/framework/unmanaged-api/fusion/createassemblynameobject-function.md) 함수입니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef enum {  
  
    CANOF_PARSE_DISPLAY_NAME            = 0x1,  
    CANOF_SET_DEFAULT_VALUES            = 0x2,  
    CANOF_VERIFY_FRIEND_ASSEMBLYNAME    = 0x4,  
    CANOF_PARSE_FRIEND_DISPLAY_NAME     =   
        CANOF_PARSE_DISPLAY_NAME | CANOF_VERIFY_FRIEND_ASSEMBLYNAME  
  
} CREATE_ASM_NAME_OBJ_FLAGS;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`CANOF_PARSE_DISPLAY_NAME`|전달 된 매개 변수 텍스트 id 임을 나타냅니다.|  
|`CANOF_SET_DEFAULT_VALUES`|몇 개의 기본값을 설정합니다.|  
|`CANOF_VERIFY_FRIEND_ASSEMBLYNAME`|Friend 어셈블리 규칙 (이름 및 공개 키)를 확인합니다. 이 멤버는 내부적 으로만 사용 합니다.|  
|`CANOF_PARSE_FRIEND_DISPLAY_NAME`|조합 된 `CANOF_PARSE_DISPLAY_NAME` 및 `CANOF_VERIFY_FRIEND_ASSEMBLYNAME` 플래그입니다. 이 멤버는 내부적 으로만 사용 합니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** Fusion.h  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [IAssemblyName 인터페이스](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)  
 [CreateAssemblyNameObject 함수](../../../../docs/framework/unmanaged-api/fusion/createassemblynameobject-function.md)  
 [Fusion 열거형](../../../../docs/framework/unmanaged-api/fusion/fusion-enumerations.md)
