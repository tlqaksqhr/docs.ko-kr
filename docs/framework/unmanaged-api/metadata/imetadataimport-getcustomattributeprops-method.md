---
title: "IMetaDataImport::GetCustomAttributeProps 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.GetCustomAttributeProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::GetCustomAttributeProps
helpviewer_keywords:
- GetCustomAttributeProps method [.NET Framework metadata]
- IMetaDataImport::GetCustomAttributeProps method [.NET Framework metadata]
ms.assetid: 6eefb243-a281-41c1-bcdc-7e17513bc446
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b1e6ef9443b99b3e6b36154558ce226d421dbc0a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportgetcustomattributeprops-method"></a>IMetaDataImport::GetCustomAttributeProps 메서드
해당 메타데이터 토큰이 지정된 경우 사용자 지정 특성의 값을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetCustomAttributeProps (  
   [in]            mdCustomAttribute   cv,  
   [out, optional] mdToken             *ptkObj,  
   [out, optional] mdToken             *ptkType,  
   [out, optional] void const          **ppBlob,  
   [out, optional] ULONG               *pcbSize  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `cv`  
 [in] 검색할 사용자 지정 특성을 나타내는 메타데이터 토큰입니다.  
  
 `ptkObj`  
 [out, optional] 사용자 지정 특성이 수정하는 개체를 나타내는 메타데이터 토큰입니다. 이 값은 `mdCustomAttribute`를 제외한 모든 메타데이터 토큰 형식일 수 있습니다.  
  
 `ptkType`  
 [out, optional] 반환된 사용자 지정 특성의 <xref:System.Type>을 나타내는 `mdMethodDef` 또는 `mdMemberRef` 메타데이터 토큰입니다.  
  
 `ppBlob`  
 [out, optional] 사용자 지정 특성의 값인 데이터 배열에 대한 포인터입니다.  
  
 `pcbSize`  
 [out, optional] *`ppBlob`에 반환된 데이터의 크기(바이트)입니다.  
  
## <a name="remarks"></a>설명  
 사용자 지정 특성은 메타데이터 엔진에서 인식할 수 있는 형식인 데이터 배열로 저장됩니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** Cor.h  
  
 **라이브러리:** MsCorEE.dll에 리소스로 포함  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [IMetaDataImport 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [IMetaDataImport2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
