---
title: "IMetaDataImport2::EnumMethodSpecs 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport2.EnumMethodSpecs
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport2::EnumMethodSpecs
helpviewer_keywords:
- IMetaDataImport2::EnumMethodSpecs method [.NET Framework metadata]
- EnumMethodSpecs method [.NET Framework metadata]
ms.assetid: b3fc1e6c-bcb6-4915-baf8-7dc0a31b8724
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6e134d19eb6699f39e6d538f93f989b87ed8f37d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimport2enummethodspecs-method"></a>IMetaDataImport2::EnumMethodSpecs 메서드
지정한 MethodDef 또는 MemberRef 연관 MethodSpec 토큰 배열의 토큰 열거자를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT EnumMethodSpecs (  
    [in, out] HCORENUM      *phEnum,   
    [in]      mdToken       tk,  
    [out]     mdMethodSpec  rMethodSpecs[],  
    [in]      ULONG         cMax,  
    [out]     ULONG         *pcMethodSpecs  
);   
```  
  
#### <a name="parameters"></a>매개 변수  
 `phEnum`  
 [out에서] 에 대 한 열거자에 대 한 포인터 `rMethodSpecs`합니다.  
  
 `tk`  
 [in] MethodDef 또는 MemberRef 토큰을 열거할 수 있는 MethodSpec 토큰은 메서드를 나타내는입니다. 하는 경우의 값 `tk` 0 (영) 이면 범위에서 모든 MethodSpec 토큰을 열거 합니다.  
  
 `rMethodSpecs`  
 [out] 열거할 MethodSpec 토큰이의 배열입니다.  
  
 `cMax`  
 [in] 요청 된 최대 수에 배치 하는 토큰의 `rMethodSpecs`합니다.  
  
 `pcMethodSpecs`  
 [out] 반환 된 토큰 수에 배치 `rMethodSpecs`합니다.  
  
## <a name="return-value"></a>반환 값  
  
|HRESULT|설명|  
|-------------|-----------------|  
|`S_OK`|`EnumMethodSpecs`성공적으로 반환 합니다.|  
|`S_FALSE`|`phEnum`에 멤버가 요소가 없습니다. 이 경우 `pcMethodSpecs` 0 (영)으로 설정 됩니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** Cor.h  
  
 **라이브러리:** MsCorEE.dll에서 리소스로 사용  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [IMetaDataImport2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)  
 [IMetaDataImport 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
