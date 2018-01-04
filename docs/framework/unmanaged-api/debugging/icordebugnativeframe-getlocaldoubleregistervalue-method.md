---
title: "ICorDebugNativeFrame::GetLocalDoubleRegisterValue 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugNativeFrame.GetLocalDoubleRegisterValue
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugNativeFrame::GetLocalDoubleRegisterValue
helpviewer_keywords:
- ICorDebugNativeFrame::GetLocalDoubleRegisterValue method [.NET Framework debugging]
- GetLocalDoubleRegisterValue method [.NET Framework debugging]
ms.assetid: 1f838215-ac8a-434f-8ce6-03021d3098d9
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ece07fcffbc0d0e6b8cf06cc04866c1b651e6a01
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugnativeframegetlocaldoubleregistervalue-method"></a>ICorDebugNativeFrame::GetLocalDoubleRegisterValue 메서드
네이티브 프레임에 대 한 지정 된 두 레지스터에 저장 된 지역 변수 또는 인수의 값을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetLocalDoubleRegisterValue (  
    [in] CorDebugRegister   highWordReg,  
    [in] CorDebugRegister   lowWordReg,  
    [in] ULONG              cbSigBlob,  
    [in] PCCOR_SIGNATURE    pvSigBlob,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `highWordReg`  
 [in] 값의 많은 단어를 포함 하는 레지스터를 지정 하는 "CorDebugRegister" 열거형의 값입니다.  
  
 `lowWordReg`  
 [in] 값은 `CorDebugRegister` 값의 낮은 단어를 포함 하는 레지스터를 지정 하는 열거형입니다.  
  
 `cbSigBlob`  
 [in] 참조 하는 이진 메타 데이터 서명의 크기를 지정 하는 정수는 `pvSigBlob` 매개 변수입니다.  
  
 `pvSigBlob`  
 [in] A `PCCOR_SIGNATURE` 값의 형식의 이진 메타 데이터 서명을를 가리키는 값입니다.  
  
 `ppValue`  
 [out] 지정 된 레지스터에 저장 된 검색 된 값을 나타내는 "ICorDebugValue" 개체의 주소에 대 한 포인터입니다.  
  
## <a name="remarks"></a>설명  
 `GetLocalDoubleRegisterValue` 네이티브 프레임이 또는-just-in-time (JIT) 메서드를 사용할 수 있으며-컴파일된 프레임입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 
