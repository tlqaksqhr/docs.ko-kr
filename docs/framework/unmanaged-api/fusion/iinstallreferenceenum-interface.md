---
title: "IInstallReferenceEnum 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IInstallReferenceEnum
api_location: fusion.dll
api_type: COM
f1_keywords: IInstallReferenceEnum
helpviewer_keywords: IInstallReferenceEnum interface [.NET Framework fusion]
ms.assetid: 2863b33b-a541-462c-bbe8-702a2832898e
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2f1a80d1d79fce952a7071abd5e435604824d00e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="iinstallreferenceenum-interface"></a><span data-ttu-id="f6ce0-102">IInstallReferenceEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f6ce0-102">IInstallReferenceEnum Interface</span></span>
<span data-ttu-id="f6ce0-103">참조 된 어셈블리가 전역 어셈블리 캐시에 설치에 대 한 열거자를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f6ce0-103">Represents an enumerator for the referenced assemblies installed in the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6ce0-104">구문</span><span class="sxs-lookup"><span data-stu-id="f6ce0-104">Syntax</span></span>  
  
```  
interface IInstallReferenceEnum : IUnknown {  
    HRESULT GetNextInstallReferenceItem (  
        [out] IInstallReferenceItem **ppRefItem,  
        [in]  DWORD dwFlags,  
        [in]  LPVOID pvReserved  
    );  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="f6ce0-105">메서드</span><span class="sxs-lookup"><span data-stu-id="f6ce0-105">Methods</span></span>  
  
|<span data-ttu-id="f6ce0-106">메서드</span><span class="sxs-lookup"><span data-stu-id="f6ce0-106">Method</span></span>|<span data-ttu-id="f6ce0-107">설명</span><span class="sxs-lookup"><span data-stu-id="f6ce0-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f6ce0-108">GetNextInstallReferenceItem 메서드</span><span class="sxs-lookup"><span data-stu-id="f6ce0-108">GetNextInstallReferenceItem Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceenum-getnextinstallreferenceitem-method.md)|<span data-ttu-id="f6ce0-109">다음에 대 한 포인터를 가져옵니다 `IInstallReferenceItem` 이에 포함 된 `IInstallReferenceEnum`합니다.</span><span class="sxs-lookup"><span data-stu-id="f6ce0-109">Gets a pointer to the next `IInstallReferenceItem` contained in this `IInstallReferenceEnum`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f6ce0-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f6ce0-110">Requirements</span></span>  
 <span data-ttu-id="f6ce0-111">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f6ce0-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f6ce0-112">**헤더:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="f6ce0-112">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="f6ce0-113">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f6ce0-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6ce0-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f6ce0-114">See Also</span></span>  
 [<span data-ttu-id="f6ce0-115">Fusion 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f6ce0-115">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)  
 [<span data-ttu-id="f6ce0-116">IInstallReferenceItem 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f6ce0-116">IInstallReferenceItem Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceitem-interface.md)
