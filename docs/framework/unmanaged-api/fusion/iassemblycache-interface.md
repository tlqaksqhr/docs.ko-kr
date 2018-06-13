---
title: IAssemblyCache 인터페이스
ms.date: 03/30/2017
api_name:
- IAssemblyCache
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyCache
helpviewer_keywords:
- IAssemblyCache interface [.NET Framework fusion]
ms.assetid: 71ea170f-872d-4fc5-81b6-27da1dec9b19
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4302a73f9f077c2e1bf4f66c2b80ab025ae4a62c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33430585"
---
# <a name="iassemblycache-interface"></a>IAssemblyCache 인터페이스
Fusion 기술에서 사용 하기 위해 전역 어셈블리 캐시를 나타냅니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[CreateAssemblyCacheItem 메서드](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-createassemblycacheitem-method.md)|새에 대 한 참조 [IAssemblyCacheItem](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md)합니다.|  
|[CreateAssemblyScavenger 메서드](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-createassemblyscavenger-method.md)|Fusion 기술에서 내부 사용을 위해 예약 되어 있습니다.|  
|[InstallAssembly 메서드](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-installassembly-method.md)|전역 어셈블리 캐시에 지정된 된 어셈블리를 설치합니다.|  
|[QueryAssemblyInfo 메서드](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-queryassemblyinfo-method.md)|지정된 된 어셈블리에 대 한 요청 된 데이터를 가져옵니다.|  
|[UninstallAssembly 메서드](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-uninstallassembly-method.md)|지정된 된 어셈블리를 전역 어셈블리 캐시에서 제거합니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** Fusion.h  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [Fusion 인터페이스](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)  
 [전역 어셈블리 캐시](../../../../docs/framework/app-domains/gac.md)
