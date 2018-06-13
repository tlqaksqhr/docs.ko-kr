---
title: IMetaDataImport::FindTypeDefByName 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.FindTypeDefByName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::FindTypeDefByName
helpviewer_keywords:
- FindTypeDefByName method [.NET Framework metadata]
- IMetaDataImport::FindTypeDefByName method [.NET Framework metadata]
ms.assetid: f4c2cd88-ac28-4bad-9ab1-2cf9d2de41e6
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2b4aad1cf1d3eb2dec249686f2897e6f393ab7e7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33445480"
---
# <a name="imetadataimportfindtypedefbyname-method"></a>IMetaDataImport::FindTypeDefByName 메서드
에 대 한 토큰 TypeDef 메타 데이터에 대 한 포인터를 가져옵니다는 <xref:System.Type> 지정 된 이름입니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT FindTypeDefByName  
   [in]  LPCWSTR       szTypeDef,  
   [in]  mdToken       tkEnclosingClass,  
   [out] mdTypeDef     *ptd  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `szTypeDef`  
 [in] TypeDef 토큰을 가져올 형식의 이름입니다.  
  
 `tkEnclosingClass`  
 [in] 바깥쪽 클래스를 나타내는 TypeDef 또는 TypeRef 토큰입니다. 중첩 된 클래스 형식을 찾을 수 없는 경우이 값을 NULL로 설정 합니다.  
  
 `ptd`  
 [out] 일치 하는 TypeDef 토큰에 대 한 포인터입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** Cor.h  
  
 **라이브러리:** MsCorEE.dll에 리소스로 포함  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [IMetaDataImport 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [IMetaDataImport2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
