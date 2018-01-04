---
title: "CorPinvokeMap 열거형"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorPinvokeMap
api_location: mscoree.dll
api_type: COM
f1_keywords: CorPinvokeMap
helpviewer_keywords: CorPinvokeMap enumeration [.NET Framework metadata]
ms.assetid: f14f986e-f6ce-42bc-aa23-18150c46d28c
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0e0771ce54e7e2973525bfcf4aba4c1f7ddf0a52
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="corpinvokemap-enumeration"></a>CorPinvokeMap 열거형
PInvoke 호출에 대 한 옵션을 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef enum  CorPinvokeMap {  
  
    pmNoMangle          = 0x0001,  
  
    pmCharSetMask       = 0x0006,  
    pmCharSetNotSpec    = 0x0000,  
    pmCharSetAnsi       = 0x0002,  
    pmCharSetUnicode    = 0x0004,  
    pmCharSetAuto       = 0x0006,  
  
    pmBestFitUseAssem   = 0x0000,  
    pmBestFitEnabled    = 0x0010,  
    pmBestFitDisabled   = 0x0020,  
    pmBestFitMask       = 0x0030,  
  
    pmThrowOnUnmappableCharUseAssem   = 0x0000,  
    pmThrowOnUnmappableCharEnabled    = 0x1000,  
    pmThrowOnUnmappableCharDisabled   = 0x2000,  
    pmThrowOnUnmappableCharMask       = 0x3000,  
  
    pmSupportsLastError = 0x0040,   
  
    pmCallConvMask      = 0x0700,  
    pmCallConvWinapi    = 0x0100,  
    pmCallConvCdecl     = 0x0200,  
    pmCallConvStdcall   = 0x0300,  
    pmCallConvThiscall  = 0x0400,  
    pmCallConvFastcall  = 0x0500,  
  
    pmMaxValue          = 0xFFFF  
  
} CorPinvokeMap;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`pmNoMangle`|각 멤버 이름은 지정 된 대로 사용 합니다.|  
|`pmCharSetMask`|예약됨.|  
|`pmCharSetNotSpec`|예약됨.|  
|`pmCharSetAnsi`|문자열로 다중 바이트 문자열을 마샬링하십시오.|  
|`pmCharSetUnicode`|유니코드 2 바이트 문자로 문자열을 마샬링하십시오.|  
|`pmCharSetAuto`|자동으로 대상 운영 체제에 대 한 적절 하 게 문자열을 마샬링하십시오. 기본값은 Windows NT, Windows 2000, Windows XP 및 Windows Server 2003 제품군;에서 유니코드 기본값은 Windows 98 및 Windows me ANSI|  
|`pmBestFitUseAssem`|예약됨.|  
|`pmBestFitEnabled`|ANSI 문자 집합에 정확 하 게 일치 없는 유니코드 문자의 최적된 매핑을 수행 합니다.|  
|`pmBestFitDisabled`|유니코드 문자의 최적된 매핑을 수행 하지 마십시오. 이 경우 모든 매핑할 수 없는 문자를으로 대체 됩니다는 '?'입니다.|  
|`pmBestFitMask`|예약됨.|  
|`pmThrowOnUnmappableCharUseAssem`|예약됨.|  
|`pmThrowOnUnmappableCharEnabled`|Interop 마샬러는 매핑할 수 없는 문자를 발견할 때 예외를 throw 합니다.|  
|`pmThrowOnUnmappableCharDisabled`|Interop 마샬러는 매핑할 수 없는 문자를 발견 한 경우 예외를 throw 하지 않습니다.|  
|`pmThrowOnUnmappableCharMask`|예약됨|  
|`pmSupportsLastError`|호출 수신자를 Win32 호출을 허용 `SetLastError` 특성 사용 메서드에서 반환 하기 전에 함수입니다.|  
|`pmCallConvMask`|예약됨|  
|`pmCallConvWinapi`|기본 플랫폼 호출 규칙을 사용 합니다. 예를 들어 Windows에서 기본값은 `StdCall` 및에 Windows CE.NET `Cdecl`합니다.|  
|`pmCallConvCdecl`|사용 하 여 `Cdecl` 호출 규칙입니다. 이 경우 호출자가 스택을 정리 합니다. 이렇게 하면 사용 함수를 호출 `varargs` (즉, 가변 개수의 매개 변수를 허용 하는 함수).|  
|`pmCallConvStdcall`|사용 하 여 `StdCall` 호출 규칙입니다. 이 경우 호출 수신자가 스택을 정리 합니다. 이것은 기본 규칙 호출 플랫폼 관리 되지 않는 함수를 호출 합니다.|  
|`pmCallConvThiscall`|사용 하 여 `ThisCall` 호출 규칙입니다. 이 경우에 첫 번째 매개 변수는 `this` 포인터가 ECX 레지스터에 저장 됩니다. 다른 매개 변수는 스택에 푸시됩니다. `ThisCall` 관리 되지 않는 DLL에서 내보낸 클래스의 메서드를 호출 하는 호출 규칙이 사용 됩니다.|  
|`pmCallConvFastcall`|예약됨.|  
|`pmMaxValue`|예약됨.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorHdr.h  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [메타데이터 열거형](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
