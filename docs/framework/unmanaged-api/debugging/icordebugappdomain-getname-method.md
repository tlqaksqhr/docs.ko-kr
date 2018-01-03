---
title: "ICorDebugAppDomain::GetName 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugAppDomain.GetName
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugAppDomain::GetName
helpviewer_keywords:
- ICorDebugAppDomain::GetName method [.NET Framework debugging]
- GetName method, ICorDebugAppDomain interface [.NET Framework debugging]
ms.assetid: 02c596d7-00b0-4e2c-856b-5425158fcefd
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 62defcb4b7a2f143269c7f617b762e3419d55426
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugappdomaingetname-method"></a>ICorDebugAppDomain::GetName 메서드
응용 프로그램 도메인의 이름을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetName (  
    [in]  ULONG32           cchName,  
    [out] ULONG32           *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]   
         WCHAR              szName[]  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `cchName`  
 [in] `szName` 배열의 크기입니다. 이 메서드를 쿼리 모드로 전환 하는 0으로이 값을 설정 합니다.  
  
 `pcchName`  
 [out] 이름 또는에 실제로 반환 된 문자 수의 크기에 대 한 포인터 `szName`합니다. 이 값을 버퍼의 크기를 알고 호출자에 게 사용 하면 쿼리 모드에서 이름에 할당할 수 있습니다.  
  
 `szName`  
 [out] 응용 프로그램 도메인의 이름을 저장 하는 배열입니다.  
  
## <a name="remarks"></a>설명  
 디버거 호출는 `GetName` 메서드를 한 번의 이름에 필요한 버퍼 크기를 가져옵니다. 디버거에서 버퍼를 할당 하 고 메서드를 호출 하는 두 번째 시간에 버퍼를 채웁니다. 첫 번째 호출의 이름, 크기를 가져오려면 라고 *쿼리 모드*합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
