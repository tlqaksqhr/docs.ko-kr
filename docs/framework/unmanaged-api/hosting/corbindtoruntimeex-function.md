---
title: CorBindToRuntimeEx 함수
ms.date: 03/30/2017
api_name:
- CorBindToRuntimeEx
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- CorBindToRuntimeEx
helpviewer_keywords:
- CorBindToRuntimeEx function [.NET Framework hosting]
ms.assetid: aae9fb17-5d01-41da-9773-1b5b5b642d81
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 553bbd79241292e1fa3b4fe718bda391191a10ae
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2018
ms.locfileid: "42935324"
---
# <a name="corbindtoruntimeex-function"></a>CorBindToRuntimeEx 함수
관리 되지 않는 호스트의 CLR (공용 언어 런타임)을 프로세스로 로드할 수 있도록 합니다. 합니다 [CorBindToRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md) 하 고 `CorBindToRuntimeEx` 함수는 동일한 작업을 수행 하지만 `CorBindToRuntimeEx` 함수를 사용 하면 CLR의 동작을 지정 하는 플래그를 설정할 수 있습니다.  
  
 이 함수에서 사용 중단에 [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]합니다.  
  
 이 함수는 다음을 수행 하는 데 사용 하는 매개 변수 집합을 사용 합니다.  
  
-   로드할 런타임 버전을 지정 합니다.  
  
-   서버 또는 워크스테이션 빌드를 로드할지 여부를 나타냅니다.  
  
-   동시 가비지 수집 또는 비 동시 가비지 컬렉션을 수행할지 여부를 제어 합니다.  
  
> [!NOTE]
>  동시 가비지 수집 WOW64를 실행 하는 응용 프로그램에서 지원 되지 않습니다 x86 에뮬레이터 (이전의 IA-64) Intel Itanium 아키텍처를 구현 하는 64 비트 시스템에서. 64 비트 Windows 시스템에서 WOW64를 사용 하는 방법에 대 한 자세한 내용은 참조 하세요. [실행 중인 32 비트 응용 프로그램](/windows/desktop/WinProg64/running-32-bit-applications)합니다.  
  
-   어셈블리가 도메인 중립적으로 로드 되는지 여부를 제어 합니다.  
  
