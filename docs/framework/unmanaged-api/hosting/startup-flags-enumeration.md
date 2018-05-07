---
title: STARTUP_FLAGS 열거형
ms.date: 03/30/2017
api_name:
- STARTUP_FLAGS
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- STARTUP_FLAGS
helpviewer_keywords:
- STARTUP_FLAGS enumeration [.NET Framework hosting]
ms.assetid: 4f043594-0c45-4bc6-988e-a6793f0d8d06
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bc1d3ffc34cd74d68bf10cb677b68f0a75bb7c67
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="startupflags-enumeration"></a>STARTUP_FLAGS 열거형
공용 언어 런타임 (CLR)의 시작 동작을 나타내는 값을 포함 합니다. 기본적으로 가비지 컬렉션은 비 동시 및 전용 기본 클래스 라이브러리는 도메인 중립적으로 영역에 로드 됩니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef enum {  
    STARTUP_CONCURRENT_GC                         = 0x1,  
    STARTUP_LOADER_OPTIMIZATION_MASK              = 0x3<<1,  
    STARTUP_LOADER_OPTIMIZATION_SINGLE_DOMAIN     = 0x1<<1,  
    STARTUP_LOADER_OPTIMIZATION_MULTI_DOMAIN      = 0x2<<1,  
    STARTUP_LOADER_OPTIMIZATION_MULTI_DOMAIN_HOST = 0x3<<1,  
  
    STARTUP_LOADER_SAFEMODE                       = 0x10,  
    STARTUP_LOADER_SETPREFERENCE                  = 0x100,  
  
    STARTUP_SERVER_GC                             = 0x1000,  
    STARTUP_HOARD_GC_VM                           = 0x2000,  
  
    STARTUP_SINGLE_VERSION_HOSTING_INTERFACE      = 0x4000,  
    STARTUP_LEGACY_IMPERSONATION                  = 0x10000,  
    STARTUP_DISABLE_COMMITTHREADSTACK             = 0x20000,  
    STARTUP_ALWAYSFLOW_IMPERSONATION              = 0x40000,  
    STARTUP_TRIM_GC_COMMIT                        = 0x80000,  
  
    STARTUP_ETW                                   = 0x100000,  
    STARTUP_ARM                                   = 0x400000  
} STARTUP_FLAGS;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`STARTUP_CONCURRENT_GC`|동시 가비지 수집을 사용 해야 함을 지정 합니다. 호출자에 게 서버 빌드 및 동시 가비지 컬렉션은 단일 프로세서 컴퓨터에서을 요청 하는 경우 워크스테이션 빌드 및 비 동시 가비지 수집 대신 실행 됩니다. **참고:** 동시 가비지 수집 WOW64를 실행 중인 응용 프로그램에서 지원 되지 않습니다 x86 에뮬레이터 (이전의 ia-64) Intel Itanium 아키텍처를 구현 하는 64 비트 시스템에서 합니다. 64 비트 Windows 시스템에서 w o w 64를 사용 하는 방법에 대 한 자세한 내용은 참조 [실행 중인 32 비트 응용 프로그램](http://msdn.microsoft.com/library/windows/desktop/aa384249.aspx)합니다.|  
|`STARTUP_LOADER_OPTIMIZATION_MASK`|해당 로더 최적화가 실행을 지정 합니다.|  
|`STARTUP_LOADER_OPTIMIZATION_SINGLE_DOMAIN`|어셈블리가 없는 도메인 중립적으로 로드 되도록 지정 합니다.|  
|`STARTUP_LOADER_OPTIMIZATION_MULTI_DOMAIN`|모든 어셈블리가 도메인 중립적으로 로드 되도록 지정 합니다.|  
|`STARTUP_LOADER_OPTIMIZATION_MULTI_DOMAIN_HOST`|도메인 중립적으로 로드 된 모든 강력한 이름의 어셈블리를 지정 합니다.|  
|`STARTUP_LOADER_SAFEMODE`|CLR 버전 정책에 전달 된 버전에 적용 되지 않습니다 지정 합니다. CLR의 지정 된 버전만 로드 됩니다. Shim 호환 되는 최신 버전을 확인 하기 위해 정책을 평가 하지 않습니다.|  
|`STARTUP_LOADER_SETPREFERENCE`|기본 런타임을 설정 하지만 실제로 시작 하지 수는 지정 합니다.|  
|`STARTUP_SERVER_GC`|서버 가비지 수집을 사용 하도록 지정 합니다.|  
|`STARTUP_HOARD_GC_VM`|가비지 수집이 사용 되는 가상 주소를 유지 합니다를 지정 합니다.|  
|`STARTUP_SINGLE_VERSION_HOSTING_INTERFACE`|호스팅 인터페이스 혼합 허용 되지 않습니다 지정 합니다.|  
|`STARTUP_LEGACY_IMPERSONATION`|기본적으로 가장 비동기 지점 간에 전달 되지 않도록 지정 합니다.|  
|`STARTUP_DISABLE_COMMITTHREADSTACK`|전체 스레드 스택 하지 커밋되어야 함을 스레드 실행을 시작할 때 지정 합니다.|  
|`STARTUP_ALWAYSFLOW_IMPERSONATION`|관리 되는 가장 및 플랫폼을 통해 수행 호출을 지정 합니다. 비동기 지점에 가로로 표시 합니다. 기본적으로 관리 되는 가장만 비동기 지점 간에 흐릅니다.|  
|`STARTUP_TRIM_GC_COMMIT`|시스템 메모리가 부족 한 경우 가비지 수집 커밋된 공간을 적게 사용 되도록 지정 합니다. 참조 `gcTrimCommitOnLowMemory` 에 [공유 웹 호스팅을 위한 최적화](../../../../docs/standard/garbage-collection/optimization-for-shared-web-hosting.md)합니다.|  
|`STARTUP_ETW`|공용 언어 런타임 이벤트에 대 한 이벤트 추적에 대 한 ETW (Windows)을 사용할 수 있는지를 지정 합니다. Windows Vista부터, 이벤트 추적 항상 사용 되므로이 플래그는 영향을 주지 않습니다. 참조 [.NET Framework 로깅 제어](../../../../docs/framework/performance/controlling-logging.md)합니다.|  
|`STARTUP_ARM`|응용 프로그램 도메인 리소스 모니터링은 사용할 수 있도록 지정 합니다. 참조는 <xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=nameWithType> 속성 및 [ \<appDomainResourceMonitoring > 요소](../../../../docs/framework/configure-apps/file-schema/runtime/appdomainresourcemonitoring-element.md)합니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** MSCorEE.h  
  
 **라이브러리:** MSCorEE.dll  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [호스팅 열거형](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
