---
title: ICorDebugILFrame2 Interface1
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame2
helpviewer_keywords:
- ICorDebugILFrame2 interface [.NET Framework debugging]
ms.assetid: f94b9d53-d8f8-4424-a95e-53a1bfd26e4a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ccb39609b37aff09ac7890df562d6c08e3c3c159
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33412437"
---
# <a name="icordebugilframe2-interface1"></a><span data-ttu-id="58dcf-102">ICorDebugILFrame2 Interface1</span><span class="sxs-lookup"><span data-stu-id="58dcf-102">ICorDebugILFrame2 Interface1</span></span>
<span data-ttu-id="58dcf-103">ICorDebugILFrame 인터페이스 논리적으로 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="58dcf-103">A logical extension of the ICorDebugILFrame interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="58dcf-104">메서드</span><span class="sxs-lookup"><span data-stu-id="58dcf-104">Methods</span></span>  
  
|<span data-ttu-id="58dcf-105">메서드</span><span class="sxs-lookup"><span data-stu-id="58dcf-105">Method</span></span>|<span data-ttu-id="58dcf-106">설명</span><span class="sxs-lookup"><span data-stu-id="58dcf-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="58dcf-107">EnumerateTypeParameters 메서드</span><span class="sxs-lookup"><span data-stu-id="58dcf-107">EnumerateTypeParameters Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-enumeratetypeparameters-method.md)|<span data-ttu-id="58dcf-108">포함 된 ICorDebugTypeEnum 개체를 가져옵니다는 <xref:System.Type> 이 프레임에서 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="58dcf-108">Gets an ICorDebugTypeEnum object that contains the <xref:System.Type> parameters in this frame.</span></span>|  
|[<span data-ttu-id="58dcf-109">RemapFunction 메서드</span><span class="sxs-lookup"><span data-stu-id="58dcf-109">RemapFunction Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-remapfunction-method.md)|<span data-ttu-id="58dcf-110">새 MSIL 오프셋을 지정 하 여 편집된 된 함수를 다시 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="58dcf-110">Remaps an edited function by specifying the new MSIL offset.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="58dcf-111">설명</span><span class="sxs-lookup"><span data-stu-id="58dcf-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="58dcf-112">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="58dcf-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="58dcf-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="58dcf-113">Requirements</span></span>  
 <span data-ttu-id="58dcf-114">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="58dcf-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="58dcf-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="58dcf-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="58dcf-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="58dcf-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="58dcf-117">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="58dcf-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58dcf-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="58dcf-118">See Also</span></span>  
 [<span data-ttu-id="58dcf-119">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="58dcf-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
