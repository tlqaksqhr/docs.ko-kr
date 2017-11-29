---
title: "IMetaDataImport::GetCustomAttributeByName 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.GetCustomAttributeByName
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::GetCustomAttributeByName
helpviewer_keywords:
- IMetaDataImport::GetCustomAttributeByName method [.NET Framework metadata]
- GetCustomAttributeByName method [.NET Framework metadata]
ms.assetid: 909aa530-2e3b-4d0a-a38a-a2750e535d7d
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 5b689c54b5e8d741d32bc941b4e78e6674f15e01
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportgetcustomattributebyname-method"></a>IMetaDataImport::GetCustomAttributeByName 메서드
지정 된 이름 및 소유자 사용자 지정 특성을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetCustomAttributeByName (  
   [in]  mdToken          tkObj,  
   [in]  LPCWSTR          szName,  
   [out] const void       **ppData,  
   [out] ULONG            *pcbData  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `tkObj`  
 [in] 사용자 지정 특성을 소유 하 고 개체를 나타내는 메타 데이터 토큰입니다.  
  
 `szName`  
 [in] 사용자 지정 특성의 이름입니다.  
  
 `ppData`  
 [out] 사용자 지정 특성의 값인 데이터 배열에 대 한 포인터입니다.  
  
 `pcbData`  
 [out] 반환 되는 데이터의 바이트 크기 *`ppData`합니다.  
  
## <a name="remarks"></a>설명  
 같은 소유자;에 대 한 여러 사용자 지정 특성을 정의할 수 동일한 이름을 가지도 될 수 있습니다. 그러나 `GetCustomAttributeByName` 하나의 인스턴스를 반환 합니다. (`GetCustomAttributeByName` 발견 되는 첫 번째 인스턴스를 반환 합니다.) 사용자 지정 특성의 모든 인스턴스를 찾으려면 호출는 [imetadataimport:: Enumcustomattributes](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumcustomattributes-method.md) 메서드.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** Cor.h  
  
 **라이브러리:** MsCorEE.dll에 리소스로 포함  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [IMetaDataImport 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [IMetaDataImport2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
