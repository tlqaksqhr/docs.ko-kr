---
title: "IReferenceAppId 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IReferenceAppId
api_location: fusion.dll
api_type: COM
f1_keywords: IReferenceAppId
helpviewer_keywords: IReferenceAppId interface [.NET Framework fusion]
ms.assetid: 8eb9e565-f358-43ce-900e-a8f8a5aa6cfb
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: cac4ef63292f1bd342bb94799872b002fdcdf945
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ireferenceappid-interface"></a><span data-ttu-id="754b0-102">IReferenceAppId 인터페이스</span><span class="sxs-lookup"><span data-stu-id="754b0-102">IReferenceAppId Interface</span></span>
<span data-ttu-id="754b0-103">현재 범위에서 응용 프로그램에 대 한 고유 식별자에 대 한 참조를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="754b0-103">Represents a reference to the unique identifier for the application in the current scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="754b0-104">메서드</span><span class="sxs-lookup"><span data-stu-id="754b0-104">Methods</span></span>  
  
|<span data-ttu-id="754b0-105">메서드</span><span class="sxs-lookup"><span data-stu-id="754b0-105">Method</span></span>|<span data-ttu-id="754b0-106">설명</span><span class="sxs-lookup"><span data-stu-id="754b0-106">Description</span></span>|  
|------------|-----------------|  
|`IReferenceAppId::get_CodeBase`|<span data-ttu-id="754b0-107">이 참조 하는 응용 프로그램에 대 한 코드 식별자의 문자열 표현에 대 한 포인터를 가져옵니다 `IReferenceAppId`합니다.</span><span class="sxs-lookup"><span data-stu-id="754b0-107">Gets a pointer to a string representation of the code identifier for the application referenced by this `IReferenceAppId`.</span></span>|  
|`IReferenceAppId::put_CodeBase`|<span data-ttu-id="754b0-108">이 참조 하는 응용 프로그램에 대 한 코드 식별자를 설정 `IReferenceAppId`합니다.</span><span class="sxs-lookup"><span data-stu-id="754b0-108">Sets the code identifier for the application referenced by this `IReferenceAppId`.</span></span>|  
|`IReferenceAppId::EnumAppPath`|<span data-ttu-id="754b0-109">한 인터페이스 포인터를 가져옵니다는 `IEnumReferenceIdentity` 인스턴스를 포함 하는 `IReferenceIdentity` 의 멤버를 나타내는 경우 `IReferenceAppId`합니다.</span><span class="sxs-lookup"><span data-stu-id="754b0-109">Gets an interface pointer to an `IEnumReferenceIdentity` instance containing the `IReferenceIdentity` instances that represent members of this `IReferenceAppId`.</span></span>|  
|`IReferenceAppId::get_SubscriptionId`|<span data-ttu-id="754b0-110">이 구독에 대 한 토큰 식별자의 문자열 표현에 대 한 포인터를 가져옵니다 `IReferenceAppId`합니다.</span><span class="sxs-lookup"><span data-stu-id="754b0-110">Gets a pointer to a string representation of the token identifier for a subscription to this `IReferenceAppId`.</span></span>|  
|`IReferenceAppId::put_SubscriptionId`|<span data-ttu-id="754b0-111">이 구독에 대 한 토큰 식별자를 설정 `IReferenceAppId` 에 지정 된 문자열 값입니다.</span><span class="sxs-lookup"><span data-stu-id="754b0-111">Sets the token identifier for a subscription to this `IReferenceAppId` to the specified string value.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="754b0-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="754b0-112">Requirements</span></span>  
 <span data-ttu-id="754b0-113">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="754b0-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="754b0-114">**헤더:** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="754b0-114">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="754b0-115">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="754b0-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="754b0-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="754b0-116">See Also</span></span>  
 [<span data-ttu-id="754b0-117">Fusion 인터페이스</span><span class="sxs-lookup"><span data-stu-id="754b0-117">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)  
 [<span data-ttu-id="754b0-118">IEnumReferenceIdentity 인터페이스</span><span class="sxs-lookup"><span data-stu-id="754b0-118">IEnumReferenceIdentity Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/ienumreferenceidentity-interface.md)  
 [<span data-ttu-id="754b0-119">IReferenceIdentity 인터페이스</span><span class="sxs-lookup"><span data-stu-id="754b0-119">IReferenceIdentity Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/ireferenceidentity-interface.md)
