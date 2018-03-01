---
title: "CorSaveSize 열거형"
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
- CorSaveSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorSaveSize
helpviewer_keywords:
- CorSaveSize enumeration [.NET Framework metadata]
ms.assetid: eb95ce39-5688-43c1-a34d-578794b32faa
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3780050285f63fa7334ec5463cd22050836dc136
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="corsavesize-enumeration"></a><span data-ttu-id="6bc57-102">CorSaveSize 열거형</span><span class="sxs-lookup"><span data-stu-id="6bc57-102">CorSaveSize Enumeration</span></span>
<span data-ttu-id="6bc57-103">저장 작업의 크기를 쿼리할 때 필요한 전체 자릿수 수준을 나타내는 값을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="6bc57-103">Contains values indicating the level of precision required when querying for the size of a save operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6bc57-104">구문</span><span class="sxs-lookup"><span data-stu-id="6bc57-104">Syntax</span></span>  
  
```  
typedef enum CorSaveSize {  
    cssAccurate                = 0x0000,   
    cssQuick                   = 0x0001,   
    cssDiscardTransientCAs     = 0x0002  
} CorSaveSize;  
```  
  
## <a name="members"></a><span data-ttu-id="6bc57-105">멤버</span><span class="sxs-lookup"><span data-stu-id="6bc57-105">Members</span></span>  
  
|<span data-ttu-id="6bc57-106">멤버</span><span class="sxs-lookup"><span data-stu-id="6bc57-106">Member</span></span>|<span data-ttu-id="6bc57-107">설명</span><span class="sxs-lookup"><span data-stu-id="6bc57-107">Description</span></span>|  
|------------|-----------------|  
|`cssAccurate`|<span data-ttu-id="6bc57-108">반환 값은 정확 하 게 해야 함을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6bc57-108">Specifies that the return value should be exact.</span></span>|  
|`cssQuick`|<span data-ttu-id="6bc57-109">반환 값을 예상할 수 있는지를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6bc57-109">Specifies that the return value should be estimated.</span></span>|  
|`cssDiscardTransientCAs`|<span data-ttu-id="6bc57-110">삭제 가능한 형식을 제거 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6bc57-110">Specifies that discardable types should be removed.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6bc57-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6bc57-111">Requirements</span></span>  
 <span data-ttu-id="6bc57-112">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6bc57-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6bc57-113">**헤더:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="6bc57-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="6bc57-114">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="6bc57-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6bc57-115">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6bc57-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6bc57-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6bc57-116">See Also</span></span>  
 [<span data-ttu-id="6bc57-117">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="6bc57-117">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
