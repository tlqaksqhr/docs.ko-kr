---
title: "ICorDebugModule::GetMetaDataInterface 메서드"
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
- ICorDebugModule.GetMetaDataInterface
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetMetaDataInterface
helpviewer_keywords:
- ICorDebugModule::GetMetaDatainterface method [.NET Framework debugging]
- GetMetaDatainterface method [.NET Framework debugging]
ms.assetid: 30d906f2-cf35-4fa9-9d4c-0c31b58c9f3a
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d374b83155ccc8511c6e3217a8a49819d81a7d48
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmodulegetmetadatainterface-method"></a>ICorDebugModule::GetMetaDataInterface 메서드
모듈에 대 한 메타 데이터를 검사 하는 데 사용할 수 있는 메타 데이터 인터페이스 개체를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetMetaDataInterface (  
    [in] REFIID      riid,  
    [out] IUnknown **ppObj  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `riid`  
 [in] 메타 데이터 인터페이스를 지정 하는 참조 ID입니다.  
  
 `ppObj`  
 [out] 주소에 대 한 포인터는 `T:IUnknown` 개체 중 하나를 [메타 데이터 인터페이스](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)합니다.  
  
## <a name="remarks"></a>설명  
 디버거에서 사용할 수는 `GetMetaDataInterface` 메서드를 해당 모듈을 편집 하기 위해 수행 해야 하는 모듈에 대 한 원래 메타 데이터의 복사본을 만듭니다. 디버거 호출 `GetMetaDataInterface` 가져오려는 [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) 인터페이스 개체는 모듈에 대 한 호출 [imetadataemit:: Savetomemory](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-savetomemory-method.md) 메모리에 모듈의 메타 데이터의 복사본을 저장 하려면.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [메타데이터](../../../../docs/framework/unmanaged-api/metadata/index.md)
