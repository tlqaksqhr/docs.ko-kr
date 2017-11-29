---
title: "디버깅 구조체"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- unmanaged structures [.NET Framework], debugging
- debugging structures [.NET Framework]
- structures [.NET Framework debugging]
ms.assetid: 173ba2c2-ab34-49ae-b6a8-e5c49882bf05
caps.latest.revision: "22"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0293a20f5f735dd38b1d167ebc5057f645fa011a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="debugging-structures"></a><span data-ttu-id="79ef8-102">디버깅 구조체</span><span class="sxs-lookup"><span data-stu-id="79ef8-102">Debugging Structures</span></span>
<span data-ttu-id="79ef8-103">이 섹션에서는 디버깅 API에서 사용하는 관리되지 않는 구조체에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="79ef8-103">This section describes the unmanaged structures that the debugging API uses.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="79ef8-104">단원 내용</span><span class="sxs-lookup"><span data-stu-id="79ef8-104">In This Section</span></span>  
 [<span data-ttu-id="79ef8-105">CLR_DEBUGGING_VERSION 구조체</span><span class="sxs-lookup"><span data-stu-id="79ef8-105">CLR_DEBUGGING_VERSION Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/clr-debugging-version-structure.md)  
 <span data-ttu-id="79ef8-106">디버깅용 CLR(공용 언어 런타임)의 제품 버전을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="79ef8-106">Defines the product version of the common language runtime (CLR) for debugging purposes.</span></span>  
  
 [<span data-ttu-id="79ef8-107">CodeChunkInfo 구조 1</span><span class="sxs-lookup"><span data-stu-id="79ef8-107">CodeChunkInfo Structure1</span></span>](../../../../docs/framework/unmanaged-api/debugging/codechunkinfo-structure.md)  
 <span data-ttu-id="79ef8-108">메모리 내의 단일 코드 청크를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="79ef8-108">Represents a single chunk of code in memory.</span></span>  
  
 [<span data-ttu-id="79ef8-109">CorDebugBlockingObject 구조체</span><span class="sxs-lookup"><span data-stu-id="79ef8-109">CorDebugBlockingObject Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md)  
 <span data-ttu-id="79ef8-110">스레드를 차단하는 개체 및 스레드 차단 이유를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="79ef8-110">Defines an object that is blocking a thread and the reason why the thread is blocked.</span></span>  
  
 [<span data-ttu-id="79ef8-111">CorDebugEHClause 구조</span><span class="sxs-lookup"><span data-stu-id="79ef8-111">CorDebugEHClause Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugehclause-structure.md)  
 <span data-ttu-id="79ef8-112">지정된 IL(중간 언어) 부분에 대한 EH(예외 처리) 절을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="79ef8-112">Represents an exception handling (EH) clause for a given piece of intermediate language (IL).</span></span>  
  
 [<span data-ttu-id="79ef8-113">CorDebugExceptionObjectStackFrame 구조체</span><span class="sxs-lookup"><span data-stu-id="79ef8-113">CorDebugExceptionObjectStackFrame Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md)  
 <span data-ttu-id="79ef8-114">예외 개체의 스택 프레임 정보를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="79ef8-114">Represents stack frame information from an exception object.</span></span>  
  
 [<span data-ttu-id="79ef8-115">CorDebugExceptionObjectStackFrame 구조체</span><span class="sxs-lookup"><span data-stu-id="79ef8-115">CorDebugExceptionObjectStackFrame Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md)  
 <span data-ttu-id="79ef8-116">지도 [!INCLUDE[wrt](../../../../includes/wrt-md.md)] GUID를 해당 [ICorDebugType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-interface.md) 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="79ef8-116">Maps a [!INCLUDE[wrt](../../../../includes/wrt-md.md)] GUID to its corresponding [ICorDebugType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-interface.md) object.</span></span>  
  
 <span data-ttu-id="79ef8-117">COR_ACTIVE_FUNCTION</span><span class="sxs-lookup"><span data-stu-id="79ef8-117">COR_ACTIVE_FUNCTION</span></span>  
 <span data-ttu-id="79ef8-118">스레드 프레임에서 현재 활성 상태인 함수에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="79ef8-118">Contains information about the functions that are currently active in a thread's frames.</span></span>  
  
 [<span data-ttu-id="79ef8-119">COR_ARRAY_LAYOUT 구조체</span><span class="sxs-lookup"><span data-stu-id="79ef8-119">COR_ARRAY_LAYOUT Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/cor-array-layout-structure.md)  
 <span data-ttu-id="79ef8-120">메모리 내 배열 개체의 레이아웃에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="79ef8-120">Provides information about the layout of an array object in memory.</span></span>  
  
 <span data-ttu-id="79ef8-121">COR_DEBUG_IL_TO_NATIVE_MAP</span><span class="sxs-lookup"><span data-stu-id="79ef8-121">COR_DEBUG_IL_TO_NATIVE_MAP</span></span>  
 <span data-ttu-id="79ef8-122">MSIL(Microsoft Intermediate Language) 코드를 네이티브 코드에 매핑하는 데 사용되는 오프셋을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="79ef8-122">Contains the offsets that are used to map Microsoft intermediate language (MSIL) code to native code.</span></span>  
  
 <span data-ttu-id="79ef8-123">COR_DEBUG_STEP_RANGE</span><span class="sxs-lookup"><span data-stu-id="79ef8-123">COR_DEBUG_STEP_RANGE</span></span>  
 <span data-ttu-id="79ef8-124">코드 범위에 대한 오프셋 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="79ef8-124">Contains the offset information for a range of code.</span></span>  
  
 [<span data-ttu-id="79ef8-125">COR_FIELD 구조체</span><span class="sxs-lookup"><span data-stu-id="79ef8-125">COR_FIELD Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md)  
 <span data-ttu-id="79ef8-126">개체의 필드에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="79ef8-126">Provides information about a field in an object.</span></span>  
  
 [<span data-ttu-id="79ef8-127">COR_GC_REFERENCE 구조체</span><span class="sxs-lookup"><span data-stu-id="79ef8-127">COR_GC_REFERENCE Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md)  
 <span data-ttu-id="79ef8-128">가비지 수집할 개체에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="79ef8-128">Contains information about an object that is to be garbage-collected.</span></span>  
  
 [<span data-ttu-id="79ef8-129">COR_HEAPINFO 구조체</span><span class="sxs-lookup"><span data-stu-id="79ef8-129">COR_HEAPINFO Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md)  
 <span data-ttu-id="79ef8-130">가비지 컬렉션 힙에 대한 일반 정보(열거 가능 여부 포함)를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="79ef8-130">Provides general information about the garbage collection heap, including whether it is enumerable.</span></span>  
  
 [<span data-ttu-id="79ef8-131">COR_HEAPOBJECT 구조체</span><span class="sxs-lookup"><span data-stu-id="79ef8-131">COR_HEAPOBJECT Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md)  
 <span data-ttu-id="79ef8-132">관리되는 힙의 개체에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="79ef8-132">Provides information about an object on the managed heap.</span></span>  
  
 <span data-ttu-id="79ef8-133">COR_IL_MAP</span><span class="sxs-lookup"><span data-stu-id="79ef8-133">COR_IL_MAP</span></span>  
 <span data-ttu-id="79ef8-134">함수의 상대 오프셋 변경 내용을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="79ef8-134">Specifies changes in the relative offset of a function.</span></span>  
  
 [<span data-ttu-id="79ef8-135">COR_SEGMENT 구조체</span><span class="sxs-lookup"><span data-stu-id="79ef8-135">COR_SEGMENT Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/cor-segment-structure.md)  
 <span data-ttu-id="79ef8-136">관리되는 힙의 메모리 영역에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="79ef8-136">Contains information about a region of memory in the managed heap.</span></span>  
  
 [<span data-ttu-id="79ef8-137">COR_TYPEID 구조체</span><span class="sxs-lookup"><span data-stu-id="79ef8-137">COR_TYPEID Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md)  
 <span data-ttu-id="79ef8-138">유형 식별자를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="79ef8-138">Contains a type identifier.</span></span>  
  
 [<span data-ttu-id="79ef8-139">COR_TYPE_LAYOUT 구조체</span><span class="sxs-lookup"><span data-stu-id="79ef8-139">COR_TYPE_LAYOUT Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/cor-type-layout-structure.md)  
 <span data-ttu-id="79ef8-140">메모리 내 개체의 레이아웃에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="79ef8-140">Provides information about the layout of an object in memory.</span></span>  
  
 <span data-ttu-id="79ef8-141">COR_VERSION</span><span class="sxs-lookup"><span data-stu-id="79ef8-141">COR_VERSION</span></span>  
 <span data-ttu-id="79ef8-142">공용 언어 런타임의 4부분으로 구성된 표준 버전 번호를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="79ef8-142">Stores the standard four-part version number of the common language runtime.</span></span>  
  
 [<span data-ttu-id="79ef8-143">StackTrace_SimpleContext 구조체</span><span class="sxs-lookup"><span data-stu-id="79ef8-143">StackTrace_SimpleContext Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/stacktrace-simplecontext-structure.md)  
 <span data-ttu-id="79ef8-144">전체 `CONTEXT` 구조체 대신 사용할 수 있는 단순 컨텍스트를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="79ef8-144">Provides a simple context that can be used in place of a full `CONTEXT` structure.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="79ef8-145">관련 단원</span><span class="sxs-lookup"><span data-stu-id="79ef8-145">Related Sections</span></span>  
 [<span data-ttu-id="79ef8-146">디버깅 Coclass</span><span class="sxs-lookup"><span data-stu-id="79ef8-146">Debugging Coclasses</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-coclasses.md)  
  
 [<span data-ttu-id="79ef8-147">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="79ef8-147">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
  
 [<span data-ttu-id="79ef8-148">디버깅 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="79ef8-148">Debugging Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)  
  
 [<span data-ttu-id="79ef8-149">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="79ef8-149">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)  
  
 [<span data-ttu-id="79ef8-150">디버깅</span><span class="sxs-lookup"><span data-stu-id="79ef8-150">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
