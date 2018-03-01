---
title: "IMetaDataImport::ResolveTypeRef 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IMetaDataImport.ResolveTypeRef
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::ResolveTypeRef
helpviewer_keywords:
- ResolveTypeRef method [.NET Framework metadata]
- IMetaDataImport::ResolveTypeRef method [.NET Framework metadata]
ms.assetid: 556bccfb-61bc-4761-b1d5-de4b1c18a38f
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 64a783297b27c9d1400670eecb7dfe4cb69c2b96
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportresolvetyperef-method"></a>IMetaDataImport::ResolveTypeRef 메서드
확인 되는 <xref:System.Type> 지정한 TypeRef 토큰이 나타내는 참조 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT ResolveTypeRef (  
   [in]  mdTypeRef       tr,  
   [in]  REFIID          riid,  
   [out] IUnknown        **ppIScope,  
   [out] mdTypeDef       *ptd  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `tr`  
 [in] 에 대 한 참조 된 형식 정보를 반환 하는 TypeRef 메타 데이터 토큰입니다.  
  
 `riid`  
 [in] 반환 하는 인터페이스의 IID `ppIScope`합니다. 일반적으로 IID_IMetaDataImport가 됩니다.  
  
 `ppIScope`  
 [out] 모듈 범위는 참조 된 유형이 정의 되어 있는 한 인터페이스입니다.  
  
 `ptd`  
 [out] 참조 된 형식을 나타내는 TypeDef 토큰에 대 한 포인터입니다.  
  
## <a name="remarks"></a>설명  
  
> [!IMPORTANT]
>  여러 응용 프로그램 도메인이 로드 된 경우에이 메서드를 사용 하지 마십시오. 메서드는 응용 프로그램 도메인 경계를 반영 하지 않습니다. 여러 버전의 어셈블리가 로드 되 면 같은 네임 스페이스와 동일한 형식을 포함 하는 경우 메서드는 찾은 첫 번째 유형은 모듈 범위를 반환 합니다.  
  
 `ResolveTypeRef` 다른 모듈에 있는 형식 정의 대 한 메서드를 검색 합니다. 형식 정의 있으면 `ResolveTypeRef` 유형에 대 한 TypeDef 토큰 뿐만 아니라 해당 모듈 범위에 대 한 인터페이스를 반환 합니다.  
  
 형식 참조를 확인할 수를 확인 범위가 AssemblyRef를 이면는 `ResolveTypeRef` 에 대 한 호출을 사용 하 여 이미 열려 있는 메타 데이터 범위에만 일치 항목을 검색 하는 메서드는 [imetadatadispenser:: Openscope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md)메서드 또는 [imetadatadispenser:: Openscopeonmemory](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md) 메서드. 때문에 이것이 `ResolveTypeRef` 만 디스크에 또는 전역 어셈블리 캐시에 어셈블리 저장 된 위치의 AssemblyRef 범위에서 확인할 수 없습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** Cor.h  
  
 **라이브러리:** MsCorEE.dll에 리소스로 포함  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [IMetaDataImport 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [IMetaDataImport2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
