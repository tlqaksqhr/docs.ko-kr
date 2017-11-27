---
title: "ICorDebugProcess2::GetReferenceValueFromGCHandle 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess2.GetReferenceValueFromGCHandle
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess2::GetReferenceValueFromGCHandle
helpviewer_keywords:
- GetReferenceValueFromGCHandle method [.NET Framework debugging]
- ICorDebugProcess2::GetReferenceValueFromGCHandle method [.NET Framework debugging]
ms.assetid: 8bdd7f4c-19f2-4ede-875e-603773e8c128
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d40d1799a7c1572e8213fda3a163fb9a84060f92
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugprocess2getreferencevaluefromgchandle-method"></a>ICorDebugProcess2::GetReferenceValueFromGCHandle 메서드
가비지 수집을 처리 하는 지정된 된 관리 되는 개체에 대 한 참조 포인터를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetReferenceValueFromGCHandle (  
    [in]  UINT_PTR                 handle,  
    [out] ICorDebugReferenceValue  **pOutValue  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `handle`  
 [in] 가비지 컬렉션 핸들을 가진 관리 되는 개체에 대 한 포인터입니다. 이 값은 한 <xref:System.IntPtr> 개체 및에서 검색할 수는 <xref:System.Runtime.InteropServices.GCHandle> 관리 되는 개체에 대 한 합니다.  
  
 `pOutValue`  
 [out] 지정된 된 관리 되는 개체에 대 한 참조를 나타내는 ICorDebugReferenceValue 개체의 주소에 대 한 포인터입니다.  
  
## <a name="remarks"></a>설명  
 가비지 컬렉션 참조 값으로 반환 된 참조 값을 혼동 하지 마십시오.  
  
 반환 된 참조는 일반적인 참조 처럼 동작합니다. 코드 실행이 중단점 후 계속 하는 경우 비활성화 됩니다. 대상 개체의 수명은 참조 값의 수명에 의해 영향을 받지 않습니다.  
  
> [!NOTE]
>  `GetReferenceValueFromGCHandle` 메서드 핸들을 확인 하지 않습니다. 따라서는 `GetReferenceValueFromGCHandle` 메서드는 디버거와 잘못 된 핸들이 전달 될 경우 디버깅 중인 코드에 잠재적으로 손상 될 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
