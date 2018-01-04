---
title: "IBindingDisplay::InitializeForProcess 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IBindingDisplay.InitializeForProcess
api_location: diasymreader.dll
api_type: COM
f1_keywords: IBindingDisplay::InitializeForProcess
helpviewer_keywords:
- IBindingDisplay::InitializeForProcess method [.NET Framework debugging]
- InitializeForProcess method [.NET Framework debugging]
ms.assetid: 59417acb-4e59-46ad-acfe-d827e6ab6078
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 56f55788fcaf08507f413a03c5364ce3bcdbbf3c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ibindingdisplayinitializeforprocess-method"></a>IBindingDisplay::InitializeForProcess 메서드
초기화는 [IBindingDisplay](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md) 개체입니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT InitializeForProcess (  
    [in] ULONG32   pid  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pid`  
 [in] 프로세스 식별자입니다.  
  
## <a name="remarks"></a>설명  
 디버거 호출은 `InitializeForProcess` 바인딩 표시 초기화를 만들 때 메서드. `InitializeForProcess`다른 메서드 전에 호출 해야 `IBindingDisplay` 호출 됩니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** BindingDisplay.h  
  
 **라이브러리:** BindingDisplay.idl  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [IBindingDisplay 인터페이스](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md)
