---
title: "IMetaDataEmit::SetClassLayout 메서드"
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
- IMetaDataEmit.SetClassLayout
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetClassLayout
helpviewer_keywords:
- IMetaDataEmit::SetClassLayout method [.NET Framework metadata]
- SetClassLayout method [.NET Framework metadata]
ms.assetid: 2576c449-388d-4434-a0e1-9f53991e11b6
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e0c02e615bf77a2cc9136b50efd7395585959141
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitsetclasslayout-method"></a>IMetaDataEmit::SetClassLayout 메서드
이전 호출에서 정의 된 클래스에 대 한 필드 레이아웃을 완료 [DefineTypeDef 메서드](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md)합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT SetClassLayout (  
    [in]  mdTypeDef           td,   
    [in]  DWORD               dwPackSize,   
    [in]  COR_FIELD_OFFSET    rFieldOffsets[],   
    [in]  ULONG               ulClassSize   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `td`  
 [in] `mdTypeDef` 토큰을 배치 하는 클래스를 지정 합니다.  
  
 `dwPackSize`  
 [in] 압축 크기: 1, 2, 4, 8 또는 16 바이트입니다. 압축 크기는 인접 한 필드 사이의 바이트 수입니다.  
  
 `rFieldOffsets`  
 [in] 배열을 [COR_FIELD_OFFSET](../../../../docs/framework/unmanaged-api/metadata/cor-field-offset-structure.md) 구조를 각각 클래스의 필드와 필드는 클래스 내에서 오프셋을 지정 합니다. 사용 하 여 배열을 종료 `mdTokenNil`합니다.  
  
 `ulClassSize`  
 [in] 클래스의 바이트 크기입니다.  
  
## <a name="remarks"></a>설명  
 클래스를 호출 하 여 초기에 정의 되는 [imetadataemit:: Definetypedef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md) 메서드 및 클래스의 필드에 대 한 세 가지 레이아웃 중 하나를 지정: 자동, 순차적으로 또는 명시적입니다. 일반적으로 자동 레이아웃을 사용 하는 필드의 레이아웃에 가장 좋은 방법은 선택 하 여 런타임에서 수 있도록 합니다.  
  
 그러나 필드를 비관리 코드에서 사용 하는 정렬 기준에 따라 레이아웃을 할 수 있습니다. 이 경우 순차적으로 또는 명시적 레이아웃 및 호출을 선택 `SetClassLayout` 필드의 레이아웃을 완료 하려면:  
  
-   순차적 레이아웃이: 압축 크기를 지정 합니다. 필드의 자연 크기 또는 압축 크기는 필드의 더 작은 오프셋에 따라 정렬 됩니다. 설정 `rFieldOffsets` 및 `ulClassSize` 0입니다.  
  
-   명시적 레이아웃: 각 필드의 오프셋을 지정 하거나, 클래스 크기와 압축 크기를 지정 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** Cor.h  
  
 **라이브러리:** MSCorEE.dll에서 리소스로 사용  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [IMetaDataEmit 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [IMetaDataEmit2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
