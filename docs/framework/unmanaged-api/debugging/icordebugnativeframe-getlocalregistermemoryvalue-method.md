---
title: "ICorDebugNativeFrame::GetLocalRegisterMemoryValue 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugNativeFrame.GetLocalRegisterMemoryValue
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugNativeFrame::GetLocalRegisterMemoryValue
helpviewer_keywords:
- ICorDebugNativeFrame::GetLocalRegisterMemoryValue method [.NET Framework debugging]
- GetLocalRegisterMemoryValue method [.NET Framework debugging]
ms.assetid: d350f69d-9aff-4f5a-8301-daea22dee2da
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 58d48b8d3b45afe4018d80ce30066708085c517a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugnativeframegetlocalregistermemoryvalue-method"></a>ICorDebugNativeFrame::GetLocalRegisterMemoryValue 메서드
그 중 낮은 word와 word 높은 메모리 위치에 저장 되 고 네이티브 프레임에 대 한 레지스터를 각각 지정 된 지역 변수 또는 인수의 값을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetLocalRegisterMemoryValue (  
    [in] CorDebugRegister   highWordReg,  
    [in] CORDB_ADDRESS      lowWordAddress,  
    [in] ULONG              cbSigBlob,  
    [in] PCCOR_SIGNATURE    pvSigBlob,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `highWordReg`  
 [in] 값의 많은 단어를 포함 하는 레지스터를 지정 하는 "CorDebugRegister" 열거형의 값입니다.  
  
 `lowWordAddress`  
 [in] A `CORDB_ADDRESS` 값의 낮은 단어를 포함 하는 메모리 위치를 지정 하는 값입니다.  
  
 `cbSigBlob`  
 [in] 참조 하는 이진 메타 데이터 서명의 크기를 지정 하는 정수는 `pvSigBlob` 매개 변수입니다.  
  
 `pvSigBlob`  
 [in] A `PCCOR_SIGNATURE` 값의 형식의 이진 메타 데이터 서명을를 가리키는 값입니다.  
  
 `ppValue`  
 [out] 지정된 된 레지스터 및 메모리 위치에 저장 된 검색 된 값을 나타내는 "ICorDebugValue" 개체의 주소에 대 한 포인터입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 