-   에 대 한 인터페이스 포인터를 가져올는 [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) CLR 인스턴스를 시작 하기 전에 구성에 대 한 추가 옵션을 설정 하려면 사용할 수 있는 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT CorBindToRuntimeEx (  
    [in]  LPCWSTR      pwszVersion,   
    [in]  LPCWSTR      pwszBuildFlavor,   
    [in]  DWORD        startupFlags,   
    [in]  REFCLSID     rclsid,   
    [in]  REFIID       riid,   
    [out] LPVOID FAR  *ppv  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pwszVersion`  
 [in] 로드 하려는 CLR의 버전을 설명 하는 문자열입니다.  
  
 .NET Framework의 버전 번호는 마침표로 구분 하 여 네 부분으로 이루어져: *major.minor.build.revision*합니다. 로 전달 되는 문자열 `pwszVersion` v"문자가" 뒤에 버전 번호 (예: "나옵니다 v1.0.1529")의 처음 세 부분이로 시작 해야 합니다.  
  
 일부 버전의 CLR은 CLR의 이전 버전과 호환성을 지정 하는 정책 문을 사용 하 여 설치 됩니다. 기본적으로 시작 shim 평가 `pwszVersion` 정책 명령문 및 로드에 대 한 최신 버전의 런타임와 호환 되는 요청 된 버전입니다. 호스트 정책 평가 건너뛰고 지정 된 정확한 버전을 로드 하 여 shim을 강제로 실행할 수 있습니다 `pwszVersion` 값을 전달 하 여 `STARTUP_LOADER_SAFEMODE` 에 대 한는 `startupFlags` 아래 설명 된 대로 매개 변수입니다.  
  
 호출자가 null을 지정 하는 경우 `pwszVersion`, `CorBindToRuntimeEx` 설치 된 런타임 버전 번호가 있는.NET Framework 4 런타임 보다 작으면 및 해당 집합에서 최신 버전의 런타임 로드 집합을 식별 합니다. 이전 버전이 설치 된 경우.NET Framework 4 이상 및 실패를 로드 하지 않습니다. Note는 null이 전달 제공 호스트는 런타임 버전이 로드 된 제어 하지 않습니다. 이 방법은 일부 시나리오에서 적합할 수 있습니다, 있지만 것이 좋습니다 호스트를 로드 하려면 특정 버전을 제공 합니다.  
  
 `pwszBuildFlavor`  
 [in] Clr 서버 또는 워크스테이션을 로드할지 여부를 지정 하는 문자열입니다. 유효한 값은 `svr` 및 `wks`입니다. 서버 빌드는 가비지 컬렉션에 대 한 다중 프로세서를 활용 하도록 최적화 되어 워크스테이션 빌드 최적화 되 고 단일 프로세서 컴퓨터에서 실행 하는 클라이언트 응용 프로그램.  
  
 경우 `pwszBuildFlavor` 로 설정 된 워크스테이션 빌드가 null 로드 됩니다. 단일 프로세서 컴퓨터에서 실행 하는 경우 워크스테이션 빌드가 항상 로드 됩니다, 경우에 `pwszBuildFlavor` 로 설정 된 `svr`합니다. 그러나 경우 `pwszBuildFlavor` 로 설정 되어 `svr` 동시 가비지 컬렉션이 지정 되 고 (에 대 한 설명을 참조 하세요.를 `startupFlags` 매개 변수), 서버 빌드가 로드 됩니다.  
  
 `startupFlags`  
 [in] 값의 조합 된 [STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) 열거형입니다. 동시 가비지 컬렉션, 도메인 중립 코드 및 동작을 제어 하는 이러한 플래그는 `pwszVersion` 매개 변수입니다. 기본값은 단일 도메인 플래그가 설정 된 경우. 유효한 값은 다음과 같습니다.  
  
-   `STARTUP_CONCURRENT_GC`  
  
-   `STARTUP_LOADER_OPTIMIZATION_SINGLE_DOMAIN`  
  
-   `STARTUP_LOADER_OPTIMIZATION_MULTI_DOMAIN`  
  
-   `STARTUP_LOADER_OPTIMIZATION_MULTI_DOMAIN_HOST`  
  
-   `STARTUP_LOADER_SAFEMODE`  
  
-   `STARTUP_LEGACY_IMPERSONATION`  
  
-   `STARTUP_LOADER_SETPREFERENCE`  
  
-   `STARTUP_SERVER_GC`  
  
-   `STARTUP_HOARD_GC_VM`  
  
-   `STARTUP_SINGLE_VERSION_HOSTING_INTERFACE`  
  
-   `STARTUP_LEGACY_IMPERSONATION`  
  
-   `STARTUP_DISABLE_COMMITTHREADSTACK`  
  
-   `STARTUP_ALWAYSFLOW_IMPERSONATION`  
  
 이러한 플래그의 설명에 대 한 참조를 [STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) 열거형입니다.  
  
 `rclsid`  
 [in] 합니다 `CLSID` 중 하나를 구현 하는 coclass의 합니다 [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) 또는 [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) 인터페이스입니다. 지원 되는 값은 CLSID_CorRuntimeHost CLSID_CLRRuntimeHost입니다.  
  
 `riid`  
 [in] 합니다 `IID` 에서 요청된 된 인터페이스의 `rclsid`합니다. 지원 되는 값은 IID_ICorRuntimeHost IID_ICLRRuntimeHost입니다.  
  
 `ppv`  
 [out] 반환 된 인터페이스 포인터를 `riid`입니다.  
  
## <a name="remarks"></a>설명  
 하는 경우 `pwszVersion` 존재 하지 않는 런타임 버전 지정 `CorBindToRuntimeEx` CLR_E_SHIM_RUNTIMELOAD의 HRESULT 값을 반환 합니다.  
  
## <a name="execution-context-and-flow-of-windows-identity"></a>실행 컨텍스트 및 Windows Id의 흐름  
 CLR의 버전 1 <xref:System.Security.Principal.WindowsIdentity> 개체 새 스레드를 스레드 풀 타이머 콜백을 등 비동기 지점 간을 흐르지 않습니다. Clr 버전 2.0에에서는 <xref:System.Threading.ExecutionContext> 개체는 현재 실행 중인 스레드에 대 한 일부 정보를 래핑하고 모든 비동기 지점에서 하지만 응용 프로그램 도메인 경계에 걸쳐 있지 흐름입니다. 마찬가지로,는 <xref:System.Security.Principal.WindowsIdentity> 비동기 지점 간에 개체도 전달 합니다. 따라서 스레드에서 현재 가장 있으면도 전달 됩니다.  
  
 두 가지 방법으로 흐름을 변경할 수 있습니다.  
  
1.  수정 하 여는 <xref:System.Threading.ExecutionContext> 스레드별 기준 흐름을 억제할 수 설정 (참조를 <xref:System.Threading.ExecutionContext.SuppressFlow%2A>를 <xref:System.Security.SecurityContext.SuppressFlow%2A>, 및 <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A> 메서드).  
  
2.  버전 1 호환성 모드로 프로세스 기본 모드를 변경 하 여 위치를 <xref:System.Security.Principal.WindowsIdentity> 개체에 관계 없이 모든 비동기 지점 간에 전달 되지 않습니다는 <xref:System.Threading.ExecutionContext> 현재 스레드에 설정 합니다. 기본 모드를 변경 하는 방법을 CLR을 로드 하는 관리 되는 실행 파일 또는 관리 되지 않는 호스팅 인터페이스 사용 되는 여부에 따라 달라 집니다.  
  
    1.  관리 되는 실행 파일을 설정 해야 합니다는 `enabled` 특성을 [ \<legacyImpersonationPolicy >](../../../../docs/framework/configure-apps/file-schema/runtime/legacyimpersonationpolicy-element.md) 요소를 `true`입니다.  
  
    2.  관리 되지 않는 호스팅 인터페이스를 설정 합니다 `STARTUP_LEGACY_IMPERSONATION` 플래그를 `startupFlags` 호출 될 때 매개 변수는 `CorBindToRuntimeEx` 함수입니다.  
  
     버전 1 호환성 모드에는 전체 프로세스 및 프로세스에서 모든 응용 프로그램 도메인에 적용 됩니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** MSCorEE.h  
  
 **라이브러리:** MSCorEE.dll  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [CorBindToCurrentRuntime 함수](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)  
 [CorBindToRuntime 함수](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md)  
 [CorBindToRuntimeByCfg 함수](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)  
 [CorBindToRuntimeHost 함수](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md)  
 [ICorRuntimeHost 인터페이스](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)  
 [사용되지 않는 CLR 호스팅 함수](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
