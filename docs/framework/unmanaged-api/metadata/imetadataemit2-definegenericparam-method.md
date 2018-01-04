---
title: "IMetaDataEmit2::DefineGenericParam 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit2.DefineGenericParam
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit2::DefineGenericParam
helpviewer_keywords:
- IMetaDataEmit2::DefineGenericParam method [.NET Framework metadata]
- DefineGenericParam method [.NET Framework metadata]
ms.assetid: 47b2a3b6-907d-43dc-858d-1ae7dca1316a
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 598c616ca91b73d9cb184d9e431e75d00d3f9850
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemit2definegenericparam-method"></a>IMetaDataEmit2::DefineGenericParam 메서드
제네릭 형식 매개 변수에 대 한 정의 만들고 해당 제네릭 형식 매개 변수에 대 한 토큰을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT DefineGenericParam (   
    [in]  mdToken         tk,   
    [in]  ULONG           ulParamSeq,   
    [in]  DWORD           dwParamFlags,   
    [in]  LPCWSTR         szname,   
    [in]  DWORD           reserved,   
    [in]  mdToken         rtkConstraints[],   
    [out] mdGenericParam  *pgp  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `tk`  
 [in] `mdTypeDef` 또는 `mdMethodDef` 메서드 또는 제네릭 매개 변수를 정의 하는 생성자를 나타내는 토큰입니다.  
  
 `ulParamSeq`  
 [in] 제네릭 매개 변수의 인덱스입니다.  
  
 `dwParamFlags`  
 [in] 값은 [CorGenericParamAttr](../../../../docs/framework/unmanaged-api/metadata/corgenericparamattr-enumeration.md) 제네릭 매개 변수 형식을 설명 하는 열거형입니다.  
  
 `szname`  
 [in] 매개 변수의 이름입니다.  
  
 `reserved`  
 [in] 이 매개 변수는 다음 버전의 확장에 대 한 예약 되어 있습니다.  
  
 `rtkConstraints`  
 [in] 형식 제약 조건과 0으로 끝나는 배열입니다. 배열 멤버 이어야 합니다는 `mdTypeDef`, `mdTypeRef`, 또는 `mdTypeSpec` 메타 데이터 토큰입니다.  
  
 `pgp`  
 [out] 제네릭 매개 변수를 나타내는 토큰입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** Cor.h  
  
 **라이브러리:** MsCorEE.dll에서 리소스로 사용  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [IMetaDataEmit2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)  
 [IMetaDataEmit 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
