---
title: IMetaDataAssemblyEmit::DefineAssembly 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.DefineAssembly
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::DefineAssembly
helpviewer_keywords:
- IMetaDataAssemblyEmit::DefineAssembly method [.NET Framework metadata]
- DefineAssembly method [.NET Framework metadata]
ms.assetid: a0637d66-74bf-4f2d-8137-9ff838bccece
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9115657c52f31d9b7b7da3c843338670343da26c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="imetadataassemblyemitdefineassembly-method"></a>IMetaDataAssemblyEmit::DefineAssembly 메서드
만듭니다는 `Assembly` 지정된 된 어셈블리에 대 한 포함 된 메타 데이터 구조 및 관련된 메타 데이터 토큰을 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT DefineAssembly (  
    [in]  void                 *pbPublicKey,  
    [in]  ULONG                cbPublicKey,  
    [in]  ULONG                uHashAlgId,  
    [in]  LPCWSTR              szName,   
    [in]  ASSEMBLYMETADATA     *pMetaData,  
    [in]  DWORD                dwAssemblyFlags,  
    [out] mdAssembly           *pmda  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pbPublicKey`  
 [in] 어셈블리가 강력 하 게 지정 하지 않은 경우 어셈블리 또는 NULL의 게시자를 식별 하는 공개 키입니다.  
  
 `cbPublicKey`  
 [in] 바이트 크기 `pbPublicKey`합니다.  
  
 `uHashAlgId`  
 [in] Sha-1 알고리즘을 지정 하려면 어셈블리 또는 NULL의 파일을 암호화 하는 데 해시 알고리즘의 식별자입니다.  
  
 `szName`  
 [in] 어셈블리의 이해 하기 쉬운 텍스트 이름입니다. 이 값은 1024 자를 초과할 수 없습니다.  
  
 `pMetaData`  
 [in] 어셈블리에 대 한 버전, 플랫폼 및 로캘 정보를 포함 하는 ASSEMBLYMETADATA 인스턴스에 대 한 포인터입니다.  
  
 `dwAssemblyFlags`  
 [in] 조합을 [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) 은 어셈블리의 기능을 설명 하는 값입니다.  
  
 `pmda`  
 [out] 메타 데이터 토큰에 대 한 포인터입니다.  
  
## <a name="remarks"></a>설명  
 하나의 `Assembly` 매니페스트 메타 데이터 구조를 정의할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** Cor.h  
  
 **라이브러리:** MsCorEE.dll에 리소스로 포함  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [IMetaDataAssemblyEmit 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
