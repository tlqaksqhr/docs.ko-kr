---
title: "CeeSectionRelocExtra 공용 구조체"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CeeSectionRelocExtra Union
api_location: mscoree.dll
api_type: COM
f1_keywords: CeeSectionRelocExtra
helpviewer_keywords: CeeSectionRelocExtra union [.NET Framework metadata]
ms.assetid: d9568cf6-7f98-4cd6-ab36-0a2bd509afcc
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c5b584ced996b31be6656082af3f64a19b1f223c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="ceesectionrelocextra-union"></a><span data-ttu-id="d412f-102">CeeSectionRelocExtra 공용 구조체</span><span class="sxs-lookup"><span data-stu-id="d412f-102">CeeSectionRelocExtra Union</span></span>
<span data-ttu-id="d412f-103">사용 되는 주소 오프셋을 나타냅니다는 [ICeeGen](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md) 인터페이스에서 섹션을 재배치 합니다.</span><span class="sxs-lookup"><span data-stu-id="d412f-103">Represents an address offset that is used by the [ICeeGen](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md) interface to relocate a section.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d412f-104">구문</span><span class="sxs-lookup"><span data-stu-id="d412f-104">Syntax</span></span>  
  
```  
typedef union  {  
    USHORT highAdj;  
} CeeSectionRelocExtra;  
```  
  
## <a name="members"></a><span data-ttu-id="d412f-105">멤버</span><span class="sxs-lookup"><span data-stu-id="d412f-105">Members</span></span>  
  
|<span data-ttu-id="d412f-106">멤버</span><span class="sxs-lookup"><span data-stu-id="d412f-106">Member</span></span>|<span data-ttu-id="d412f-107">설명</span><span class="sxs-lookup"><span data-stu-id="d412f-107">Description</span></span>|  
|------------|-----------------|  
|`highAdj`|<span data-ttu-id="d412f-108">섹션에 대 한 상위 주소 조정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d412f-108">The upper address adjustment for the section.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d412f-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d412f-109">Requirements</span></span>  
 <span data-ttu-id="d412f-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d412f-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d412f-111">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="d412f-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d412f-112">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="d412f-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d412f-113">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d412f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d412f-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d412f-114">See Also</span></span>  
 [<span data-ttu-id="d412f-115">메타 데이터 공용 구조체</span><span class="sxs-lookup"><span data-stu-id="d412f-115">Metadata Unions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-unions.md)
