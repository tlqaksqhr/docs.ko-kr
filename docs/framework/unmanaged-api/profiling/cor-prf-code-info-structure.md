---
title: "COR_PRF_CODE_INFO 구조체"
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
- COR_PRF_CODE_INFO
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_CODE_INFO
helpviewer_keywords:
- COR_PRF_CODE_INFO structure [.NET Framework profiling]
ms.assetid: cf30e27c-1f7e-43a2-ba1e-01e4137301db
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 173ebcd2b97b3b542a8ea96338a9c6b59b5dc6d6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="corprfcodeinfo-structure"></a><span data-ttu-id="086be-102">COR_PRF_CODE_INFO 구조체</span><span class="sxs-lookup"><span data-stu-id="086be-102">COR_PRF_CODE_INFO Structure</span></span>
<span data-ttu-id="086be-103">메모리 내에 저장된 연속하는 네이티브 코드 블록 하나를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="086be-103">Represents one contiguous block of native code stored in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="086be-104">구문</span><span class="sxs-lookup"><span data-stu-id="086be-104">Syntax</span></span>  
  
```  
typedef struct _COR_PRF_CODE_INFO {  
    UINT_PTR startAddress;  
    SIZE_T size;  
} COR_PRF_CODE_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="086be-105">멤버</span><span class="sxs-lookup"><span data-stu-id="086be-105">Members</span></span>  
  
|<span data-ttu-id="086be-106">멤버</span><span class="sxs-lookup"><span data-stu-id="086be-106">Member</span></span>|<span data-ttu-id="086be-107">설명</span><span class="sxs-lookup"><span data-stu-id="086be-107">Description</span></span>|  
|------------|-----------------|  
|`startAddress`|<span data-ttu-id="086be-108">코드의 연속 블록의 시작 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="086be-108">The starting address of the contiguous block of code.</span></span>|  
|`size`|<span data-ttu-id="086be-109">블록의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="086be-109">The size of the block.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="086be-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="086be-110">Requirements</span></span>  
 <span data-ttu-id="086be-111">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="086be-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="086be-112">**헤더:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="086be-112">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="086be-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="086be-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="086be-114">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="086be-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="086be-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="086be-115">See Also</span></span>  
 [<span data-ttu-id="086be-116">프로파일링 구조체</span><span class="sxs-lookup"><span data-stu-id="086be-116">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
