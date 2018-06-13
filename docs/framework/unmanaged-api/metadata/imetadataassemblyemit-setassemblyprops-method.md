---
title: IMetaDataAssemblyEmit::SetAssemblyProps 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.SetAssemblyProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::SetAssemblyProps
helpviewer_keywords:
- SetAssemblyProps method [.NET Framework metadata]
- IMetaDataAssemblyEmit::SetAssemblyProps method [.NET Framework metadata]
ms.assetid: 91b633d7-9e75-43c3-a8d2-2144984e5f9e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6f8132296035e9ddcdcad76d93ed05358beb0b81
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33448235"
---
# <a name="imetadataassemblyemitsetassemblyprops-method"></a>IMetaDataAssemblyEmit::SetAssemblyProps 메서드
지정된 `Assembly` 메타데이터 구조를 수정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT SetAssemblyProps (  
    [in] mdAssembly               pma,  
    [in] const void               *pbPublicKey,  
    [in] ULONG                    cbPublicKey,  
    [in] ULONG                    ulHashAlgId,  
    [in] LPCWSTR                  szName,  
    [in] const ASSEMBLYMETADATA   *pMetaData,  
    [in] DWORD                    dwAssemblyFlags  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pma`  
 [in] 메타 데이터 토큰을 지정 하는 `Assembly` 메타 데이터 구조를 수정할 수 있습니다.  
  
 `pbPublicKey`  
 [in] 어셈블리의 게시자의 공개 키에 대 한 포인터입니다.  
  
 `cbPublicKey`  
 [in] 바이트 크기 `pbPublicKey`합니다.  
  
 `ulHashAlgId`  
 [in] 어셈블리 파일을 해시 하는 데 사용 되는 해시 알고리즘에 대 한 식별자입니다.  
  
 `szName`  
 [in] 어셈블리의 이해 하기 쉬운 텍스트 이름입니다.  
  
 `pMetaData`  
 [in] 포인터 ASSEMBLYMETADATA 어셈블리에 대 한 버전, 플랫폼 및 로캘 정보를 포함 하는입니다.  
  
 `dwAssemblyFlags`  
 [in] 비트 조합 [AssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/assemblyflags-enumeration.md) 어셈블리의 다양 한 특성을 지정 하는 값입니다.  
  
## <a name="remarks"></a>설명  
 만들려는 `Assembly` 메타 데이터 구조를 사용 하 여는 [imetadataassemblyemit:: Defineassembly](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassembly-method.md) 메서드.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** Cor.h  
  
 **라이브러리:** MsCorEE.dll에서 리소스로 사용  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [IMetaDataAssemblyEmit 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
