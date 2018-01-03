---
title: "CodeChunkInfo 구조 1"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CodeChunkInfo
api_location: mscordbi.dll
api_type: COM
f1_keywords: CodeChunkInfo
helpviewer_keywords: CodeChunkInfo structure [.NET Framework debugging]
ms.assetid: 0f482454-8517-48de-ba7a-d7aedab13bb5
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d7b3b858d645f01f58ba0b67465b22dd05282656
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="codechunkinfo-structure1"></a><span data-ttu-id="b200b-102">CodeChunkInfo 구조 1</span><span class="sxs-lookup"><span data-stu-id="b200b-102">CodeChunkInfo Structure1</span></span>
<span data-ttu-id="b200b-103">메모리 내의 단일 코드 청크를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b200b-103">Represents a single chunk of code in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b200b-104">구문</span><span class="sxs-lookup"><span data-stu-id="b200b-104">Syntax</span></span>  
  
```  
typedef struct _CodeChunkInfo {  
    CORDB_ADDRESS startAddr;  
    ULONG32       length;  
} CodeChunkInfo;  
```  
  
## <a name="members"></a><span data-ttu-id="b200b-105">멤버</span><span class="sxs-lookup"><span data-stu-id="b200b-105">Members</span></span>  
  
|<span data-ttu-id="b200b-106">멤버</span><span class="sxs-lookup"><span data-stu-id="b200b-106">Member</span></span>|<span data-ttu-id="b200b-107">설명</span><span class="sxs-lookup"><span data-stu-id="b200b-107">Description</span></span>|  
|------------|-----------------|  
|`startAddr`|<span data-ttu-id="b200b-108">A `CORDB_ADDRESS` 청크의 시작 주소를 지정 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="b200b-108">A `CORDB_ADDRESS` value that specifies the starting address of the chunk.</span></span>|  
|`length`|<span data-ttu-id="b200b-109">바이트 청크의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="b200b-109">The size, in bytes, of the chunk.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b200b-110">설명</span><span class="sxs-lookup"><span data-stu-id="b200b-110">Remarks</span></span>  
 <span data-ttu-id="b200b-111">단일 코드 청크는 함수 같은 코드 개체에 포함 된 네이티브 코드의 영역입니다.</span><span class="sxs-lookup"><span data-stu-id="b200b-111">The single chunk of code is a region of native code that is part of a code object such as a function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b200b-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b200b-112">Requirements</span></span>  
 <span data-ttu-id="b200b-113">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b200b-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b200b-114">**헤더:** CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="b200b-114">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="b200b-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b200b-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b200b-116">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b200b-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b200b-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b200b-117">See Also</span></span>  
 [<span data-ttu-id="b200b-118">GetCodeChunks 메서드</span><span class="sxs-lookup"><span data-stu-id="b200b-118">GetCodeChunks Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md)  
 [<span data-ttu-id="b200b-119">디버깅 구조체</span><span class="sxs-lookup"><span data-stu-id="b200b-119">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [<span data-ttu-id="b200b-120">디버깅</span><span class="sxs-lookup"><span data-stu-id="b200b-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
