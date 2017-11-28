---
title: "IMetaDataEmit::SetFieldMarshal 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.SetFieldMarshal
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::SetFieldMarshal
helpviewer_keywords:
- SetFieldMarshal method [.NET Framework metadata]
- IMetaDataEmit::SetFieldMarshal method [.NET Framework metadata]
ms.assetid: be232314-7f69-4855-bfab-63361bd22307
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 3ef1d50d0d74a92a5bcaf23981226e5a6c852edd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemitsetfieldmarshal-method"></a>IMetaDataEmit::SetFieldMarshal 메서드
지정한 토큰이 참조 하는 필드, return, 메서드 또는 메서드 매개 변수의 대 한 마샬링 정보 PInvoke를 설정 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT SetFieldMarshal (  
    [in]  mdToken          tk,   
    [in]  PCCOR_SIGNATURE  pvNativeType,   
    [in]  ULONG            cbNativeType   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `tk`  
 [in] 대상 데이터 항목에 대 한 토큰입니다. 이 역할은 한 `mdFieldDef` 또는 `mdParamDef` 토큰입니다.  
  
 `pvNativeType`  
 [in] 관리 되지 않는 형식에 대 한 서명입니다.  
  
 `cbNativeType`  
 [in] 바이트 수 `pvNativeType`합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** Cor.h  
  
 **라이브러리:** MSCorEE.dll에서 리소스로 사용  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [IMetaDataEmit 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [IMetaDataEmit2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
