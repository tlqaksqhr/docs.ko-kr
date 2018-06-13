---
title: COR_PRF_FUNCTION_ARGUMENT_RANGE 구조체
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 92e3a0a930a4e4b91cac27cbed1b745dea4207a9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33450026"
---
# <a name="corprffunctionargumentrange-structure"></a><span data-ttu-id="02a90-102">COR_PRF_FUNCTION_ARGUMENT_RANGE 구조체</span><span class="sxs-lookup"><span data-stu-id="02a90-102">COR_PRF_FUNCTION_ARGUMENT_RANGE Structure</span></span>
<span data-ttu-id="02a90-103">왼쪽에서 오른쪽 순서로 연속적으로 메모리에 저장한 함수 인수 블록을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="02a90-103">Represents a block of function arguments stored contiguously in left-to-right order in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02a90-104">구문</span><span class="sxs-lookup"><span data-stu-id="02a90-104">Syntax</span></span>  
  
```  
typedef struct _COR_PRF_FUNCTION_ARGUMENT_RANGE {  
    UINT_PTR startAddress;  
    ULONG length;  
} COR_PRF_FUNCTION_ARGUMENT_RANGE;  
```  
  
## <a name="members"></a><span data-ttu-id="02a90-105">멤버</span><span class="sxs-lookup"><span data-stu-id="02a90-105">Members</span></span>  
  
|<span data-ttu-id="02a90-106">멤버</span><span class="sxs-lookup"><span data-stu-id="02a90-106">Members</span></span>|<span data-ttu-id="02a90-107">설명</span><span class="sxs-lookup"><span data-stu-id="02a90-107">Description</span></span>|  
|-------------|-----------------|  
|`startAddress`|<span data-ttu-id="02a90-108">블록의 시작 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="02a90-108">The starting address of the block.</span></span>|  
|`length`|<span data-ttu-id="02a90-109">인접 한 블록의 길이입니다.</span><span class="sxs-lookup"><span data-stu-id="02a90-109">The length of the contiguous block.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="02a90-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="02a90-110">Requirements</span></span>  
 <span data-ttu-id="02a90-111">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="02a90-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="02a90-112">**헤더:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="02a90-112">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="02a90-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="02a90-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="02a90-114">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="02a90-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02a90-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="02a90-115">See Also</span></span>  
 [<span data-ttu-id="02a90-116">프로파일링 구조체</span><span class="sxs-lookup"><span data-stu-id="02a90-116">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
