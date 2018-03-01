---
title: "ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs 메서드"
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
- ICorDebugAppDomain3.GetCachedWinRTTypesForIIDs
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs
helpviewer_keywords:
- ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs method, [.NET Framework debugging]
- GetCachedWinRTTypesForIIDs method, ICorDebugAppDomain3 interface [.NET Framework debugging]
ms.assetid: 23682ca0-1bcf-48e6-996e-69f7ba337682
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 5a7ce44dcfc709b4fea1952471cf31f5f07d4d0e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugappdomain3getcachedwinrttypesforiids-method"></a><span data-ttu-id="b0e4a-102">ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs 메서드</span><span class="sxs-lookup"><span data-stu-id="b0e4a-102">ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs Method</span></span>
<span data-ttu-id="b0e4a-103">캐시에 대 한 열거자를 가져옵니다 [!INCLUDE[wrt](../../../../includes/wrt-md.md)] 10 인터페이스 식별자에 따라 응용 프로그램 도메인의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="b0e4a-103">Gets an enumerator for cached [!INCLUDE[wrt](../../../../includes/wrt-md.md)] types in an application domain based on their interface identifiers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0e4a-104">구문</span><span class="sxs-lookup"><span data-stu-id="b0e4a-104">Syntax</span></span>  
  
```  
HRESULT GetCachedWinRTTypesForIIDs (   
    [in]  ULONG32            cReqTypes,  
    [in]  GUID                *iidsToResolve,  
    [out] ICorDebugTypeEnum   **ppTypesEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b0e4a-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b0e4a-105">Parameters</span></span>  
 `cReqTypes`  
 <span data-ttu-id="b0e4a-106">[in] 필요한 형식의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="b0e4a-106">[in] The number of required types.</span></span>  
  
 `iidsToResolve`  
 <span data-ttu-id="b0e4a-107">[in] 관리 되는 표현에 해당 하는 인터페이스 식별자를 포함 하는 배열에 대 한 포인터는 [!INCLUDE[wrt](../../../../includes/wrt-md.md)] 형식을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0e4a-107">[in] A pointer to an array that contains the interface identifiers corresponding to the managed representations of the [!INCLUDE[wrt](../../../../includes/wrt-md.md)] types to be retrieved.</span></span>  
  
 `ppTypesEnum`  
 <span data-ttu-id="b0e4a-108">[out] 캐시 된 열거를 허용 하는 "ICorDebugTypeEnum" 인터페이스 개체의 주소에 대 한 포인터의 표현을 관리는 [!INCLUDE[wrt](../../../../includes/wrt-md.md)] 형식을 가져올의 인터페이스 식별자에 따라 `iidsToResolve`합니다.</span><span class="sxs-lookup"><span data-stu-id="b0e4a-108">[out] A pointer to the address of an "ICorDebugTypeEnum" interface object that allows enumeration of the cached managed representations of the [!INCLUDE[wrt](../../../../includes/wrt-md.md)] types retrieved, based on the interface identifiers in `iidsToResolve`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b0e4a-109">설명</span><span class="sxs-lookup"><span data-stu-id="b0e4a-109">Remarks</span></span>  
 <span data-ttu-id="b0e4a-110">"ICorDebugTypeEnum" 컬렉션의 해당 항목의 형식을 갖습니다 메서드가 특정 인터페이스 식별자에 대 한 정보를 검색 하지 못하면 `ELEMENT_TYPE_END` 데이터 검색 문제 인 한 오류에 대 한 또는 `ELEMENT_TYPE_VOID` 알 수 없는 인터페이스에 대 한 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="b0e4a-110">If the method fails to retrieve information for a specific interface identifier, the corresponding entry in the "ICorDebugTypeEnum" collection will have a type of `ELEMENT_TYPE_END` for errors due to data retrieval issues, or `ELEMENT_TYPE_VOID` for unknown interface identifiers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b0e4a-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b0e4a-111">Requirements</span></span>  
 <span data-ttu-id="b0e4a-112">**플랫폼:**[!INCLUDE[wrt](../../../../includes/wrt-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b0e4a-112">**Platforms:** [!INCLUDE[wrt](../../../../includes/wrt-md.md)]</span></span>  
  
 <span data-ttu-id="b0e4a-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b0e4a-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b0e4a-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b0e4a-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b0e4a-115">**.NET framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b0e4a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0e4a-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b0e4a-116">See Also</span></span>  
 [<span data-ttu-id="b0e4a-117">ICorDebugAppDomain3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b0e4a-117">ICorDebugAppDomain3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-interface.md)
