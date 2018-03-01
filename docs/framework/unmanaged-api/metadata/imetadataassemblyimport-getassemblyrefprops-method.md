---
title: "IMetaDataAssemblyImport::GetAssemblyRefProps 메서드"
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
- IMetaDataAssemblyImport.GetAssemblyRefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::GetAssemblyRefProps
helpviewer_keywords:
- IMetaDataAssemblyImport::GetAssemblyRefProps method [.NET Framework metadata]
- GetAssemblyRefProps method [.NET Framework metadata]
ms.assetid: 5c6b7fb4-cbca-4479-b650-ab9a99732ea0
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 76ae1d81db314530ab33a42cb99824da1745dff0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataassemblyimportgetassemblyrefprops-method"></a>IMetaDataAssemblyImport::GetAssemblyRefProps 메서드
지정 된 메타 데이터 서명 가진 어셈블리 참조에 대 한 속성의 집합을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetAssemblyRefProps (  
    [in]  mdAssemblyRef        mdar,   
    [out] const void          **ppbPublicKeyOrToken,   
    [out] ULONG                *pcbPublicKeyOrToken,   
    [out] LPWSTR               szName,   
    [in]  ULONG                cchName,   
    [out] ULONG                *pchName,   
    [out] ASSEMBLYMETADATA     *pMetaData,   
    [out] const void           **ppbHashValue,   
    [out] ULONG                *pcbHashValue,   
    [out] DWORD                *pdwAssemblyRefFlags  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `mdar`  
 [in] `mdAssemblyRef` 메타 데이터 토큰을 가져올 속성에 대 한 어셈블리 참조를 나타내는입니다.  
  
 `ppbPublicKeyOrToken`  
 [out] 공개 키 또는 메타 데이터 토큰에 대 한 포인터입니다.  
  
 `pcbPublicKeyOrToken`  
 [out] 반환 된 공개 키 또는 토큰의 바이트 수입니다.  
  
 `szName`  
 [out] 어셈블리의 단순한 이름입니다.  
  
 `cchName`  
 [in] 와이드 문자에서 크기의 `szName`합니다.  
  
 `pchName`  
 [out] 와이드 문자에 실제로 반환 된 수에 대 한 포인터 `szName`합니다.  
  
 `pMetaData`  
 [out] 어셈블리 메타 데이터가 포함 된 ASSEMBLYMETADATA 구조체에 대 한 포인터입니다.  
  
 `ppbHashValue`  
 [out] 해시 값에 대 한 포인터입니다. 이것이의 sha-1 알고리즘을 사용 하 여 해시는 `PublicKey` 는 arfFullOriginator의 플래그를 지정 하지 않으면 참조 되는 어셈블리의 속성은 [AssemblyRefFlags](../../../../docs/framework/unmanaged-api/metadata/assemblyrefflags-enumeration.md) 열거형 설정 됩니다.  
  
 `pcbHashValue`  
 [out] 반환 된 해시 값의 와이드 문자 수를 지정 합니다.  
  
 `pdwAssemblyRefFlags`  
 [out] 어셈블리에 적용할 메타 데이터를 설명 하는 플래그에 대 한 포인터입니다. 플래그 값은 하나 이상의 조합 [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) 값입니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드가 반환; 성공 하면 s_ok이 고 그렇지 않은 경우 Winerror.h 헤더 파일에 정의 된 오류 코드 중 하나 반환 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** Cor.h  
  
 **라이브러리:** MsCorEE.dll에서 리소스로 사용  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [IMetaDataAssemblyImport 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
