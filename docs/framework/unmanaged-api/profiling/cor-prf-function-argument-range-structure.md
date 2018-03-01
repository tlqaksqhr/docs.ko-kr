---
title: "COR_PRF_FUNCTION_ARGUMENT_RANGE 구조체"
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
- COR_PRF_FUNCTION_ARGUMENT_RANGE
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_FUNCTION_ARGUMENT_RANGE
helpviewer_keywords:
- COR_PRF_FUNCTION_ARGUMENT_RANGE structure [.NET Framework profiling'
ms.assetid: 9f469eac-ac66-419b-8668-fe705bc1a51f
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 7f61d23fc3ee3c6c8adb46c0deecdd72d155ae65
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="corprffunctionargumentrange-structure"></a><span data-ttu-id="486bd-102">COR_PRF_FUNCTION_ARGUMENT_RANGE 구조체</span><span class="sxs-lookup"><span data-stu-id="486bd-102">COR_PRF_FUNCTION_ARGUMENT_RANGE Structure</span></span>
<span data-ttu-id="486bd-103">왼쪽에서 오른쪽 순서로 연속적으로 메모리에 저장한 함수 인수 블록을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="486bd-103">Represents a block of function arguments stored contiguously in left-to-right order in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="486bd-104">구문</span><span class="sxs-lookup"><span data-stu-id="486bd-104">Syntax</span></span>  
  
```  
typedef struct _COR_PRF_FUNCTION_ARGUMENT_RANGE {  
    UINT_PTR startAddress;  
    ULONG length;  
} COR_PRF_FUNCTION_ARGUMENT_RANGE;  
```  
  
## <a name="members"></a><span data-ttu-id="486bd-105">멤버</span><span class="sxs-lookup"><span data-stu-id="486bd-105">Members</span></span>  
  
|<span data-ttu-id="486bd-106">멤버</span><span class="sxs-lookup"><span data-stu-id="486bd-106">Members</span></span>|<span data-ttu-id="486bd-107">설명</span><span class="sxs-lookup"><span data-stu-id="486bd-107">Description</span></span>|  
|-------------|-----------------|  
|`startAddress`|<span data-ttu-id="486bd-108">블록의 시작 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="486bd-108">The starting address of the block.</span></span>|  
|`length`|<span data-ttu-id="486bd-109">인접 한 블록의 길이입니다.</span><span class="sxs-lookup"><span data-stu-id="486bd-109">The length of the contiguous block.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="486bd-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="486bd-110">Requirements</span></span>  
 <span data-ttu-id="486bd-111">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="486bd-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="486bd-112">**헤더:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="486bd-112">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="486bd-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="486bd-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="486bd-114">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="486bd-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="486bd-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="486bd-115">See Also</span></span>  
 [<span data-ttu-id="486bd-116">프로파일링 구조체</span><span class="sxs-lookup"><span data-stu-id="486bd-116">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
