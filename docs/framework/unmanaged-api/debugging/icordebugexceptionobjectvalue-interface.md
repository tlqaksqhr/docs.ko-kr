---
title: "ICorDebugExceptionObjectValue 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugExceptionObjectValue
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugExceptionObjectValue
helpviewer_keywords: ICorDebugExceptionObjectValue interface [.NET Framework debugging]
ms.assetid: 43416dd5-8892-4106-9f59-f9143b19ddb4
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 47733a6af18d42d0d9db1e50cf21646289ef1443
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugexceptionobjectvalue-interface"></a><span data-ttu-id="a3d70-102">ICorDebugExceptionObjectValue 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a3d70-102">ICorDebugExceptionObjectValue Interface</span></span>
<span data-ttu-id="a3d70-103">관리 되는 예외 개체에서 스택 추적 정보를 제공 하는 "ICorDebugObjectValue" 인터페이스를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3d70-103">Extends the "ICorDebugObjectValue" interface to provide stack trace information from a managed exception object.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a3d70-104">메서드</span><span class="sxs-lookup"><span data-stu-id="a3d70-104">Methods</span></span>  
  
|<span data-ttu-id="a3d70-105">메서드</span><span class="sxs-lookup"><span data-stu-id="a3d70-105">Method</span></span>|<span data-ttu-id="a3d70-106">설명</span><span class="sxs-lookup"><span data-stu-id="a3d70-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a3d70-107">EnumerateExceptionCallStack 메서드</span><span class="sxs-lookup"><span data-stu-id="a3d70-107">EnumerateExceptionCallStack Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectvalue-enumerateexceptioncallstack-method.md)|<span data-ttu-id="a3d70-108">예외 개체에 포함 된 호출 스택에 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a3d70-108">Gets an enumerator to the call stack embedded in an exception object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a3d70-109">설명</span><span class="sxs-lookup"><span data-stu-id="a3d70-109">Remarks</span></span>  
 <span data-ttu-id="a3d70-110">에 대 한 호출 `QueryInterface` 에서 파생 되는 관리 되는 개체에 대 한 성공할 <xref:System.Exception?displayProperty=nameWithType>합니다.</span><span class="sxs-lookup"><span data-stu-id="a3d70-110">The call to `QueryInterface` will succeed for managed objects that derive from <xref:System.Exception?displayProperty=nameWithType>.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a3d70-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a3d70-111">Requirements</span></span>  
 <span data-ttu-id="a3d70-112">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a3d70-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a3d70-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a3d70-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a3d70-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a3d70-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a3d70-115">**.NET framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a3d70-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3d70-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a3d70-116">See Also</span></span>  
 [<span data-ttu-id="a3d70-117">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a3d70-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="a3d70-118">디버깅</span><span class="sxs-lookup"><span data-stu-id="a3d70-118">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)  
 
