---
title: "CorLocalRefPreservation 열거형"
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
- CorLocalRefPreservation
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorLocalRefPreservation
helpviewer_keywords:
- CorLocalRefPreservation enumeration [.NET Framework metadata]
ms.assetid: 44757163-1228-4213-a4c4-d4de503cc75d
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: c35bbfef62f65a9a401d00f9ae56e2f4c00bb0b2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="corlocalrefpreservation-enumeration"></a><span data-ttu-id="b2e88-102">CorLocalRefPreservation 열거형</span><span class="sxs-lookup"><span data-stu-id="b2e88-102">CorLocalRefPreservation Enumeration</span></span>
<span data-ttu-id="b2e88-103">로컬 참조의 처리에 대한 플래그 값을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="b2e88-103">Contains flag values for the treatment of local references.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2e88-104">구문</span><span class="sxs-lookup"><span data-stu-id="b2e88-104">Syntax</span></span>  
  
```  
typedef enum CorLocalRefPreservation  
{  
    MDPreserveLocalRefsNone     =   0x00000000,  
    MDPreserveLocalTypeRef      =   0x00000001,  
    MDPreserveLocalMemberRef    =   0x00000002  
} CorLocalRefPreservation;  
```  
  
## <a name="members"></a><span data-ttu-id="b2e88-105">멤버</span><span class="sxs-lookup"><span data-stu-id="b2e88-105">Members</span></span>  
  
|<span data-ttu-id="b2e88-106">멤버</span><span class="sxs-lookup"><span data-stu-id="b2e88-106">Member</span></span>|<span data-ttu-id="b2e88-107">설명</span><span class="sxs-lookup"><span data-stu-id="b2e88-107">Description</span></span>|  
|------------|-----------------|  
|`MDPreserveLocalRefsNone`|<span data-ttu-id="b2e88-108">없는 로컬 참조를 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2e88-108">Preserve no local references.</span></span>|  
|`MDPreserveLocalTypeRef`|<span data-ttu-id="b2e88-109">지역 형식 참조를 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2e88-109">Preserve local type references.</span></span>|  
|`MDPreserveLocalMemberRef`|<span data-ttu-id="b2e88-110">로컬 멤버 참조를 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2e88-110">Preserve local member references.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b2e88-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b2e88-111">Requirements</span></span>  
 <span data-ttu-id="b2e88-112">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b2e88-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b2e88-113">**헤더:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="b2e88-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="b2e88-114">**.NET framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b2e88-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2e88-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b2e88-115">See Also</span></span>  
 [<span data-ttu-id="b2e88-116">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="b2e88-116">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
