---
title: Fusion 전역 정적 함수
ms.date: 03/30/2017
helpviewer_keywords:
- unmanaged global static functions [.NET Framework], fusion
- fusion global static functions [.NET Framework]
- global static functions [.NET Framework fusion]
ms.assetid: 229b2188-9168-4b44-a987-e1f515494688
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 86cb59c0935c193a9865d5ace5fe11c96226d9e8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="fusion-global-static-functions"></a>Fusion 전역 정적 함수
이 여기서는 fusion API를 사용 하는 관리 되지 않는 전역 정적 함수를 설명 합니다.  
  
## <a name="in-this-section"></a>섹션 내용  
 [ClearDownloadCache 함수](../../../../docs/framework/unmanaged-api/fusion/cleardownloadcache-function.md)  
 다운로드 된 어셈블리의 전역 어셈블리 캐시를 지웁니다.  
  
 [CompareAssemblyIdentity 함수](../../../../docs/framework/unmanaged-api/fusion/compareassemblyidentity-function.md)  
 동일한 지 여부를 확인 하려면 두 개의 어셈블리 id를 비교 합니다.  
  
 [CreateApplicationContext 함수](../../../../docs/framework/unmanaged-api/fusion/createapplicationcontext-function.md)  
 내부 전용입니다. (이 함수는.NET Framework 인프라를 지원 하며 사용자 코드에서 직접 사용할 수 없습니다.)  
  
 [CreateAssemblyCache 함수](../../../../docs/framework/unmanaged-api/fusion/createassemblycache-function.md)  
 새에 대 한 포인터를 가져옵니다 [IAssemblyCache](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md) 전역 어셈블리 캐시를 나타내는 인스턴스입니다.  
  
 [CreateAssemblyEnum 함수](../../../../docs/framework/unmanaged-api/fusion/createassemblyenum-function.md)  
 에 대 한 포인터를 가져옵니다는 [IAssemblyEnum](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md) 를 나타내는 지정된 된 어셈블리에 존재 하는 개체의 목록입니다.  
  
 [CreateAssemblyNameObject 함수](../../../../docs/framework/unmanaged-api/fusion/createassemblynameobject-function.md)  
 에 대 한 포인터를 가져옵니다는 [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) 지정한 이름 가진 어셈블리의 고유 id를 나타내는 인스턴스입니다.  
  
 [CreateHistoryReader 함수](../../../../docs/framework/unmanaged-api/fusion/createhistoryreader-function.md)  
 지정된 된 파일에 대 한 기록 판독기를 만듭니다.  
  
 [CreateInstallReferenceEnum 함수](../../../../docs/framework/unmanaged-api/fusion/createinstallreferenceenum-function.md)  
 에 대 한 포인터를 가져옵니다는 [IInstallReferenceEnum](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceenum-interface.md) 목록이 지정된 된 어셈블리에 대 한 응용 프로그램의 한 참조를 나타내는 인스턴스입니다.  
  
 [GetAppIdAuthority 함수](../../../../docs/framework/unmanaged-api/fusion/getappidauthority-function.md)  
 에 대 한 포인터를 가져옵니다는 [IAppIdAuthority](../../../../docs/framework/unmanaged-api/fusion/iappidauthority-interface.md) 응용 프로그램 id 및 참조에 대 한 키를 관리 하는 인스턴스입니다.  
  
 [GetAssemblyIdentityFromFile 함수](../../../../docs/framework/unmanaged-api/fusion/getassemblyidentityfromfile-function.md)  
 에 대 한 포인터를 가져옵니다는 `IUnknown` 개체와 지정한 `IID` 지정 된 파일 경로에 있는 어셈블리에 있습니다.  
  
 [GetCachePath 함수](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md)  
 지정된 된 플래그를 사용 하 여 캐시 된 어셈블리에 경로 가져옵니다.  
  
 [GetHistoryFileDirectory 함수](../../../../docs/framework/unmanaged-api/fusion/gethistoryfiledirectory-function.md)  
 응용 프로그램 기록 디렉터리의 경로 검색 합니다.  
  
 [GetIdentityAuthority 함수](../../../../docs/framework/unmanaged-api/fusion/getidentityauthority-function.md)  
 에 대 한 포인터를 가져옵니다는 [IIdentityAuthority](../../../../docs/framework/unmanaged-api/fusion/iidentityauthority-interface.md) 코드 개체에 대 한 키를 관리 하는 인스턴스입니다.  
  
 [IsFrameworkAssembly 함수](../../../../docs/framework/unmanaged-api/fusion/isframeworkassembly-function.md)  
 지정된 된 어셈블리 관리 되는지 여부를 나타내는 값을 가져옵니다.  
  
 [NukeDownloadedCache 함수](../../../../docs/framework/unmanaged-api/fusion/nukedownloadedcache-function.md)  
 공용 언어 런타임에서 다운로드 캐시를 삭제합니다.  
  
 [PreBindAssemblyEx 함수](../../../../docs/framework/unmanaged-api/fusion/prebindassemblyex-function.md)  
 어셈블리에 대 한 사후 정책 표시 이름을 가져옵니다.  
  
## <a name="related-sections"></a>관련 단원  
 [Fusion 인터페이스](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)  
  
 [Fusion 열거형](../../../../docs/framework/unmanaged-api/fusion/fusion-enumerations.md)  
  
 [Fusion 구조체](../../../../docs/framework/unmanaged-api/fusion/fusion-structures.md)  
  
 [전역 어셈블리 캐시](../../../../docs/framework/app-domains/gac.md)
