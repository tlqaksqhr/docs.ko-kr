---
title: CorPEKind 열거형
ms.date: 03/30/2017
api_name:
- CorPEKind
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorPEKind
helpviewer_keywords:
- CorPEKind enumeration [.NET Framework metadata]
ms.assetid: 22dc6dea-b1b9-4982-a730-a022d586b117
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b5869eb16bd768d58a6f27a83f2d8d51914a8aed
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33443117"
---
# <a name="corpekind-enumeration"></a>CorPEKind 열거형
에 대 한 호출에서 반환 된 이식 가능한 실행 (PE) 파일을 설명 하는 값이 포함 되어 [imetadataimport2:: Getpekind](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getpekind-method.md)합니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef enum CorPEKind {  
  
    peNot           = 0x00000000,  
    peILonly        = 0x00000001,  
    pe32BitRequired = 0x00000002,  
    pe32Plus        = 0x00000004,  
    pe32Unmanaged   = 0x00000008,  
    pe32BitPreferred= 0x00000010  
  
} CorPEKind;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`peNot`|PE 파일 아님을 나타냅니다.|  
|`peILOnly`|이 PE 파일에 관리 코드가 포함 되어 있음을 나타냅니다.|  
|`pe32BitRequired`|이 PE 파일에서 Win32 호출이 나타냅니다.|  
|`pe32Plus`|64 비트 플랫폼에서이 PE 파일을 실행 함을 나타냅니다.|  
|`pe32Unmanaged`|PE 파일을 네이티브 코드를 나타냅니다.|  
|pe32BitPreferred|이 PE 파일 플랫폼 중립적 이며 선호 하는 32 비트 환경에서 로드할 수를 나타냅니다.|  
  
## <a name="remarks"></a>설명  
 이러한 값을 비트 조합으로 사용할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorHdr.h  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [메타데이터 열거형](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
