---
title: "CeeSectionRelocExtra 공용 구조체"
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
- CeeSectionRelocExtra Union
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CeeSectionRelocExtra
helpviewer_keywords:
- CeeSectionRelocExtra union [.NET Framework metadata]
ms.assetid: d9568cf6-7f98-4cd6-ab36-0a2bd509afcc
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 9591967dc70d54bd020414077fcc57b8007db9d2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ceesectionrelocextra-union"></a><span data-ttu-id="84a52-102">CeeSectionRelocExtra 공용 구조체</span><span class="sxs-lookup"><span data-stu-id="84a52-102">CeeSectionRelocExtra Union</span></span>
<span data-ttu-id="84a52-103">사용 되는 주소 오프셋을 나타냅니다는 [ICeeGen](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md) 인터페이스에서 섹션을 재배치 합니다.</span><span class="sxs-lookup"><span data-stu-id="84a52-103">Represents an address offset that is used by the [ICeeGen](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md) interface to relocate a section.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84a52-104">구문</span><span class="sxs-lookup"><span data-stu-id="84a52-104">Syntax</span></span>  
  
```  
typedef union  {  
    USHORT highAdj;  
} CeeSectionRelocExtra;  
```  
  
## <a name="members"></a><span data-ttu-id="84a52-105">멤버</span><span class="sxs-lookup"><span data-stu-id="84a52-105">Members</span></span>  
  
|<span data-ttu-id="84a52-106">멤버</span><span class="sxs-lookup"><span data-stu-id="84a52-106">Member</span></span>|<span data-ttu-id="84a52-107">설명</span><span class="sxs-lookup"><span data-stu-id="84a52-107">Description</span></span>|  
|------------|-----------------|  
|`highAdj`|<span data-ttu-id="84a52-108">섹션에 대 한 상위 주소 조정 합니다.</span><span class="sxs-lookup"><span data-stu-id="84a52-108">The upper address adjustment for the section.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="84a52-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="84a52-109">Requirements</span></span>  
 <span data-ttu-id="84a52-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="84a52-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="84a52-111">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="84a52-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="84a52-112">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="84a52-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="84a52-113">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="84a52-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84a52-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="84a52-114">See Also</span></span>  
 [<span data-ttu-id="84a52-115">메타데이터 공용 구조체</span><span class="sxs-lookup"><span data-stu-id="84a52-115">Metadata Unions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-unions.md)
