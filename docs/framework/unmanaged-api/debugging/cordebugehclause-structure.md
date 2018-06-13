---
title: CorDebugEHClause 구조
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- CorDebugEHClause
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 0e350a1b-6997-46d0-bfc5-962a5011ef43
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 40820a805310786eeb0effd7c5284c1a70a6e70b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33407602"
---
# <a name="cordebugehclause-structure"></a><span data-ttu-id="c52b5-102">CorDebugEHClause 구조</span><span class="sxs-lookup"><span data-stu-id="c52b5-102">CorDebugEHClause Structure</span></span>
<span data-ttu-id="c52b5-103">[.NET Framework 4.5.2 이상 버전에서 지원됨]</span><span class="sxs-lookup"><span data-stu-id="c52b5-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="c52b5-104">지정된 IL(중간 언어) 코드 부분에 대한 EH(예외 처리) 절을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c52b5-104">Represents an exception handling (EH) clause for a given piece of intermediate language (IL) code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c52b5-105">구문</span><span class="sxs-lookup"><span data-stu-id="c52b5-105">Syntax</span></span>  
  
```cpp
typedef struct _CorDebugEHClause {  
   ULONG32 Flags;  
   ULONG32 TryOffset;  
   ULONG32 TryLength;  
   ULONG32 HandlerOffset;  
   ULONG32 HandlerLength;  
   ULONG32 ClassToken;  
   ULONG32 FilterOffset;  
} CorDebugEHClause;  
```  
  
## <a name="members"></a><span data-ttu-id="c52b5-106">멤버</span><span class="sxs-lookup"><span data-stu-id="c52b5-106">Members</span></span>  
  
