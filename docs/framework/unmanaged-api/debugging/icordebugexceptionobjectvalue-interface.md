---
title: ICorDebugExceptionObjectValue 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugExceptionObjectValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugExceptionObjectValue
helpviewer_keywords:
- ICorDebugExceptionObjectValue interface [.NET Framework debugging]
ms.assetid: 43416dd5-8892-4106-9f59-f9143b19ddb4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d6805b7b49f76b80161aef5051fe3c284192f582
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33413776"
---
# <a name="icordebugexceptionobjectvalue-interface"></a><span data-ttu-id="e43e7-102">ICorDebugExceptionObjectValue 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e43e7-102">ICorDebugExceptionObjectValue Interface</span></span>
<span data-ttu-id="e43e7-103">관리 되는 예외 개체에서 스택 추적 정보를 제공 하는 "ICorDebugObjectValue" 인터페이스를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="e43e7-103">Extends the "ICorDebugObjectValue" interface to provide stack trace information from a managed exception object.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e43e7-104">메서드</span><span class="sxs-lookup"><span data-stu-id="e43e7-104">Methods</span></span>  
  
|<span data-ttu-id="e43e7-105">메서드</span><span class="sxs-lookup"><span data-stu-id="e43e7-105">Method</span></span>|<span data-ttu-id="e43e7-106">설명</span><span class="sxs-lookup"><span data-stu-id="e43e7-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e43e7-107">EnumerateExceptionCallStack 메서드</span><span class="sxs-lookup"><span data-stu-id="e43e7-107">EnumerateExceptionCallStack Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectvalue-enumerateexceptioncallstack-method.md)|<span data-ttu-id="e43e7-108">예외 개체에 포함 된 호출 스택에 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e43e7-108">Gets an enumerator to the call stack embedded in an exception object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e43e7-109">설명</span><span class="sxs-lookup"><span data-stu-id="e43e7-109">Remarks</span></span>  
 <span data-ttu-id="e43e7-110">에 대 한 호출 `QueryInterface` 에서 파생 되는 관리 되는 개체에 대 한 성공할 <xref:System.Exception?displayProperty=nameWithType>합니다.</span><span class="sxs-lookup"><span data-stu-id="e43e7-110">The call to `QueryInterface` will succeed for managed objects that derive from <xref:System.Exception?displayProperty=nameWithType>.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e43e7-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e43e7-111">Requirements</span></span>  
 <span data-ttu-id="e43e7-112">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e43e7-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e43e7-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e43e7-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e43e7-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e43e7-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e43e7-115">**.NET framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e43e7-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e43e7-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e43e7-116">See Also</span></span>  
 [<span data-ttu-id="e43e7-117">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e43e7-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="e43e7-118">디버깅</span><span class="sxs-lookup"><span data-stu-id="e43e7-118">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)  
 
