---
title: "IMetaDataEmit::SetEventProps 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.SetEventProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::SetEventProps
helpviewer_keywords:
- IMetaDataEmit::SetEventProps method [.NET Framework metadata]
- SetEventProps method [.NET Framework metadata]
ms.assetid: 3b039e50-63ec-4730-99ff-2327408de477
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f8e2089c3f4b4e7677c2ddb9eabc8ee08cfd3695
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitseteventprops-method"></a>IMetaDataEmit::SetEventProps 메서드
설정 하거나 업데이트에 대 한 이전 호출에서 정의 된 이벤트의 지정된 된 기능 [imetadataemit:: Defineevent](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineevent-method.md)합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT SetEventProps (  
    [in]  mdEvent     ev,   
    [in]  DWORD       dwEventFlags,   
    [in]  mdToken     tkEventType,   
    [in]  mdMethodDef mdAddOn,   
    [in]  mdMethodDef mdRemoveOn,   
    [in]  mdMethodDef mdFire,   
    [in]  mdMethodDef rmdOtherMethods[]   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `ev`  
 [in] 이벤트 토큰입니다.  
  
 `dwEventFlags`  
 [in] 이벤트 플래그입니다. 이 비트 마스크의 `CorEventAttr` 값입니다.  
  
 `tkEventType`  
 [in] 이벤트 클래스에 대 한 토큰입니다. 이 역할은 한 `mdTypeDef` 또는 `mdTypeRef` 토큰입니다.  
  
 `mdAddOn`  
 [in] 이벤트 또는 null에 가입 하는 데 사용 되는 메서드.  
  
 `mdRemoveOn`  
 [in] 이벤트 또는 null를 등록 취소 하는 데 사용 되는 메서드.  
  
 `mdFire`  
 [in] 이벤트를 발생 시키는 (파생된 클래스)에 의해 사용 되는 메서드.  
  
 `rmdOtherMethods[]`  
 [in] 이벤트와 연결 된 다른 방법에 대 한 토큰의 배열입니다. 배열의 마지막 요소 여야 합니다 `mdMethodDefNil`합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** Cor.h  
  
 **라이브러리:** MSCorEE.dll에서 리소스로 사용  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [IMetaDataEmit 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [IMetaDataEmit2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
