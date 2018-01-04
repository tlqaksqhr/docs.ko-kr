---
title: "IMetaDataImport::GetMethodProps 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.GetMethodProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::GetMethodProps
helpviewer_keywords:
- GetMethodProps method [.NET Framework metadata]
- IMetaDataImport::GetMethodProps method [.NET Framework metadata]
ms.assetid: e0667ef7-1d31-4c89-a2d3-d426f023f8d2
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e4e0ae7dfed4b13ea83e16d6380443c9d1b72b06
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportgetmethodprops-method"></a>IMetaDataImport::GetMethodProps 메서드
지정한 MethodDef 토큰이 참조하는 메서드와 연결된 메타데이터를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetMethodProps (  
    [in]  mdMethodDef         mb,  
    [out] mdTypeDef           *pClass,  
    [out] LPWSTR              szMethod,  
    [in]  ULONG               cchMethod,  
    [out] ULONG               *pchMethod,  
    [out] DWORD               *pdwAttr,  
    [out] PCCOR_SIGNATURE     *ppvSigBlob,  
    [out] ULONG               *pcbSigBlob,  
    [out] ULONG               *pulCodeRVA,  
    [out] DWORD               *pdwImplFlags  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `mb`  
 [in] 에 대 한 메타 데이터를 반환할 메서드를 나타내는 MethodDef 토큰입니다.  
  
 `pClass`  
 [out] 메서드를 구현 하는 형식을 나타내는 TypeDef 토큰에 대 한 포인터입니다.  
  
 `szMethod`  
 [out] 메서드의 이름을 포함 하는 버퍼에 대 한 포인터입니다.  
  
 `cchMethod`  
 [in] 요청된 된 크기의 `szMethod`합니다.  
  
 `pchMethod`  
 [out] 와이드 문자에서 크기에 대 한 포인터 `szMethod`, 또는 경우 와이드 문자 메서드 이름에 실제 수입니다.  
  
 `pdwAttr`  
 [out] 메서드와 연결 된 모든 플래그에 대 한 포인터입니다.  
  
 `ppvSigBlob`  
 [out] 이진 메타 데이터 서명 메서드의 포인터입니다.  
  
 `pcbSigBlob`  
 [out] 바이트의 크기에 대 한 포인터 `ppvSigBlob`합니다.  
  
 `pulCodeRVA`  
 [out] 메서드의 상대 가상 주소에 대 한 포인터입니다.  
  
 `pdwImplFlags`  
 [out] 메서드에 대 한 구현 플래그에 대 한 포인터입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** Cor.h  
  
 **라이브러리:** MsCorEE.dll에 리소스로 포함  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [IMetaDataImport 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [IMetaDataImport2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
