---
title: "ICorDebugAppDomain2::GetArrayOrPointerType 메서드"
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
- ICorDebugAppDomain2.GetArrayOrPointerType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain2::GetArrayOrPointerType
helpviewer_keywords:
- GetArrayOrPointerType method [.NET Framework debugging]
- ICorDebugAppDomain2::GetArrayOrPointerType method [.NET Framework debugging]
ms.assetid: 97e493f5-3a62-4ec7-b42f-4af57bf71f57
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 6beb75638ccbf81149fd7fa1682acca3e7673dc8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugappdomain2getarrayorpointertype-method"></a>ICorDebugAppDomain2::GetArrayOrPointerType 메서드
지정된 된 형식, 포인터 또는 지정된 된 형식에 대 한 참조의 배열을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetArrayOrPointerType (  
    [in]  CorElementType    elementType,  
    [in]  ULONG32           nRank,  
    [in]  ICorDebugType     *pTypeArg,  
    [out] ICorDebugType     **ppType  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `elementType`  
 [in] 기본 네이티브 형식 (배열, 포인터 또는 참조)를 만들 수를 지정 하는 CorElementType 열거형의 값입니다.  
  
 `nRank`  
 [in] 배열 차수 (차원 수). 이 값 경우 0 이어야 합니다 `elementType` 포인터 또는 참조 형식을 지정 합니다.  
  
 `pTypeArg`  
 [in] 배열의 형식을 나타내는 ICorDebugType 개체에 대 한 포인터, 포인터 또는 참조를 만들 수 있습니다.  
  
 `ppType`  
 [out] 주소에 대 한 포인터는 `ICorDebugType` 생성 된 배열, 포인터 형식 또는 참조를 나타내는 개체를 입력 합니다.  
  
## <a name="remarks"></a>설명  
 값 *elementType* 다음 중 하나 여야 합니다.  
  
-   ELEMENT_TYPE_PTR  
  
-   ELEMENT_TYPE_BYREF  
  
-   ELEMENT_TYPE_ARRAY 또는 ELEMENT_TYPE_SZARRAY  
  
 하는 경우의 값 *elementType* ELEMENT_TYPE_PTR 또는 ELEMENT_TYPE_BYREF, *nRank* 0 이어야 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
