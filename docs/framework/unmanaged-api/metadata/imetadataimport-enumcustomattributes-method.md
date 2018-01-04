---
title: "IMetaDataImport::EnumCustomAttributes 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.EnumCustomAttributes
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::EnumCustomAttributes
helpviewer_keywords:
- EnumCustomAttributes method [.NET Framework metadata]
- IMetaDataImport::EnumCustomAttributes method [.NET Framework metadata]
ms.assetid: 798513a0-68b1-4d04-bc5b-782a4445ea68
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4e45c15f3d09972d1c83c9b330965c4e8afd21b7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportenumcustomattributes-method"></a>IMetaDataImport::EnumCustomAttributes 메서드
지정 된 형식 또는 멤버와 연결 된 사용자 지정 특성 정의 토큰을 열거 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT EnumCustomAttributes (   
   [in, out] HCORENUM      *phEnum,  
   [in]  mdToken            tk,   
   [in]  mdToken            tkType,   
   [out] mdCustomAttribute  rCustomAttributes[],   
   [in]  ULONG              cMax,  
   [out, optional] ULONG   *pcCustomAttributes  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `phEnum`  
 [out에서] 반환 된 열거자에 대 한 포인터입니다.  
  
 `tk`  
 [in] 열거형 또는 모든 사용자 지정 특성에 대 한 0의 범위에 대 한 토큰입니다.  
  
 `tkType`  
 [in] 특성을 열거할 수의 형식의 생성자에 대 한 토큰 또는 `null` 모든 형식에 대 한 합니다.  
  
 `rCustomAttributes`  
 [out] 사용자 지정 특성 토큰의 배열입니다.  
  
 `cMax`  
 [in] `rCustomAttributes` 배열의 최대 크기입니다.  
  
 `pcCustomAttributes`  
 [out, optional] 반환 된 토큰 값의 실제 수 `rCustomAttributes`합니다.  
  
## <a name="return-value"></a>반환 값  
  
|HRESULT|설명|  
|-------------|-----------------|  
|`S_OK`|`EnumCustomAttributes`성공적으로 반환 합니다.|  
|`S_FALSE`|열거를 사용자 지정 특성이 없는 합니다. 이 경우 `pcCustomAttributes` 은 0입니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** Cor.h  
  
 **라이브러리:** MsCorEE.dll에 리소스로 포함  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [IMetaDataImport 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [IMetaDataImport2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
