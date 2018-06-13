---
title: ICorDebugInternalFrame2::GetFrameAddress 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugInternalFrame2.GetFrameAddress Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugInternalFrame2::GetFrameAddress
helpviewer_keywords:
- GetFrameAddress method [.NET Framework debugging]
- ICorDebugInternalFrame2::GetFrameAddress method [.NET Framework debugging]
ms.assetid: 4ee8d058-ffc8-4967-9133-a5adfef4e518
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d088aaaaa80ee3513a37ea0345d720832504c005
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33421150"
---
# <a name="icordebuginternalframe2getframeaddress-method"></a><span data-ttu-id="28270-102">ICorDebugInternalFrame2::GetFrameAddress 메서드</span><span class="sxs-lookup"><span data-stu-id="28270-102">ICorDebugInternalFrame2::GetFrameAddress Method</span></span>
<span data-ttu-id="28270-103">내부 프레임의 스택 주소를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="28270-103">Returns the stack address of the internal frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28270-104">구문</span><span class="sxs-lookup"><span data-stu-id="28270-104">Syntax</span></span>  
  
```  
HRESULT GetFrameAddress([out] CORDB_ADDRESS *pAddress);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="28270-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="28270-105">Parameters</span></span>  
 `pAddress`  
 <span data-ttu-id="28270-106">[out] 에 대 한 포인터는 `CORDB_ADDRESS` 내부 프레임에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="28270-106">[out] Pointer to the `CORDB_ADDRESS` for the internal frame.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="28270-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="28270-107">Return Value</span></span>  
 <span data-ttu-id="28270-108">이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="28270-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="28270-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="28270-109">HRESULT</span></span>|<span data-ttu-id="28270-110">설명</span><span class="sxs-lookup"><span data-stu-id="28270-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="28270-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="28270-111">S_OK</span></span>|<span data-ttu-id="28270-112">내부 프레임의 주소 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="28270-112">The address of the internal frame was successfully returned.</span></span>|  
|<span data-ttu-id="28270-113">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="28270-113">E_FAIL</span></span>|<span data-ttu-id="28270-114">내부 프레임의 주소를 반환할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="28270-114">The address of the internal frame could not be returned.</span></span>|  
|<span data-ttu-id="28270-115">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="28270-115">E_INVALIDARG</span></span>|<span data-ttu-id="28270-116">`pAddress`가 `null`인 경우</span><span class="sxs-lookup"><span data-stu-id="28270-116">`pAddress` is `null`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="28270-117">설명</span><span class="sxs-lookup"><span data-stu-id="28270-117">Remarks</span></span>  
 <span data-ttu-id="28270-118">반환 된 값 `pAddress` 는 스택의 다른 프레임을 기준으로 내부 프레임의 위치를 확인 하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28270-118">The value returned in `pAddress` can be used to determine the location of the internal frame relative to other frames on the stack.</span></span> <span data-ttu-id="28270-119">IA 64 기반 컴퓨터에도 스택에 거주 하 고 내부 프레임 및 포인터는 없습니다. 해당 백업 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="28270-119">Even on IA-64-based computers, the internal frame lives on the stack only, and there is no corresponding pointer to a backing store.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="28270-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="28270-120">Requirements</span></span>  
 <span data-ttu-id="28270-121">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="28270-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="28270-122">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="28270-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="28270-123">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="28270-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="28270-124">**.NET framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="28270-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28270-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="28270-125">See Also</span></span>  
 [<span data-ttu-id="28270-126">ICorDebugInternalFrame2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="28270-126">ICorDebugInternalFrame2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md)  
 [<span data-ttu-id="28270-127">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="28270-127">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="28270-128">디버깅</span><span class="sxs-lookup"><span data-stu-id="28270-128">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
