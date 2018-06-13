---
title: AddFile2 메서드
ms.date: 03/30/2017
api_name:
- AddFile2
- IALink2.AddFile2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- AddFile2
helpviewer_keywords:
- AddFile2 method
ms.assetid: 03bc49bf-a89b-4fb6-a88d-97482e061195
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f4735103f277d710dd23adfa19c475c425feaa36
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33403333"
---
# <a name="addfile2-method"></a>AddFile2 메서드
어셈블리에 파일을 추가합니다. 바인딩되지 않은 모듈을 만드는 데 사용할 수도 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT AddFile2(  
    mdAssembly AssemblyID,  
    LPCWSTR pszFilename,  
    DWORD dwFlags,  
    IMetaDataEmit2* pEmitter,  
    mdFile* pFileToken  
) PURE;  
```  
  
#### <a name="parameters"></a>매개 변수  
 `AssemblyID`  
 파일이 추가 되는 어셈블리에 대 한 ID입니다.  
  
 `pszFilename`  
 추가할 파일의 이름입니다.  
  
 `dwFlags`  
 COM + `FileDef` 플래그와 같은 `ffContainsNoMetaData` 및 `ffWriteable`합니다. `dwFlags` 에 전달 [DefineFile 메서드](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md)합니다.  
  
 `pEmitter`  
 인터페이스를 [IMetaDataEmit2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md) 인터페이스입니다.  
  
 `pFileToken`  
 추가 중인 파일에 대 한 ID를 받습니다.  
  
## <a name="return-value"></a>반환 값  
 메서드가 성공 하면 S_OK를 반환 합니다.  
  
## <a name="requirements"></a>요구 사항  
 Alink.h가 필요합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IALink2 인터페이스](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [IALink 인터페이스](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [ALink API](../../../../docs/framework/unmanaged-api/alink/index.md)
