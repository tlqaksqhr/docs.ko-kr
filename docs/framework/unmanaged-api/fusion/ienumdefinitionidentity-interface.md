---
title: "IEnumDefinitionIdentity 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IEnumDefinitionIdentity
api_location: fusion.dll
api_type: COM
f1_keywords: IEnumDefinitionIdentity
helpviewer_keywords: IEnumDefinitionIdentity interface [.NET Framework fusion]
ms.assetid: 8263e75d-251b-4abc-8a1a-c62884142232
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: bc1f3a46ac7da58fb2c209f833173a1bc6b32ea4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ienumdefinitionidentity-interface"></a><span data-ttu-id="dd4e1-102">IEnumDefinitionIdentity 인터페이스</span><span class="sxs-lookup"><span data-stu-id="dd4e1-102">IEnumDefinitionIdentity Interface</span></span>
<span data-ttu-id="dd4e1-103">컬렉션의 열거자 역할을 `IDefinitionIdentity` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="dd4e1-103">Serves as the enumerator for a collection of `IDefinitionIdentity` objects.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd4e1-104">구문</span><span class="sxs-lookup"><span data-stu-id="dd4e1-104">Syntax</span></span>  
  
```  
IEnumDefinitionIdentity : IUnknown {  
  
    HRESULT Clone (  
        [out] IEnumDefinitionIdentity **ppIEnumDefinitionIdentity  
    );  
  
    HRESULT Next (  
        [in]  ULONG               celt,  
        [out, length_is(celt), size_is(*pceltWritten)]  
              IDefinitionIdentity *rgpIDefinitionIdentity[],  
        [out] ULONG               *pceltWritten  
    );  
  
    HRESULT Reset ();  
  
    HRESULT Skip (  
        [in] ULONG celt  
    );  
  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="dd4e1-105">메서드</span><span class="sxs-lookup"><span data-stu-id="dd4e1-105">Methods</span></span>  
  
|<span data-ttu-id="dd4e1-106">메서드</span><span class="sxs-lookup"><span data-stu-id="dd4e1-106">Method</span></span>|<span data-ttu-id="dd4e1-107">설명</span><span class="sxs-lookup"><span data-stu-id="dd4e1-107">Description</span></span>|  
|------------|-----------------|  
|`IEnumDefinitionIdentity::Clone`|<span data-ttu-id="dd4e1-108">새 인터페이스 포인터를 가져옵니다 `IEnumDefinitionIdentity` 이와 동일한 멤버를 포함 하는 개체 `IEnumDefinitionIdentity`합니다.</span><span class="sxs-lookup"><span data-stu-id="dd4e1-108">Gets an interface pointer to a new `IEnumDefinitionIdentity` object that contains the same members as this `IEnumDefinitionIdentity`.</span></span>|  
|`IEnumDefinitionIdentity::Next`|<span data-ttu-id="dd4e1-109">지정된 된 수의 가져옵니다 `IDefinitionIdentity` 개체를 현재 위치부터 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd4e1-109">Gets the specified number of `IDefinitionIdentity` objects, starting at the current position.</span></span>|  
|`IEnumDefinitionIdentity::Reset`|<span data-ttu-id="dd4e1-110">명령 포인터의 시작으로 이동 `IEnumDefinitionIdentity`합니다.</span><span class="sxs-lookup"><span data-stu-id="dd4e1-110">Moves the instruction pointer to the beginning of this `IEnumDefinitionIdentity`.</span></span>|  
|`IEnumDefinitionIdentity::Skip`|<span data-ttu-id="dd4e1-111">명령 포인터 앞으로 요소를 현재 위치부터 지정한 수 만큼 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd4e1-111">Moves the instruction pointer forward by the specified number of elements, starting at the current position.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="dd4e1-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="dd4e1-112">Requirements</span></span>  
 <span data-ttu-id="dd4e1-113">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="dd4e1-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dd4e1-114">**헤더:** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="dd4e1-114">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="dd4e1-115">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dd4e1-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd4e1-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dd4e1-116">See Also</span></span>  
 [<span data-ttu-id="dd4e1-117">Fusion 인터페이스</span><span class="sxs-lookup"><span data-stu-id="dd4e1-117">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)  
 [<span data-ttu-id="dd4e1-118">IDefinitionIdentity 인터페이스</span><span class="sxs-lookup"><span data-stu-id="dd4e1-118">IDefinitionIdentity Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md)
