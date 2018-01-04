---
title: "ICorDebugInternalFrame2::IsCloserToLeaf 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugInternalFrame2.IsCloserToLeaf Method
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugInternalFrame2::IsCloserToLeaf
helpviewer_keywords:
- ICorDebugInternalFrame2::IsCloserToLeaf method [.NET Framework debugging]
- IsCloserToLeaf method [.NET Framework debugging]
ms.assetid: c1d3d1eb-8370-4f25-8297-3bd262b4740a
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7b6b769c25e0cd706eb57965b73d0fcfdcf9b9ea
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebuginternalframe2isclosertoleaf-method"></a>ICorDebugInternalFrame2::IsCloserToLeaf 메서드
확인 여부는 `this` 내부 프레임 보다 더 가까운 리프에 지정된 된 ICorDebugFrame 개체입니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT IsCloserToLeaf([in] ICorDebugFrame * pFrameToCompare,  
                       [out] BOOL * pIsCloser);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pFrameToCompare`  
 [in] 비교에 대 한 포인터 `ICorDebugFrame` 개체입니다.  
  
 `pIsCloser`  
 [out] `true` 경우는 `this` 내부 프레임 보다에 더 가까운 리프로 지정 된 프레임 `pFrameToCompare`, 그렇지 않으면 `false`합니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|비교 했습니다.|  
|E_FAIL|비교를 수행할 수 없습니다.|  
|E_INVALIDARG|`pFrameToCompare` 또는 `pIsCloser`이 null입니다.|  
  
## <a name="remarks"></a>설명  
 `IsCloserToLeaf`데 사용할 수는 내부 다른 스택 프레임의 프레임 인터리빙에 대 한 정책을 구현 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICorDebugInternalFrame2 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md)  
 [디버깅 인터페이스](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [디버깅](../../../../docs/framework/unmanaged-api/debugging/index.md)
