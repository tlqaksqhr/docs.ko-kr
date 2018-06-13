---
title: IDefinitionIdentity 인터페이스
ms.date: 03/30/2017
api_name:
- IDefinitionIdentity
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IDefinitionIdentity
helpviewer_keywords:
- IDefinitionIdentity interface [.NET Framework fusion]
ms.assetid: ce5ba888-5fbe-4efd-91cf-f0ff94d8428b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 401c23e44cc473d0a27a82a00343852693cb0f2e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33429347"
---
# <a name="idefinitionidentity-interface"></a><span data-ttu-id="95d62-102">IDefinitionIdentity 인터페이스</span><span class="sxs-lookup"><span data-stu-id="95d62-102">IDefinitionIdentity Interface</span></span>
<span data-ttu-id="95d62-103">현재 범위에서 응용 프로그램을 정의 하는 코드의 고유한 시그니처를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="95d62-103">Represents the unique signature of the code that defines the application in the current scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="95d62-104">메서드</span><span class="sxs-lookup"><span data-stu-id="95d62-104">Methods</span></span>  
  
|<span data-ttu-id="95d62-105">메서드</span><span class="sxs-lookup"><span data-stu-id="95d62-105">Method</span></span>|<span data-ttu-id="95d62-106">설명</span><span class="sxs-lookup"><span data-stu-id="95d62-106">Description</span></span>|  
|------------|-----------------|  
|`IDefinitionIdentity::Clone`|<span data-ttu-id="95d62-107">새 인터페이스 포인터를 가져옵니다 `IDefinitionIdentity` 이 동일한 개체 `IDefinitionIdentity`, 지정 된 특성 변경을 제외 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95d62-107">Gets an interface pointer to a new `IDefinitionIdentity` object that is identical to this `IDefinitionIdentity`, except for the specified attribute changes.</span></span>|  
|`IDefinitionIdentity::EnumAttributes`|<span data-ttu-id="95d62-108">한 인터페이스 포인터를 가져옵니다는 [IEnumIDENTITY_ATTRIBUTE](../../../../docs/framework/unmanaged-api/fusion/ienumidentity-attribute-interface.md) 이 연관 된 특성을 포함 하는 개체 `IDefinitionIdentity`합니다.</span><span class="sxs-lookup"><span data-stu-id="95d62-108">Gets an interface pointer to an [IEnumIDENTITY_ATTRIBUTE](../../../../docs/framework/unmanaged-api/fusion/ienumidentity-attribute-interface.md) object that contains the attributes associated with this `IDefinitionIdentity`.</span></span>|  
|`IDefinitionIdentity::GetAttribute`|<span data-ttu-id="95d62-109">지정된 된 네임 스페이스에서 지정한 이름 가진 특성의 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="95d62-109">Gets the value of the attribute with the specified name in the specified namespace.</span></span>|  
|`IDefinitionIdentity::SetAttribute`|<span data-ttu-id="95d62-110">지정된 된 값으로 지정된 된 네임 스페이스에서 지정된 된 이름을 가진 특성을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="95d62-110">Sets the attribute that has the specified name in the specified namespace to the specified value.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="95d62-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="95d62-111">Requirements</span></span>  
 <span data-ttu-id="95d62-112">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="95d62-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="95d62-113">**헤더:** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="95d62-113">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="95d62-114">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="95d62-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95d62-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="95d62-115">See Also</span></span>  
 [<span data-ttu-id="95d62-116">Fusion 인터페이스</span><span class="sxs-lookup"><span data-stu-id="95d62-116">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