|<span data-ttu-id="c52b5-107">멤버</span><span class="sxs-lookup"><span data-stu-id="c52b5-107">Member</span></span>|<span data-ttu-id="c52b5-108">설명</span><span class="sxs-lookup"><span data-stu-id="c52b5-108">Description</span></span>|  
|------------|-----------------|  
|`Flags`|<span data-ttu-id="c52b5-109">EH 절의 예외 정보를 설명하는 비트 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="c52b5-109">A bit field that describes the exception information in the EH clause.</span></span> <span data-ttu-id="c52b5-110">자세한 내용은 설명 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c52b5-110">For more information, see the Remarks section.</span></span>|  
|`TryOffset`|<span data-ttu-id="c52b5-111">메서드 본문 시작 지점부터 `try` 블록의 오프셋(바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="c52b5-111">The offset, in bytes, of the `try` block from the start of the method body.</span></span>|  
|`TryLength`|<span data-ttu-id="c52b5-112">`try` 블록의 길이(바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="c52b5-112">The length, in bytes, of the `try` block.</span></span>|  
|`HandlerOffset`|<span data-ttu-id="c52b5-113">이 `try` 블록의 처리기 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="c52b5-113">The location of the handler for this `try` block.</span></span>|  
|`HandlerLength`|<span data-ttu-id="c52b5-114">처리기 코드의 크기(바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="c52b5-114">The size of the handler code in bytes.</span></span>|  
|`ClassToken`|<span data-ttu-id="c52b5-115">형식 기반 예외 처리기의 메타데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="c52b5-115">The metadata token for a type-based exception handler.</span></span>|  
|`FilterOffset`|<span data-ttu-id="c52b5-116">필터 기반 예외 처리기에 대한 메서드 본문 시작 지점부터의 오프셋(바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="c52b5-116">The offset, in bytes, from the start of the method body for a filter-based exception handler.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c52b5-117">설명</span><span class="sxs-lookup"><span data-stu-id="c52b5-117">Remarks</span></span>  
 <span data-ttu-id="c52b5-118">배열을 `CoreDebugEHClause` 값에서 반환 되는 [GetEHClauses](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-getehclauses-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="c52b5-118">An array of `CoreDebugEHClause` values is returned by the [GetEHClauses](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-getehclauses-method.md) method.</span></span>  
  
 <span data-ttu-id="c52b5-119">EH 절 정보는 CLI 사양을 통해 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="c52b5-119">The EH clause information is defined by the CLI specification.</span></span> <span data-ttu-id="c52b5-120">자세한 내용은 참조 [표준 ecma-355: CLI 공용 언어 인프라 (), 6 판](http://www.ecma-international.org/publications/standards/Ecma-335.htm)합니다.</span><span class="sxs-lookup"><span data-stu-id="c52b5-120">For more information, see [Standard ECMA-355: Common Language Infrastructure (CLI), 6th Edition](http://www.ecma-international.org/publications/standards/Ecma-335.htm).</span></span>  
  
 <span data-ttu-id="c52b5-121">`flags` 필드는 다음 플래그를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c52b5-121">The `flags` field can contain the following flags.</span></span> <span data-ttu-id="c52b5-122">이러한 플래그는 CorDebug.idl 또는 CorDebug.h에서 정의되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c52b5-122">Note that they are not defined in CorDebug.idl or CorDebug.h.</span></span>  
  
|<span data-ttu-id="c52b5-123">플래그</span><span class="sxs-lookup"><span data-stu-id="c52b5-123">Flag</span></span>|<span data-ttu-id="c52b5-124">값</span><span class="sxs-lookup"><span data-stu-id="c52b5-124">Value</span></span>|<span data-ttu-id="c52b5-125">설명</span><span class="sxs-lookup"><span data-stu-id="c52b5-125">Description</span></span>|  
|----------|-----------|-----------------|  
|`COR_ILEXCEPTION_CLAUSE_EXCEPTION`|<span data-ttu-id="c52b5-126">0x00000000</span><span class="sxs-lookup"><span data-stu-id="c52b5-126">0x00000000</span></span>|<span data-ttu-id="c52b5-127">형식이 지정된 예외 절입니다.</span><span class="sxs-lookup"><span data-stu-id="c52b5-127">A typed exception clause.</span></span>|  
|`COR_ILEXCEPTION_CLAUSE_FILTER`|<span data-ttu-id="c52b5-128">0x00000001</span><span class="sxs-lookup"><span data-stu-id="c52b5-128">0x00000001</span></span>|<span data-ttu-id="c52b5-129">예외 필터 및 처리기 절입니다.</span><span class="sxs-lookup"><span data-stu-id="c52b5-129">An exception filter and handler clause.</span></span>|  
|`COR_ILEXCEPTION_CLAUSE_FINALLY`|<span data-ttu-id="c52b5-130">0x00000002</span><span class="sxs-lookup"><span data-stu-id="c52b5-130">0x00000002</span></span>|<span data-ttu-id="c52b5-131">`finally` 절입니다.</span><span class="sxs-lookup"><span data-stu-id="c52b5-131">A `finally` clause.</span></span>|  
|`COR_ILEXCEPTION_CLAUSE_FAULT`|<span data-ttu-id="c52b5-132">0x00000004</span><span class="sxs-lookup"><span data-stu-id="c52b5-132">0x00000004</span></span>|<span data-ttu-id="c52b5-133">fault 절, 즉 예외가 throw될 때만 호출되는 `finally` 절입니다.</span><span class="sxs-lookup"><span data-stu-id="c52b5-133">A fault clause (a `finally` clause that is called only when an exception is thrown).</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c52b5-134">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c52b5-134">Requirements</span></span>  
 <span data-ttu-id="c52b5-135">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c52b5-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c52b5-136">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c52b5-136">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c52b5-137">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c52b5-137">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c52b5-138">**.NET framework 버전:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c52b5-138">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c52b5-139">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c52b5-139">See Also</span></span>  
 [<span data-ttu-id="c52b5-140">GetEHClauses 메서드</span><span class="sxs-lookup"><span data-stu-id="c52b5-140">GetEHClauses Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-getehclauses-method.md)  
 [<span data-ttu-id="c52b5-141">디버깅 구조체</span><span class="sxs-lookup"><span data-stu-id="c52b5-141">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
