---
title: IMetaDataImport::EnumInterfaceImpls 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumInterfaceImpls
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumInterfaceImpls
helpviewer_keywords:
- IMetaDataImport::EnumInterfaceImpls method [.NET Framework metadata]
- EnumInterfaceImpls method [.NET Framework metadata]
ms.assetid: ba6e178f-128b-4e47-a13c-b4be73eb106c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 824337a8a87282e59c9fc5df18c71800339e8d7b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33447463"
---
# <a name="imetadataimportenuminterfaceimpls-method"></a>IMetaDataImport::EnumInterfaceImpls 메서드
인터페이스 구현을 나타내는 MethodDef 토큰을 열거합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT EnumInterfaceImpls (  
   [in, out]  HCORENUM       *phEnum,   
   [in]   mdTypeDef          td,  
   [out]  mdInterfaceImpl    rImpls[],   
   [in]   ULONG              cMax,  
   [out]  ULONG*             pcImpls  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `phEnum`  
 [out에서] 열거자에 대 한 포인터입니다.  
  
 `td`  
 [in] 인터페이스 구현을 나타내는 MethodDef 토큰 인을 열거할 수는 TypeDef의 토큰입니다.  
  
 `rImpls`  
 [out] MethodDef 토큰을 저장 하는 데 사용 되는 배열입니다.  
  
 `cMax`  
 [in] `rImpls` 배열의 최대 크기입니다.  
  
 `pcImpls`  
 [out] 반환 된 토큰의 실제 수 `rImpls`합니다.  
  
## <a name="return-value"></a>반환 값  
  
|HRESULT|설명|  
|-------------|-----------------|  
|`S_OK`|`EnumInterfaceImpls` 성공적으로 반환 합니다.|  
|`S_FALSE`|열거할 MethodDef 토큰이 있습니다. 이 경우 `pcImpls` 0으로 설정 됩니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** Cor.h  
  
 **라이브러리:** MsCorEE.dll에 리소스로 포함  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [IMetaDataImport 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [IMetaDataImport2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
