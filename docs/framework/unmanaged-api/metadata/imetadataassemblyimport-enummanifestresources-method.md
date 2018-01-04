---
title: "IMetaDataAssemblyImport::EnumManifestResources 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataAssemblyImport.EnumManifestResources
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataAssemblyImport::EnumManifestResources
helpviewer_keywords:
- IMetaDataAssemblyImport::EnumManifestResources method [.NET Framework metadata]
- EnumManifestResources method [.NET Framework metadata]
ms.assetid: 9543b111-5705-40c9-935c-a3ffc7a581aa
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: fa31441d060744bb17fc26a61daa7e655aa378fd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataassemblyimportenummanifestresources-method"></a>IMetaDataAssemblyImport::EnumManifestResources 메서드
현재 어셈블리 매니페스트에서 참조 하는 리소스에 대 한 열거자에 대 한 포인터를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT EnumManifestResources (  
    [in, out] HCORENUM         *phEnum,   
    [out] mdManifestResource   rManifestResources[],   
    [in]  ULONG                cMax,   
    [out] ULONG                *pcTokens  
);   
```  
  
#### <a name="parameters"></a>매개 변수  
 `phEnum`  
 [out에서] 열거자에 대 한 포인터입니다. null 이어야 합니다 경우이 값은 `EnumManifestResources` 메서드를 처음으로 호출 됩니다.  
  
 `rManifestResources`  
 [out] 저장 하는 데 사용 되는 배열에서 `mdManifestResource` 메타 데이터 토큰입니다.  
  
 `cMax`  
 [in] 최대 `mdManifestResource` 에 배치할 수 있는 토큰 `rManifestResources`합니다.  
  
 `pcTokens`  
 [out] 수가 `mdManifestResource` 토큰에 실제로 배치 `rManifestResources`합니다.  
  
## <a name="return-value"></a>반환 값  
  
|HRESULT|설명|  
|-------------|-----------------|  
|`S_OK`|`EnumManifestResources`성공적으로 반환 합니다.|  
|`S_FALSE`|열거할 토큰이 있습니다. 이 경우 `pcTokens` 0으로 설정 됩니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** Cor.h  
  
 **라이브러리:** MsCorEE.dll에서 리소스로 사용  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [IMetaDataAssemblyImport 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
