---
title: IEnumReferenceIdentity 인터페이스
ms.date: 03/30/2017
api_name:
- IEnumReferenceIdentity
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IEnumReferenceIdentity
helpviewer_keywords:
- IEnumReferenceIdentity interface [.NET Framework fusion]
ms.assetid: a17b3155-7216-4e16-8c9f-abce21f549e7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4ebc9fe36955bac8b93ec95e9a55fc8ac1197d9a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33429123"
---
# <a name="ienumreferenceidentity-interface"></a><span data-ttu-id="6b079-102">IEnumReferenceIdentity 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6b079-102">IEnumReferenceIdentity Interface</span></span>
<span data-ttu-id="6b079-103">컬렉션의 열거자 역할을 `IReferenceIdentity` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="6b079-103">Serves as an enumerator for a collection of `IReferenceIdentity` objects.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6b079-104">메서드</span><span class="sxs-lookup"><span data-stu-id="6b079-104">Methods</span></span>  
  
|<span data-ttu-id="6b079-105">메서드</span><span class="sxs-lookup"><span data-stu-id="6b079-105">Method</span></span>|<span data-ttu-id="6b079-106">설명</span><span class="sxs-lookup"><span data-stu-id="6b079-106">Description</span></span>|  
|------------|-----------------|  
|`IEnumReferenceIdentity::Clone`|<span data-ttu-id="6b079-107">새 인터페이스 포인터를 가져옵니다 `IEnumReferenceIdentity` 이와 동일한 멤버를 포함 하는 `IEnumReferenceIdentity`합니다.</span><span class="sxs-lookup"><span data-stu-id="6b079-107">Gets an interface pointer to a new `IEnumReferenceIdentity` that contains the same members as this `IEnumReferenceIdentity`.</span></span>|  
|`IEnumReferenceIdentity::Next`|<span data-ttu-id="6b079-108">지정된 된 수의 가져옵니다 `IReferenceIdentity` 개체를 현재 위치부터 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b079-108">Gets the specified number of `IReferenceIdentity` objects, starting at the current position.</span></span>|  
|`IEnumReferenceIdentity::Reset`|<span data-ttu-id="6b079-109">명령 포인터의 시작으로 이동 `IEnumReferenceIdentity`합니다.</span><span class="sxs-lookup"><span data-stu-id="6b079-109">Moves the instruction pointer to the beginning of this `IEnumReferenceIdentity`.</span></span>|  
|`IEnumReferenceIdentity::Skip`|<span data-ttu-id="6b079-110">명령 포인터 앞으로 요소를 현재 위치부터 지정한 수 만큼 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b079-110">Moves the instruction pointer forward by the specified number of elements, starting at the current position.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6b079-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6b079-111">Requirements</span></span>  
 <span data-ttu-id="6b079-112">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6b079-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6b079-113">**헤더:** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="6b079-113">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="6b079-114">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6b079-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b079-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6b079-115">See Also</span></span>  
 [<span data-ttu-id="6b079-116">Fusion 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6b079-116">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)  
 [<span data-ttu-id="6b079-117">IReferenceIdentity 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6b079-117">IReferenceIdentity Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/ireferenceidentity-interface.md)
