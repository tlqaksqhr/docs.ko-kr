---
title: "IMetaDataEmit::DefineEvent 메서드"
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
- IMetaDataEmit.DefineEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineEvent
helpviewer_keywords:
- IMetaDataEmit::DefineEvent method [.NET Framework metadata]
- DefineEvent method [.NET Framework metadata]
ms.assetid: cf064bac-9a9f-41c5-9e1d-108ff7af3afe
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 8f27c0a01dd795cfcc5399c4115cd6d905629fd7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitdefineevent-method"></a>IMetaDataEmit::DefineEvent 메서드
지정한 메타 데이터 서명을 사용 하 여 이벤트에 대 한 정의 만들고 해당 이벤트 정의 토큰을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT DefineEvent (   
    [in]  mdTypeDef    td,   
    [in]  LPCWSTR      szEvent,   
    [in]  DWORD        dwEventFlags,   
    [in]  mdToken      tkEventType,   
    [in]  mdMethodDef  mdAddOn,   
    [in]  mdMethodDef  mdRemoveOn,   
    [in]  mdMethodDef  mdFire,   
    [in]  mdMethodDef  rmdOtherMethods[],   
    [out] mdEvent      *pmdEvent   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `td`  
 [in] 대상 클래스 또는 인터페이스에 대 한 토큰입니다. 이 역할은 한 `mdTypeDef` 또는 `mdTypeDefNil` 토큰입니다.  
  
 `szEvent`  
 [in] 이벤트의 이름입니다.  
  
 `dwEventFlags`  
 [in] 이벤트 플래그입니다.  
  
 `tkEventType`  
 [in] 이벤트 클래스에 대 한 토큰입니다. 이 한 `mdTypeDef`, `mdTypeRef`, 또는 `mdTokenNil` 토큰입니다.  
  
 `mdAddOn`  
 [in] 이벤트 또는 null에 가입 하는 데 사용 되는 메서드.  
  
 `mdRemoveOn`  
 [in] 이벤트 또는 null를 등록 취소 하는 데 사용 되는 메서드.  
  
 `mdFire`  
 [in] 이벤트를 발생 시키는 (파생된 클래스)에 의해 사용 되는 메서드.  
  
 `rmdOtherMethods[]`  
 [in] 이벤트와 연결 된 다른 방법에 대 한 토큰의 배열입니다. 배열의으로 종료 되는 `mdMethodDefNil` 토큰입니다.  
  
 `pmdEvent`  
 [out] 이벤트에 할당 된 메타 데이터 토큰입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** Cor.h  
  
 **라이브러리:** MSCorEE.dll에서 리소스로 사용  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [IMetaDataEmit 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [IMetaDataEmit2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
