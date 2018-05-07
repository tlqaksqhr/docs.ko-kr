---
title: FUSION_INSTALL_REFERENCE 구조체
ms.date: 03/30/2017
api_name:
- FUSION_INSTALL_REFERENCE
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- FUSION_INSTALL_REFERENCE
helpviewer_keywords:
- FUSION_INSTALL_REFERENCE structure [.NET Framework fusion]
ms.assetid: ae181ec8-36bf-4ed1-9a02-ca27d417c80b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4685d1a23fdf1874817522a16ccd428d81acd1ac
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="fusioninstallreference-structure"></a>FUSION_INSTALL_REFERENCE 구조체
응용 프로그램은 전역 어셈블리 캐시에는 응용 프로그램이 설치 된 어셈블리 참조를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef struct _FUSION_INSTALL_REFERENCE_ {  
    DWORD    cbSize,  
    DWORD    dwFlags,  
    GUID     guidScheme,  
    LPCWSTR  szIdentifier,  
    LPCWSTR  szNonCanonicalData  
} FUSION_INSTALL_REFERENCE, *LPFUSION_INSTALL_REFERENCE;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`cbSize`|크기 (바이트)에서 구조입니다.|  
|`dwFlags`|다음 버전의 확장에 대 한 예약 되어 있습니다. 이 값은 0 (영) 이어야 합니다.|  
|`guidScheme`|참조를 추가 하는 엔터티. 이 필드는 다음 값 중 하나일 수 있습니다.<br /><br /> -FUSION_REFCOUNT_MSI_GUID: Microsoft Windows Installer를 사용 하 여 설치 된 응용 프로그램에서 어셈블리 참조입니다. `szIdentifier` 필드가로 설정 된 `MSI`, 및 `szNonCanonicalData` 필드가로 설정 된 `Windows Installer`합니다. 이 스키마는 Windows-side-by-side 어셈블리에 사용 됩니다.<br />-FUSION_REFCOUNT_UNINSTALL_SUBKEY_GUID: 어셈블리에 표시 되는 응용 프로그램에서 참조 되는 **프로그램 추가/제거** 인터페이스입니다. `szIdentifier` 필드에서 응용 프로그램을 등록 하는 토큰이 제공 된 **프로그램 추가/제거** 인터페이스입니다.<br />-FUSION_REFCOUNT_FILEPATH_GUID: 파일 시스템에는 파일에 의해 표시 되는 응용 프로그램에서 어셈블리 참조입니다. `szIdentifier` 필드에이 파일의 경로를 제공 합니다.<br />-FUSION_REFCOUNT_OPAQUE_STRING_GUID:는 불투명 문자열에 의해서만 표현 하는 응용 프로그램에서 어셈블리 참조입니다. `szIdentifier` 필드가 불투명 문자열이 제공 합니다. 이 값을 제거 하는 경우 전역 어셈블리 캐시 불투명 참조가 있는지 여부를 확인 하지 않습니다.<br />-FUSION_REFCOUNT_OSINSTALL_GUID:이 값은 예약 되어 있습니다.|  
|`szIdentifier`|전역 어셈블리 캐시에 어셈블리를 설치 하는 응용 프로그램을 식별 하는 고유 문자열입니다. 해당 값의 값에 따라 달라는 `guidScheme` 필드입니다.|  
|`szNonCanonicalData`|엔터티 참조를 추가 하 여만 인식 하는 문자열입니다. 전역 어셈블리 캐시에서는이 문자열을 저장 하지만 사용 하지는 않습니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** Fusion.h  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [Fusion 구조체](../../../../docs/framework/unmanaged-api/fusion/fusion-structures.md)  
 [전역 어셈블리 캐시](../../../../docs/framework/app-domains/gac.md)
