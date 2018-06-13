---
title: IMetaDataImport::EnumTypeDefs 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumTypeDefs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumTypeDefs
helpviewer_keywords:
- EnumTypeDefs method [.NET Framework metadata]
- IMetaDataImport::EnumTypeDefs method [.NET Framework metadata]
ms.assetid: 4e508711-da92-4381-aaf8-6803075cdaa2
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 53ed486a885514d02bf2be9c473e102c2c5f0e15
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33446845"
---
# <a name="imetadataimportenumtypedefs-method"></a>IMetaDataImport::EnumTypeDefs 메서드
현재 범위 내의 모든 형식을 나타내는 TypeDef 토큰을 열거합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT EnumTypeDefs (  
   [out] HCORENUM   *phEnum,   
   [in]  mdTypeDef  rTypeDefs[],  
   [in]  ULONG      cMax,   
   [out] ULONG      *pcTypeDefs  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `phEnum`  
 [out] 새 열거자에 대 한 포인터입니다. 이 메서드의 첫 번째 호출에 대 한 NULL 이어야 합니다.  
  
 `rTypeDefs`  
 [in] TypeDef 토큰을 저장 하는 데 사용 되는 배열입니다.  
  
 `cMax`  
 [in] `rTypeDefs` 배열의 최대 크기입니다.  
  
 `pcTypeDefs`  
 [out] 반환 하는 TypeDef 토큰 수 `rTypeDefs`합니다.  
  
## <a name="return-value"></a>반환 값  
  
|HRESULT|설명|  
|-------------|-----------------|  
|`S_OK`|`EnumTypeDefs` 성공적으로 반환 합니다.|  
|`S_FALSE`|열거할 토큰이 있습니다. 이 경우 `pcTypeDefs` 은 0입니다.|  
  
## <a name="remarks"></a>설명  
 TypeDef 토큰에는 같은 클래스 또는 인터페이스 형식 뿐만 아니라 확장성 메커니즘을 통해 추가 된 모든 형식을 나타냅니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** Cor.h  
  
 **라이브러리:** MsCorEE.dll에 리소스로 포함  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [IMetaDataImport 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [IMetaDataImport2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
