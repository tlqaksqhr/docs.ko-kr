---
title: COR_NATIVE_LINK 구조체
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d0d9b8a9a1014d98c51f1471f8203be07f7ff49c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33440959"
---
# <a name="cornativelink-structure"></a><span data-ttu-id="825f7-102">COR_NATIVE_LINK 구조체</span><span class="sxs-lookup"><span data-stu-id="825f7-102">COR_NATIVE_LINK Structure</span></span>
<span data-ttu-id="825f7-103">네이티브 코드를 연결하는 데 사용되는 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="825f7-103">Contains information that is used to link native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="825f7-104">구문</span><span class="sxs-lookup"><span data-stu-id="825f7-104">Syntax</span></span>  
  
```  
typedef struct   
{  
    BYTE        m_linkType;  
    BYTE        m_flags;  
    mdMemberRef m_entryPoint;  
} COR_NATIVE_LINK;  
```  
  
## <a name="members"></a><span data-ttu-id="825f7-105">멤버</span><span class="sxs-lookup"><span data-stu-id="825f7-105">Members</span></span>  
  
|<span data-ttu-id="825f7-106">멤버</span><span class="sxs-lookup"><span data-stu-id="825f7-106">Member</span></span>|<span data-ttu-id="825f7-107">설명</span><span class="sxs-lookup"><span data-stu-id="825f7-107">Description</span></span>|  
|------------|-----------------|  
|`m_linkType`|<span data-ttu-id="825f7-108">네이티브 코드에서 연결 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="825f7-108">The type to be linked in native code.</span></span> <span data-ttu-id="825f7-109">이 값은 중 하나는 [CorNativeLinkType](../../../../docs/framework/unmanaged-api/metadata/cornativelinktype-enumeration.md) 값입니다.</span><span class="sxs-lookup"><span data-stu-id="825f7-109">This value is one of the [CorNativeLinkType](../../../../docs/framework/unmanaged-api/metadata/cornativelinktype-enumeration.md) values.</span></span>|  
|`m_flags`|<span data-ttu-id="825f7-110">네이티브 코드를 연결할 때 링커에서 사용 하는 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="825f7-110">Flags used by the linker when linking native code.</span></span> <span data-ttu-id="825f7-111">이 값은 중 하나는 [CorNativeLinkFlags](../../../../docs/framework/unmanaged-api/metadata/cornativelinkflags-enumeration.md) 값입니다.</span><span class="sxs-lookup"><span data-stu-id="825f7-111">This value is one of the [CorNativeLinkFlags](../../../../docs/framework/unmanaged-api/metadata/cornativelinkflags-enumeration.md) values.</span></span>|  
|`m_entryPoint`|<span data-ttu-id="825f7-112">진입점을 나타내는 MemberRef 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="825f7-112">The MemberRef metadata token that represents the entry point.</span></span> <span data-ttu-id="825f7-113">형식은 `lib:entrypoint`합니다.</span><span class="sxs-lookup"><span data-stu-id="825f7-113">The format is `lib:entrypoint`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="825f7-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="825f7-114">Requirements</span></span>  
 <span data-ttu-id="825f7-115">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="825f7-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="825f7-116">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="825f7-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="825f7-117">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="825f7-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="825f7-118">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="825f7-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="825f7-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="825f7-119">See Also</span></span>  
 [<span data-ttu-id="825f7-120">메타데이터 구조체</span><span class="sxs-lookup"><span data-stu-id="825f7-120">Metadata Structures</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)  
 [<span data-ttu-id="825f7-121">CorNativeLinkType 열거형</span><span class="sxs-lookup"><span data-stu-id="825f7-121">CorNativeLinkType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/metadata/cornativelinktype-enumeration.md)  
 [<span data-ttu-id="825f7-122">CorNativeLinkFlags 열거형</span><span class="sxs-lookup"><span data-stu-id="825f7-122">CorNativeLinkFlags Enumeration</span></span>](../../../../docs/framework/unmanaged-api/metadata/cornativelinkflags-enumeration.md)
