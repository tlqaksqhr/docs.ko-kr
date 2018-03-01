---
title: "ICLRRuntimeInfo 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICLRRuntimeInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo
helpviewer_keywords:
- ICLRRuntimeInfo interface [.NET Framework hosting]
ms.assetid: 287e5ede-b3a7-4ef8-a756-4fca3f285a82
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 11976e8c147b2c5cab2dd67946b561d703028c8a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="iclrruntimeinfo-interface"></a>ICLRRuntimeInfo 인터페이스
버전, 디렉터리 및 부하 상태를 포함 하 여 특정 공용 언어 런타임 (CLR)에 대 한 정보를 반환 하는 메서드를 제공 합니다. 또한이 인터페이스는 런타임을 초기화 하지 않고 런타임 관련 기능을 제공 합니다. 런타임 상대 포함 [LoadLibrary](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-loadlibrary-method.md) 메서드, 특정 모듈 런타임 [GetProcAddress](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getprocaddress-method.md) 메서드를 통해 런타임 제공 인터페이스는 [GetInterface](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md)메서드.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[BindAsLegacyV2Runtime 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-bindaslegacyv2runtime-method.md)|이 런타임의 모든 레거시 CLR 버전 2 정품 인증 정책 결정에 대 한를 바인딩합니다.|  
|[GetDefaultStartupFlags 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getdefaultstartupflags-method.md)|CLR 시작 플래그와 호스트 구성 파일을 가져옵니다.|  
|[GetInterface 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md)|현재 프로세스에 CLR을 로드 하 고 런타임 인터페이스 포인터와 같은 반환 [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md), [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md) 및 [IMetaDataDispenser](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)합니다. 이 메서드를 모두 대체는 `CorBindTo*` 함수입니다.|  
|[GetProcAddress 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getprocaddress-method.md)|이 인터페이스와 연결 된 CLR에서 내보낸 지정된 된 함수 주소를 가져옵니다. 이 메서드를 대체는 [GetRealProcAddress](../../../../docs/framework/unmanaged-api/hosting/getrealprocaddress-function.md) 메서드.|  
|[GetRuntimeDirectory 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getruntimedirectory-method.md)|이 인터페이스와 연결 된 CLR의 설치 디렉터리를 가져옵니다. 이 메서드를 대체는 [GetCORSystemDirectory](../../../../docs/framework/unmanaged-api/hosting/getcorsystemdirectory-function.md) 메서드.|  
|[GetVersionString 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getversionstring-method.md)|와 연결 된 공용 언어 런타임 (CLR) 버전 정보를 가져옵니다는 주어진 [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) 인터페이스입니다. 이 메서드를 대체는 [GetRequestedRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeinfo-function.md) 및 [GetRequestedRuntimeVersion](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md) 메서드.|  
|[IsLoadable 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-isloadable-method.md)|이 인터페이스와 연결 된 런타임을 고려 하는 현재 프로세스에 로드할 수 있는지 여부를 나타냅니다. 이미 프로세스에 로드 될 수 있는 다른 런타임과 합니다.|  
|[IsLoaded 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-isloaded-method.md)|CLR 연관 있는지 여부를 나타냅니다는 [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) 인터페이스는 프로세스에 로드 됩니다.|  
|[IsStarted 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-isstarted-method.md)|여부 CLR와 연결 된 나타냅니다는 [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) 인터페이스 시작 되었습니다.|  
|[LoadErrorString 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-loaderrorstring-method.md)|지정된 된 문화권에 대 한 적절 한 오류 메시지를 HRESULT 값을 변환합니다. 이 메서드를 대체는 [LoadStringRC](../../../../docs/framework/unmanaged-api/hosting/loadstringrc-function.md) 및 [LoadStringRCEx](../../../../docs/framework/unmanaged-api/hosting/loadstringrcex-function.md) 메서드.|  
|[LoadLibrary 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-loadlibrary-method.md)|가 나타내는 CLR의 프레임 워크 디렉터리에서 라이브러리를 로드 한 [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) 인터페이스입니다. 이 메서드를 대체는 [LoadLibraryShim](../../../../docs/framework/unmanaged-api/hosting/loadlibraryshim-function.md) 메서드.|  
|[SetDefaultStartupFlags 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-setdefaultstartupflags-method.md)|CLR 시작 플래그와 호스트 구성 파일을 설정합니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** MetaHost.h  
  
 **라이브러리:** MSCorEE.dll에 리소스로 포함  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [호스팅 인터페이스](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [호스팅](../../../../docs/framework/unmanaged-api/hosting/index.md)
