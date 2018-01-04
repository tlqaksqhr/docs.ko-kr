---
title: "IMetaDataAssemblyEmit::SetAssemblyRefProps 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataAssemblyEmit.SetAssemblyRefProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataAssemblyEmit::SetAssemblyRefProps
helpviewer_keywords:
- SetAssemblyRefProps method [.NET Framework metadata]
- IMetaDataAssemblyEmit::SetAssemblyRefProps method [.NET Framework metadata]
ms.assetid: 70a32bf3-9051-4f96-ae87-11356d06a073
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 446137d28fdd64d7f9e5c84cc57e9ec967982430
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataassemblyemitsetassemblyrefprops-method"></a>IMetaDataAssemblyEmit::SetAssemblyRefProps 메서드
지정된 `AssemblyRef` 메타데이터 구조를 수정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT SetAssemblyRefProps (  
    [in] mdAssemblyRef              ar,  
    [in] const void                 *pbPublicKeyOrToken,  
    [in] ULONG                      cbPublicKeyOrToken,  
    [in] LPCWSTR                    szName,   
    [in] const ASSEMBLYMETADATA     *pMetaData,   
    [in] const void                 *pbHashValue,  
    [in] ULONG                      cbHashValue,  
    [in] DWORD                      dwAssemblyRefFlags  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `ar`  
 [in] 메타 데이터 토큰을 지정 하는 `AssemblyRef` 메타 데이터 구조를 수정할 수 있습니다.  
  
 `pbPublicKeyOrToken`  
 [in] 참조 된 어셈블리의 게시자의 공개 키입니다.  
  
 `cbPublicKeyOrToken`  
 [in] 바이트 크기 `pbPublicKeyOrToken`합니다.  
  
 `szName`  
 [in] 어셈블리의 이해 하기 쉬운 텍스트 이름입니다.  
  
 `pMetaData`  
 [in] 어셈블리에 대 한 버전, 플랫폼 및 로캘 정보를 포함 하는 ASSEMBLYMETADATA 인스턴스에 대 한 포인터입니다.  
  
 `pbHashValue`  
 [in] 어셈블리와 연결 된 데이터 해시에 대 한 포인터입니다.  
  
 `cbHashValue`  
 [in] 바이트 크기 `pbHashValue`합니다.  
  
 `dwAssemblyRefFlags`  
 [in] 비트 조합 [AssemblyRefFlags](../../../../docs/framework/unmanaged-api/metadata/assemblyrefflags-enumeration.md) 참조 된 어셈블리의 특성을 지정 하는 값입니다.  
  
## <a name="remarks"></a>설명  
 만들려는 `AssemblyRef` 메타 데이터 구조를 사용 하 여는 [imetadataassemblyemit:: Defineassemblyref](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md) 메서드.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** Cor.h  
  
 **라이브러리:** MsCorEE.dll에서 리소스로 사용  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [IMetaDataAssemblyEmit 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
