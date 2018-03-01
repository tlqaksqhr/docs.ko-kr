---
title: "COR_NATIVE_LINK 구조체"
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
- COR_NATIVE_LINK
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COR_NATIVE_LINK
helpviewer_keywords:
- COR_NATIVE_LINK structure [.NET Framework metadata]
ms.assetid: 6ef78d3c-1c69-4141-b687-dcb065b7a74d
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 63e5946e98e7c862a2502a71a02e605a38086618
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="cornativelink-structure"></a><span data-ttu-id="5598b-102">COR_NATIVE_LINK 구조체</span><span class="sxs-lookup"><span data-stu-id="5598b-102">COR_NATIVE_LINK Structure</span></span>
<span data-ttu-id="5598b-103">네이티브 코드를 연결하는 데 사용되는 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="5598b-103">Contains information that is used to link native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5598b-104">구문</span><span class="sxs-lookup"><span data-stu-id="5598b-104">Syntax</span></span>  
  
```  
typedef struct   
{  
    BYTE        m_linkType;  
    BYTE        m_flags;  
    mdMemberRef m_entryPoint;  
} COR_NATIVE_LINK;  
```  
  
## <a name="members"></a><span data-ttu-id="5598b-105">멤버</span><span class="sxs-lookup"><span data-stu-id="5598b-105">Members</span></span>  
  
|<span data-ttu-id="5598b-106">멤버</span><span class="sxs-lookup"><span data-stu-id="5598b-106">Member</span></span>|<span data-ttu-id="5598b-107">설명</span><span class="sxs-lookup"><span data-stu-id="5598b-107">Description</span></span>|  
|------------|-----------------|  
|`m_linkType`|<span data-ttu-id="5598b-108">네이티브 코드에서 연결 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="5598b-108">The type to be linked in native code.</span></span> <span data-ttu-id="5598b-109">이 값은 중 하나는 [CorNativeLinkType](../../../../docs/framework/unmanaged-api/metadata/cornativelinktype-enumeration.md) 값입니다.</span><span class="sxs-lookup"><span data-stu-id="5598b-109">This value is one of the [CorNativeLinkType](../../../../docs/framework/unmanaged-api/metadata/cornativelinktype-enumeration.md) values.</span></span>|  
|`m_flags`|<span data-ttu-id="5598b-110">네이티브 코드를 연결할 때 링커에서 사용 하는 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="5598b-110">Flags used by the linker when linking native code.</span></span> <span data-ttu-id="5598b-111">이 값은 중 하나는 [CorNativeLinkFlags](../../../../docs/framework/unmanaged-api/metadata/cornativelinkflags-enumeration.md) 값입니다.</span><span class="sxs-lookup"><span data-stu-id="5598b-111">This value is one of the [CorNativeLinkFlags](../../../../docs/framework/unmanaged-api/metadata/cornativelinkflags-enumeration.md) values.</span></span>|  
|`m_entryPoint`|<span data-ttu-id="5598b-112">진입점을 나타내는 MemberRef 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="5598b-112">The MemberRef metadata token that represents the entry point.</span></span> <span data-ttu-id="5598b-113">형식은 `lib:entrypoint`합니다.</span><span class="sxs-lookup"><span data-stu-id="5598b-113">The format is `lib:entrypoint`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5598b-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5598b-114">Requirements</span></span>  
 <span data-ttu-id="5598b-115">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5598b-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5598b-116">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="5598b-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5598b-117">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="5598b-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5598b-118">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5598b-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5598b-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5598b-119">See Also</span></span>  
 [<span data-ttu-id="5598b-120">메타데이터 구조체</span><span class="sxs-lookup"><span data-stu-id="5598b-120">Metadata Structures</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)  
 [<span data-ttu-id="5598b-121">CorNativeLinkType 열거형</span><span class="sxs-lookup"><span data-stu-id="5598b-121">CorNativeLinkType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/metadata/cornativelinktype-enumeration.md)  
 [<span data-ttu-id="5598b-122">CorNativeLinkFlags 열거형</span><span class="sxs-lookup"><span data-stu-id="5598b-122">CorNativeLinkFlags Enumeration</span></span>](../../../../docs/framework/unmanaged-api/metadata/cornativelinkflags-enumeration.md)
