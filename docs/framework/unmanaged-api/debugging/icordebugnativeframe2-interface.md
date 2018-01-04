---
title: "ICorDebugNativeFrame2 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugNativeFrame2
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugNativeFrame2
helpviewer_keywords: ICorDebugNativeFrame2 interface [.NET Framework debugging]
ms.assetid: 52a80838-af36-4399-bc97-d8a4c6d76df2
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f501d49f007e22c6f7db0e759ee19b40f87b4b33
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugnativeframe2-interface"></a><span data-ttu-id="8f5cb-102">ICorDebugNativeFrame2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8f5cb-102">ICorDebugNativeFrame2 Interface</span></span>
<span data-ttu-id="8f5cb-103">자식 및 부모 프레임 관계를 테스트하는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8f5cb-103">Provides methods that test for child and parent frame relationships.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8f5cb-104">메서드</span><span class="sxs-lookup"><span data-stu-id="8f5cb-104">Methods</span></span>  
  
|<span data-ttu-id="8f5cb-105">메서드</span><span class="sxs-lookup"><span data-stu-id="8f5cb-105">Method</span></span>|<span data-ttu-id="8f5cb-106">설명</span><span class="sxs-lookup"><span data-stu-id="8f5cb-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8f5cb-107">IsChild 메서드</span><span class="sxs-lookup"><span data-stu-id="8f5cb-107">IsChild Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-ischild-method.md)|<span data-ttu-id="8f5cb-108">현재 프레임이 자식 프레임이 인지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f5cb-108">Determines whether the current frame is a child frame.</span></span>|  
|[<span data-ttu-id="8f5cb-109">IsMatchingParentFrame 메서드</span><span class="sxs-lookup"><span data-stu-id="8f5cb-109">IsMatchingParentFrame Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-ismatchingparentframe-method.md)|<span data-ttu-id="8f5cb-110">지정된 된 프레임의 현재 프레임 부모 인지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f5cb-110">Determines whether the specified frame is the parent of the current frame.</span></span>|  
|[<span data-ttu-id="8f5cb-111">GetStackParameterSize 메서드</span><span class="sxs-lookup"><span data-stu-id="8f5cb-111">GetStackParameterSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-getstackparametersize-method.md)|<span data-ttu-id="8f5cb-112">X86 운영 체제에 대 한 스택에 매개 변수의 누적 크기를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f5cb-112">Returns the cumulative size of the parameters on the stack on x86 operating systems.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8f5cb-113">설명</span><span class="sxs-lookup"><span data-stu-id="8f5cb-113">Remarks</span></span>  
 <span data-ttu-id="8f5cb-114">이 인터페이스는 "ICorDebugNativeFrame" 인터페이스를 논리적으로 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f5cb-114">This interface logically extends the "ICorDebugNativeFrame" interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8f5cb-115">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8f5cb-115">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8f5cb-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8f5cb-116">Requirements</span></span>  
 <span data-ttu-id="8f5cb-117">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8f5cb-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8f5cb-118">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8f5cb-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8f5cb-119">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8f5cb-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8f5cb-120">**.NET framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8f5cb-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f5cb-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8f5cb-121">See Also</span></span>  
    
 [<span data-ttu-id="8f5cb-122">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8f5cb-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="8f5cb-123">디버깅</span><span class="sxs-lookup"><span data-stu-id="8f5cb-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
