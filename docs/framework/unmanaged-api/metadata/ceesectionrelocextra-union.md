---
title: CeeSectionRelocExtra 공용 구조체
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c7634ec801a30aa7ba07954c1df0c3d37ec279eb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33440303"
---
# <a name="ceesectionrelocextra-union"></a><span data-ttu-id="7cef2-102">CeeSectionRelocExtra 공용 구조체</span><span class="sxs-lookup"><span data-stu-id="7cef2-102">CeeSectionRelocExtra Union</span></span>
<span data-ttu-id="7cef2-103">사용 되는 주소 오프셋을 나타냅니다는 [ICeeGen](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md) 인터페이스에서 섹션을 재배치 합니다.</span><span class="sxs-lookup"><span data-stu-id="7cef2-103">Represents an address offset that is used by the [ICeeGen](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md) interface to relocate a section.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7cef2-104">구문</span><span class="sxs-lookup"><span data-stu-id="7cef2-104">Syntax</span></span>  
  
```  
typedef union  {  
    USHORT highAdj;  
} CeeSectionRelocExtra;  
```  
  
## <a name="members"></a><span data-ttu-id="7cef2-105">멤버</span><span class="sxs-lookup"><span data-stu-id="7cef2-105">Members</span></span>  
  
|<span data-ttu-id="7cef2-106">멤버</span><span class="sxs-lookup"><span data-stu-id="7cef2-106">Member</span></span>|<span data-ttu-id="7cef2-107">설명</span><span class="sxs-lookup"><span data-stu-id="7cef2-107">Description</span></span>|  
|------------|-----------------|  
|`highAdj`|<span data-ttu-id="7cef2-108">섹션에 대 한 상위 주소 조정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7cef2-108">The upper address adjustment for the section.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7cef2-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7cef2-109">Requirements</span></span>  
 <span data-ttu-id="7cef2-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7cef2-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7cef2-111">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="7cef2-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7cef2-112">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="7cef2-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7cef2-113">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7cef2-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7cef2-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7cef2-114">See Also</span></span>  
 [<span data-ttu-id="7cef2-115">메타데이터 공용 구조체</span><span class="sxs-lookup"><span data-stu-id="7cef2-115">Metadata Unions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-unions.md)
