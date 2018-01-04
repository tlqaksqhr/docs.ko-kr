---
title: "IMetaDataDispenserEx::GetOption 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataDispenserEx.GetOption
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataDispenserEx::GetOption
helpviewer_keywords:
- GetOption method [.NET Framework metadata]
- IMetaDataDispenserEx::GetOption method [.NET Framework metadata]
ms.assetid: d7f794e5-8e25-4d65-850a-7c34fbfce87d
topic_type: apiref
caps.latest.revision: "16"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1fd59fa20e95de8486eaa7f18a63333459361ac8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="imetadatadispenserexgetoption-method"></a>IMetaDataDispenserEx::GetOption 메서드
현재 메타 데이터 범위에 대 한 지정된 된 옵션의 값을 가져옵니다. 옵션은 현재 메타 데이터 범위에 대 한 호출의 처리 방법을 제어 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetOption (  
    [in]  REFGUID         optionId,   
    [out] const VARIANT   *pValue  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `optionId`  
 [in] 검색할 옵션을 지정 하는 GUID에 대 한 포인터입니다. 지원 되는 Guid의 목록은 설명 섹션을 참조 하십시오.  
  
 `pValue`  
 [out] 반환 된 옵션의 값입니다. 이 값의 형식은 지정된 된 옵션의 종류의 변형 됩니다.  
  
## <a name="remarks"></a>설명  
 다음 목록은 지원 되는이 메서드에 대 한 Guid를 나타냅니다. 설명에 대 한 참조는 [imetadatadispenserex:: Setoption](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-setoption-method.md) 메서드. 경우 `optionId` 은이 목록에 없는이 메서드는 HRESULT를 반환 `E_INVALIDARG`, 잘못 된 매개 변수를 나타내는입니다.  
  
-   MetaDataCheckDuplicatesFor  
  
-   MetaDataRefToDefCheck  
  
-   MetaDataNotificationForTokenMovement  
  
-   MetaDataSetENC  
  
-   MetaDataErrorIfEmitOutOfOrder  
  
-   MetaDataGenerateTCEAdapters  
  
-   MetaDataLinkerOptions  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** Cor.h  
  
 **라이브러리:** MsCorEE.dll에서 리소스로 사용  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [IMetaDataDispenserEx 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)  
 [IMetaDataDispenser 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
