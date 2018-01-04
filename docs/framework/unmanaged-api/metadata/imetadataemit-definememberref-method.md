---
title: "IMetaDataEmit::DefineMemberRef 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.DefineMemberRef
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::DefineMemberRef
helpviewer_keywords:
- DefineMemberRef method [.NET Framework metadata]
- IMetaDataEmit::DefineMemberRef method [.NET Framework metadata]
ms.assetid: 21b5bcb8-ea75-4962-8acc-ad17584061e5
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 38c2c495bc88dadae2d71b1b3710f30998023516
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitdefinememberref-method"></a>IMetaDataEmit::DefineMemberRef 메서드
현재 범위를 벗어난 모듈의 멤버에 대 한 참조를 정의 하 고 해당 참조 정의 하는 토큰을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT DefineMemberRef (   
    [in]  mdToken           tkImport,   
    [in]  LPCWSTR           szName,   
    [in]  PCCOR_SIGNATURE   pvSigBlob,   
    [in]  ULONG             cbSigBlob,   
    [out] mdMemberRef       *pmr   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `tkImport`  
 [in] 멤버가 전역; 경우 대상 멤버의 클래스 또는 인터페이스에 대 한 토큰 멤버가 전역,이 경우에 `mdModuleRef` 해당 다른 파일에 대 한 토큰입니다.  
  
 `szName`  
 [in] 대상 멤버의 이름입니다.  
  
 `pvSigBlob`  
 [in] 대상 멤버의 서명입니다.  
  
 `cbSigBlob`  
 [in] 바이트 수 `pvSigBlob`합니다.  
  
 `pmr`  
 [out] `mdMemberRef` 할당 된 토큰입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** Cor.h  
  
 **라이브러리:** MSCorEE.dll에서 리소스로 사용  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [IMetaDataEmit 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [IMetaDataEmit2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
