---
title: IDENTITY_ATTRIBUTE 구조체
ms.date: 03/30/2017
api_name:
- IDENTITY_ATTRIBUTE
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IDENTITY_ATTRIBUTE
helpviewer_keywords:
- IDENTITY_ATTRIBUTE structure [.NET Framework fusion]
ms.assetid: 1ee7c434-9681-4fa8-badd-652cb1a9742b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f716ff35ae0cd3d2a53c55756b8957e54fa355c6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33431537"
---
# <a name="identityattribute-structure"></a><span data-ttu-id="5a903-102">IDENTITY_ATTRIBUTE 구조체</span><span class="sxs-lookup"><span data-stu-id="5a903-102">IDENTITY_ATTRIBUTE Structure</span></span>
<span data-ttu-id="5a903-103">에 대 한 메타 데이터 특성 정보를 포함 한 [IDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md) 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="5a903-103">Contains metadata attribute information about an [IDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a903-104">구문</span><span class="sxs-lookup"><span data-stu-id="5a903-104">Syntax</span></span>  
  
```  
typedef struct _IDENTITY_ATTRIBUTE {  
    LPCWSTR  pszNamespace;  
    LPCWSTR  pszName;  
    LPCWSTR  pszValue;  
} IDENTITY_ATTRIBUTE;  
```  
  
## <a name="members"></a><span data-ttu-id="5a903-105">멤버</span><span class="sxs-lookup"><span data-stu-id="5a903-105">Members</span></span>  
  
|<span data-ttu-id="5a903-106">멤버</span><span class="sxs-lookup"><span data-stu-id="5a903-106">Member</span></span>|<span data-ttu-id="5a903-107">설명</span><span class="sxs-lookup"><span data-stu-id="5a903-107">Description</span></span>|  
|------------|-----------------|  
|`pszNamespace`|<span data-ttu-id="5a903-108">네임 스페이스를 포함 된 null로 끝나는 문자열에 대 한 포인터의 특성이입니다.</span><span class="sxs-lookup"><span data-stu-id="5a903-108">A pointer to a null-terminated character string that contains the namespace the attribute is in.</span></span>|  
|`pszName`|<span data-ttu-id="5a903-109">특성의 이름을 포함 하는 null로 끝나는 문자열에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="5a903-109">A pointer to a null-terminated character string that contains the name of the attribute.</span></span>|  
|`pszValue`|<span data-ttu-id="5a903-110">특성의 값이 포함 된 null로 끝나는 문자열에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="5a903-110">A pointer to a null-terminated character string that contains the value of the attribute.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5a903-111">설명</span><span class="sxs-lookup"><span data-stu-id="5a903-111">Remarks</span></span>  
 <span data-ttu-id="5a903-112">`IDENTITY_ATTRIBUTE` 구조 null로 끝나는 문자열에 대 한 세 포인터를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a903-112">The `IDENTITY_ATTRIBUTE` structure contains three pointers to null-terminated character strings.</span></span> <span data-ttu-id="5a903-113">이러한 세 가지 문자열 특성이 두 개에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a903-113">These three strings describe one attribute.</span></span>  
  
 <span data-ttu-id="5a903-114">인스턴스는 `IDENTITY_ATTRIBUTE` 구조는의 인스턴스에 연결 되어 있는 [IDENTITY_ATTRIBUTE_BLOB](../../../../docs/framework/unmanaged-api/fusion/identity-attribute-blob-structure.md) 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="5a903-114">An instance of an `IDENTITY_ATTRIBUTE` structure is associated with an instance of an [IDENTITY_ATTRIBUTE_BLOB](../../../../docs/framework/unmanaged-api/fusion/identity-attribute-blob-structure.md) structure.</span></span> <span data-ttu-id="5a903-115">`IDENTITY_ATTRIBUTE` 실제 문자열 및 해당 구조에 포함 된 `IDENTITY_ATTRIBUTE_BLOB` 구조에 나열 된 세 개의 문자열에 대 한 오프셋이 나열 된 `IDENTITY_ATTRIBUTE` 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="5a903-115">The `IDENTITY_ATTRIBUTE` structure contains the actual strings, and the corresponding `IDENTITY_ATTRIBUTE_BLOB` structure lists the offsets to the three strings listed in the `IDENTITY_ATTRIBUTE` structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5a903-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5a903-116">Requirements</span></span>  
 <span data-ttu-id="5a903-117">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5a903-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5a903-118">**헤더:** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="5a903-118">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="5a903-119">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5a903-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a903-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5a903-120">See Also</span></span>  
 [<span data-ttu-id="5a903-121">IDefinitionIdentity 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5a903-121">IDefinitionIdentity Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md)  
 [<span data-ttu-id="5a903-122">IDENTITY_ATTRIBUTE_BLOB 구조체</span><span class="sxs-lookup"><span data-stu-id="5a903-122">IDENTITY_ATTRIBUTE_BLOB Structure</span></span>](../../../../docs/framework/unmanaged-api/fusion/identity-attribute-blob-structure.md)  
 [<span data-ttu-id="5a903-123">Fusion 구조체</span><span class="sxs-lookup"><span data-stu-id="5a903-123">Fusion Structures</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-structures.md)
