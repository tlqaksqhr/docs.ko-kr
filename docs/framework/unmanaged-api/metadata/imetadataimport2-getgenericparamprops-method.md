---
title: "IMetaDataImport2::GetGenericParamProps 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport2.GetGenericParamProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport2::GetGenericParamProps
helpviewer_keywords:
- IMetaDataImport2::GetGenericParamProps method [.NET Framework metadata]
- GetGenericParamProps method [.NET Framework metadata]
ms.assetid: dbb21e67-712b-49e7-a27c-a1e73ffd46c5
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: af6ab8fd6e941f5219c1aad2946479dda0b64264
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimport2getgenericparamprops-method"></a>IMetaDataImport2::GetGenericParamProps 메서드
지정한 토큰이 나타내는 제네릭 매개 변수와 연관 된 메타 데이터를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetGenericParamProps (  
   [in]  mdGenericParam  gp,  
   [out] ULONG           *pulParamSeq,  
   [out] DWORD           *pdwParamFlags,  
   [out] mdToken         *ptOwner,  
   [out] DWORD           *reserved,  
   [out] LPWSTR          wzName,  
   [in]  ULONG           cchName,  
   [out] ULONG           *pchName  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `gp`  
 [in] 반환할 메타 데이터에 대 한 제네릭 매개 변수를 나타내는 토큰입니다.  
  
 `pulParamSeq`  
 [out] 서 수 위치는 `Type` 부모 생성자 또는 메서드 매개 변수입니다.  
  
 `pdwParamFlags`  
 [out] 값은 [CorGenericParamAttr](../../../../docs/framework/unmanaged-api/metadata/corgenericparamattr-enumeration.md) 설명 하는 열거형의 `Type` 제네릭 매개 변수입니다.  
  
 `ptOwner`  
 [out] 형식 정의 또는 MethodDef 토큰 매개 변수의 소유자를 나타내는입니다.  
  
 `reserved`  
 [out] 다음 버전의 확장에 대 한 예약 되어 있습니다.  
  
 `wzName`  
 [out] 제네릭 매개 변수의 이름입니다.  
  
 `cchName`  
 [in] 크기는 `wzName` 버퍼입니다.  
  
 `pchName`  
 [out] 와이드 문자에서는 이름의 반환 된 크기입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** Cor.h  
  
 **라이브러리:** MsCorEE.dll에서 리소스로 사용  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [IMetaDataImport2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)  
 [IMetaDataImport 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
