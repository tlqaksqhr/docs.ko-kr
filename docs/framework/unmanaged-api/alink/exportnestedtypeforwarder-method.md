---
title: "ExportNestedTypeForwarder 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IALink.ExportNestedTypeForwarder
api_location: alink.dll
api_type: COM
f1_keywords: ExportNestedTypeForwarder
helpviewer_keywords: ExportNestedTypeForwarder method
ms.assetid: 886ea6c5-6b26-4b88-8bf6-448d6d191950
topic_type: apiref
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 41c0984e4439b89ddee2b55bbca7a098075d6bd7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="exportnestedtypeforwarder-method"></a>ExportNestedTypeForwarder 메서드
지정된 된 어셈블리의 형식 테이블에 중첩 된 형식에 대 한 형식 전달자를 추가합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT ExportNestedTypeForwarder(  
    mdAssembly      AssemblyID,  
    mdToken         FileToken,  
    mdTypeDef       TypeToken,  
    mdExportedType  ParentType,  
    LPCWSTR         pszTypename,  
    DWORD           dwFlags,  
    mdExportedType* pType  
) PURE;  
```  
  
#### <a name="parameters"></a>매개 변수  
 `AssemblyID`  
 내보낼 어셈블리의 ID입니다.  
  
 `FileToken`  
 파일 형식을 정의 하는 파일의 토큰 또는 어셈블리 ID입니다.  
  
 `TypeToken`  
 토큰 형식입니다.  
  
 `ParentType`  
 부모 유형의 토큰입니다.  
  
 `pszTypename`  
 내보낼 정규화 된 형식 이름입니다.  
  
 `dwFlags`  
 `ComType`와 같은 플래그 `tdPublic` 또는 `tdNested`합니다.  
  
 `pType`  
 내보내기 형식의 토큰을 받습니다. 이 중첩 된 형식을 내보내는에 필요 합니다.  
  
## <a name="return-value"></a>반환 값  
 메서드가 성공 하면 S_OK를 반환 합니다.  
  
## <a name="requirements"></a>요구 사항  
 Alink.h 필요  
  
## <a name="see-also"></a>참고 항목  
 [IALink 인터페이스](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [IALink2 인터페이스](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [ALink API](../../../../docs/framework/unmanaged-api/alink/index.md)
