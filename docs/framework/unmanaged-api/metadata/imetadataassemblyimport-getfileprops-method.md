---
title: "IMetaDataAssemblyImport::GetFileProps 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataAssemblyImport.GetFileProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataAssemblyImport::GetFileProps
helpviewer_keywords:
- GetFileProps method [.NET Framework metadata]
- IMetaDataAssemblyImport::GetFileProps method [.NET Framework metadata]
ms.assetid: c5e6216f-ae3d-4697-9688-66b69c1251ec
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c4ca64d4781f0cc228c0af7f2ae772098d2f164a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="imetadataassemblyimportgetfileprops-method"></a>IMetaDataAssemblyImport::GetFileProps 메서드
지정한 메타 데이터 서명 사용 하 여 파일의 속성을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetFileProps (  
    [in]  mdFile      mdf,   
    [out] LPWSTR      szName,   
    [in]  ULONG       cchName,   
    [out] ULONG       *pchName,   
    [out] const void  **ppbHashValue,   
    [out] ULONG       *pcbHashValue,   
    [out] DWORD       *pdwFileFlags  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `mdf`  
 [in] `mdFile` 파일을 가져올 속성을 나타내는 메타 데이터 토큰입니다.  
  
 `szName`  
 [out] 파일의 단순한 이름입니다.  
  
 `cchName`  
 [in] 와이드 문자에서 크기의 `szName`합니다.  
  
 `pchName`  
 [out] 와이드 문자에 실제로 반환 된 수가 `szName`합니다.  
  
 `ppbHashValue`  
 [out] 해시 값에 대 한 포인터입니다. 파일의 sha-1 알고리즘을 사용 하는 해시입니다.  
  
 `pcbHashValue`  
 [out] 반환 된 해시 값의 와이드 문자 수를 지정 합니다.  
  
 `pdwFileFlags`  
 [out] 파일에 적용 하는 메타 데이터를 설명 하는 플래그에 대 한 포인터입니다. 플래그 값은 하나 이상의 조합 [CorFileFlags](../../../../docs/framework/unmanaged-api/metadata/corfileflags-enumeration.md) 값입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** Cor.h  
  
 **라이브러리:** MsCorEE.dll에서 리소스로 사용  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [IMetaDataAssemblyImport 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
