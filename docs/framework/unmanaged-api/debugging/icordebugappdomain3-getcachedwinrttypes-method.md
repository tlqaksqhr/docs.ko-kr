---
title: ICorDebugAppDomain3::GetCachedWinRTTypes 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain3.GetCachedWinRTTypes
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain3::GetCachedWinRTTypes
helpviewer_keywords:
- ICorDebugAppDomain3::GetCachedWinRTTypes method [.NET Framework debugging]
- GetCachedWinRTTypes method, ICorDebugAppDomain3 interface [.NET Framework debugging]
ms.assetid: 9afd0e04-a403-41e2-9528-a6dcbcdcbd4d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 782a6cf70aa3e3446d8da3160712d57245afe176
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33405527"
---
# <a name="icordebugappdomain3getcachedwinrttypes-method"></a><span data-ttu-id="40c29-102">ICorDebugAppDomain3::GetCachedWinRTTypes 메서드</span><span class="sxs-lookup"><span data-stu-id="40c29-102">ICorDebugAppDomain3::GetCachedWinRTTypes Method</span></span>
<span data-ttu-id="40c29-103">모든 캐시에 대 한 열거자를 가져옵니다 [!INCLUDE[wrt](../../../../includes/wrt-md.md)] 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="40c29-103">Gets an enumerator for all cached [!INCLUDE[wrt](../../../../includes/wrt-md.md)] types.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40c29-104">구문</span><span class="sxs-lookup"><span data-stu-id="40c29-104">Syntax</span></span>  
  
```  
HRESULT GetCachedWinRTTypes (   
    [out] ICorDebugGuidToTypeEnum **ppGuidToTypeEnum)  
;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="40c29-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="40c29-105">Parameters</span></span>  
 `ppGuidToTypeEnum`  
 <span data-ttu-id="40c29-106">[out] 에 대 한 포인터는 [ICorDebugGuidToTypeEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-interface.md) 인터페이스 개체의 관리 되는 표현을 열거할 수 있는 [!INCLUDE[wrt](../../../../includes/wrt-md.md)] 현재 응용 프로그램 도메인에 로드 된 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="40c29-106">[out] A pointer to an [ICorDebugGuidToTypeEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-interface.md) interface object that can enumerate the managed representations of [!INCLUDE[wrt](../../../../includes/wrt-md.md)] types currently loaded in the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="40c29-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="40c29-107">Requirements</span></span>  
 <span data-ttu-id="40c29-108">**플랫폼:** [!INCLUDE[wrt](../../../../includes/wrt-md.md)]</span><span class="sxs-lookup"><span data-stu-id="40c29-108">**Platforms:** [!INCLUDE[wrt](../../../../includes/wrt-md.md)]</span></span>  
  
 <span data-ttu-id="40c29-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="40c29-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="40c29-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="40c29-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="40c29-111">**.NET framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="40c29-111">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40c29-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="40c29-112">See Also</span></span>  
 [<span data-ttu-id="40c29-113">ICorDebugAppDomain3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="40c29-113">ICorDebugAppDomain3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-interface.md)
