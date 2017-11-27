---
title: "COR_PRF_FUNCTION_ARGUMENT_RANGE 구조체"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_PRF_FUNCTION_ARGUMENT_RANGE
api_location: mscorwks.dll
api_type: COM
f1_keywords: COR_PRF_FUNCTION_ARGUMENT_RANGE
helpviewer_keywords: COR_PRF_FUNCTION_ARGUMENT_RANGE structure [.NET Framework profiling'
ms.assetid: 9f469eac-ac66-419b-8668-fe705bc1a51f
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 0c0dd9cac695d892c07f33728c22bd35102c4389
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="corprffunctionargumentrange-structure"></a><span data-ttu-id="943ad-102">COR_PRF_FUNCTION_ARGUMENT_RANGE 구조체</span><span class="sxs-lookup"><span data-stu-id="943ad-102">COR_PRF_FUNCTION_ARGUMENT_RANGE Structure</span></span>
<span data-ttu-id="943ad-103">왼쪽에서 오른쪽 순서로 연속적으로 메모리에 저장한 함수 인수 블록을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="943ad-103">Represents a block of function arguments stored contiguously in left-to-right order in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="943ad-104">구문</span><span class="sxs-lookup"><span data-stu-id="943ad-104">Syntax</span></span>  
  
```  
typedef struct _COR_PRF_FUNCTION_ARGUMENT_RANGE {  
    UINT_PTR startAddress;  
    ULONG length;  
} COR_PRF_FUNCTION_ARGUMENT_RANGE;  
```  
  
## <a name="members"></a><span data-ttu-id="943ad-105">멤버</span><span class="sxs-lookup"><span data-stu-id="943ad-105">Members</span></span>  
  
|<span data-ttu-id="943ad-106">멤버</span><span class="sxs-lookup"><span data-stu-id="943ad-106">Members</span></span>|<span data-ttu-id="943ad-107">설명</span><span class="sxs-lookup"><span data-stu-id="943ad-107">Description</span></span>|  
|-------------|-----------------|  
|`startAddress`|<span data-ttu-id="943ad-108">블록의 시작 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="943ad-108">The starting address of the block.</span></span>|  
|`length`|<span data-ttu-id="943ad-109">인접 한 블록의 길이입니다.</span><span class="sxs-lookup"><span data-stu-id="943ad-109">The length of the contiguous block.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="943ad-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="943ad-110">Requirements</span></span>  
 <span data-ttu-id="943ad-111">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="943ad-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="943ad-112">**헤더:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="943ad-112">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="943ad-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="943ad-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="943ad-114">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="943ad-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="943ad-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="943ad-115">See Also</span></span>  
 [<span data-ttu-id="943ad-116">프로 파일링 구조체</span><span class="sxs-lookup"><span data-stu-id="943ad-116">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
