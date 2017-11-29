---
title: "IMetaDataAssemblyImport::GetManifestResourceProps 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataAssemblyImport.GetManifestResourceProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataAssemblyImport::GetManifestResourceProps
helpviewer_keywords:
- GetManifestResourceProps method [.NET Framework metadata]
- IMetaDataAssemblyImport::GetManifestResourceProps method [.NET Framework metadata]
ms.assetid: 00be4789-ac63-4397-b2ec-1629a5c5a585
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 29458b0b7afa5a0c0be908915b4fc91c85d28c72
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="imetadataassemblyimportgetmanifestresourceprops-method"></a>IMetaDataAssemblyImport::GetManifestResourceProps 메서드
지정 된 메타 데이터 서명 가진 매니페스트 리소스의 속성 집합을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetManifestResourceProps (  
    [in]  mdManifestResource   mdmr,   
    [out] LPWSTR               szName,   
    [in]  ULONG                cchName,   
    [out] ULONG                *pchName,   
    [out] mdToken              *ptkImplementation,   
    [out] DWORD                *pdwOffset,   
    [out] DWORD                *pdwResourceFlags  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `mdmr`  
 [in] `mdManifestResource` 토큰을 가져올 속성에 대 한 리소스를 나타내는입니다.  
  
 `szName`  
 [out] 리소스의 이름입니다.  
  
 `cchName`  
 [in] 와이드 문자에서 크기의 `szName`합니다.  
  
 `pchName`  
 [out] 와이드 문자에 실제로 반환 된 수에 대 한 포인터 `szName`합니다.  
  
 `ptkImplementation`  
 [out] 에 대 한 포인터는 `mdFile` 토큰 또는 `mdAssemblyRef` 리소스가 포함 된 파일 또는 어셈블리를 각각 나타내는 토큰입니다.  
  
 `pdwOffset`  
 [out] 파일 내에서 리소스의 시작 부분에 대 한 오프셋을 지정 하는 값에 대 한 포인터입니다.  
  
 `pdwResourceFlags`  
 [out] 리소스에 적용 되는 메타 데이터를 설명 하는 플래그에 대 한 포인터입니다. 플래그 값은 하나 이상의 조합 [CorManifestResourceFlags](../../../../docs/framework/unmanaged-api/metadata/cormanifestresourceflags-enumeration.md) 값입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** Cor.h  
  
 **라이브러리:** MsCorEE.dll에서 리소스로 사용  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [IMetaDataAssemblyImport 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
