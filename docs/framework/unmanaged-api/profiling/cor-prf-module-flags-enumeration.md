---
title: COR_PRF_MODULE_FLAGS 열거형
ms.date: 03/30/2017
api_name:
- COR_PRF_MODULE_FLAGS
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_MODULE_FLAGS
helpviewer_keywords:
- COR_PRF_MODULE_FLAGS enumeration [.NET Framework profiling]
ms.assetid: 7bc3a938-0df1-4739-9ff1-89cff454b704
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 48617022940d889abedb9a9d25f04782371c4a5f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="corprfmoduleflags-enumeration"></a>COR_PRF_MODULE_FLAGS 열거형
모듈의 속성을 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef enum  
{  
    COR_PRF_MODULE_DISK             = 0x00000001,  
    COR_PRF_MODULE_NGEN             = 0x00000002,  
    COR_PRF_MODULE_DYNAMIC          = 0x00000004,  
    COR_PRF_MODULE_COLLECTIBLE      = 0x00000008,  
    COR_PRF_MODULE_RESOURCE         = 0x00000010,  
    COR_PRF_MODULE_FLAT_LAYOUT      = 0x00000020,  
    COR_PRF_MODULE_WINDOWS_RUNTIME  = 0x00000040  
}   COR_PRF_MODULE_FLAGS;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|COR_PRF_MODULE_DISK|모듈은 디스크에서 로드 되었습니다.|  
|COR_PRF_MODULE_NGEN|모듈 네이티브 이미지 생성기 (Ngen.exe)에 의해 생성 되었습니다.|  
|COR_PRF_MODULE_DYNAMIC|모듈의 메서드에 의해 생성 된 <xref:System.Reflection.Emit?displayProperty=nameWithType> 네임 스페이스입니다.|  
|COR_PRF_MODULE_COLLECTIBLE|모듈의 수명은 가비지 수집기에 의해 관리 됩니다.|  
|COR_PRF_MODULE_RESOURCE|모듈 메타 데이터를 포함 하 고 자원으로 엄격 하 게 사용 됩니다. 이 비트는 관리 되는 것에 해당 되는 <xref:System.Reflection.Module.IsResource%2A?displayProperty=nameWithType> 메서드.|  
|COR_PRF_MODULE_FLAT_LAYOUT|메모리에 모듈의 레이아웃은 플랫 매핑되지 않습니다. 모듈에이 비트는 설정, 프로파일러는 읽을 이식 가능한 실행 (PE) 파일 헤더에서 직접 정보를 가상 Rva (상대 주소) 헤더에서를 해석할 때 주의 해야 합니다.|  
|COR_PRF_MODULE_WINDOWS_RUNTIME|Windows 런타임 콘텐츠 형식 플래그는이 모듈의이 어셈블리에 대 한 메타 데이터에서 설정 됩니다. 이 경우 모든 Windows 메타 데이터 (.winmd) 모듈에 대 한 합니다.|  
  
## <a name="remarks"></a>설명  
 COR_PRF_MODULE_FLAGS의 비트를 프로파일러에 반환 되는 `pdwModuleFlags` 의 출력 매개 변수는 [icorprofilerinfo3:: Getmoduleinfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getmoduleinfo2-method.md) 메서드. 두 개 이상의 플래그의 일부 조합은 가능 하지만 일부 조합은 가능 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [프로파일링 열거형](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
