---
title: "IMetaDataImport::EnumSignatures 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.EnumSignatures
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::EnumSignatures
helpviewer_keywords:
- EnumSignatures method [.NET Framework metadata]
- IMetaDataImport::EnumSignatures method [.NET Framework metadata]
ms.assetid: d0d65060-6f90-42a2-95cf-6ffb04352996
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 88d47e2512103947f007c81450157a0b3e334a33
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportenumsignatures-method"></a>IMetaDataImport::EnumSignatures 메서드
현재 범위의 독립 실행형 서명을 나타내는 Signature 토큰을 열거합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT EnumSignatures (  
   [in, out] HCORENUM     *phEnum,  
   [out]     mdSignature  rSignatures[],  
   [in]      ULONG        cMax,  
   [out]     ULONG        *pcSignatures  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `phEnum`  
 [out에서] 열거자에 대 한 포인터입니다. 이 메서드의 첫 번째 호출에 대 한 NULL 이어야 합니다.  
  
 `rSignatures`  
 [out] 서명 토큰을 저장 하는 데 사용 되는 배열입니다.  
  
 `cMax`  
 [in] `rSignatures` 배열의 최대 크기입니다.  
  
 `pcSignatures`  
 [out] 반환 된 서명 토큰 수 `rSignatures`합니다.  
  
## <a name="return-value"></a>반환 값  
  
|HRESULT|설명|  
|-------------|-----------------|  
|`S_OK`|`EnumSignatures`성공적으로 반환 합니다.|  
|`S_FALSE`|열거할 토큰이 있습니다. 이 경우 `pcSignatures` 은 0입니다.|  
  
## <a name="remarks"></a>설명  
 서명 토큰에 의해 만들어집니다는 [imetadataemit:: Gettokenfromsig](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromsig-method.md) 메서드.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** Cor.h  
  
 **라이브러리:** MsCorEE.dll에 리소스로 포함  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [IMetaDataImport 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [IMetaDataImport2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
