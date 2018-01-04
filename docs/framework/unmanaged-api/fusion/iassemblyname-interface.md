---
title: "IAssemblyName 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IAssemblyName
api_location: fusion.dll
api_type: COM
f1_keywords: IAssemblyName
helpviewer_keywords: IAssemblyName interface [.NET Framework fusion]
ms.assetid: f7f8e605-6b67-4151-936f-f04ecd671d90
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 902ad9f67d06306e79666f0e10d85bdb9c65c377
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="iassemblyname-interface"></a><span data-ttu-id="dc769-102">IAssemblyName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="dc769-102">IAssemblyName Interface</span></span>
<span data-ttu-id="dc769-103">설명 하 고 어셈블리의 고유 id를 가진 작업 하기 위한 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc769-103">Provides methods for describing and working with an assembly's unique identity.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="dc769-104">메서드</span><span class="sxs-lookup"><span data-stu-id="dc769-104">Methods</span></span>  
  
|<span data-ttu-id="dc769-105">메서드</span><span class="sxs-lookup"><span data-stu-id="dc769-105">Method</span></span>|<span data-ttu-id="dc769-106">설명</span><span class="sxs-lookup"><span data-stu-id="dc769-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="dc769-107">Clone 메서드</span><span class="sxs-lookup"><span data-stu-id="dc769-107">Clone Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-clone-method.md)|<span data-ttu-id="dc769-108">이 항목의 단순 복사본을 만듭니다 `IAssemblyName` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="dc769-108">Creates a shallow copy of this `IAssemblyName` object.</span></span>|  
|[<span data-ttu-id="dc769-109">Finalize 메서드</span><span class="sxs-lookup"><span data-stu-id="dc769-109">Finalize Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-finalize-method.md)|<span data-ttu-id="dc769-110">이러한 `IAssemblyName` 리소스를 해제 하 고 소멸자가 호출 되기 전에 다른 정리 작업을 수행할 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="dc769-110">Allows this `IAssemblyName` object to release resources and perform other cleanup operations before its destructor is called.</span></span>|  
|[<span data-ttu-id="dc769-111">GetDisplayName 메서드</span><span class="sxs-lookup"><span data-stu-id="dc769-111">GetDisplayName Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-getdisplayname-method.md)|<span data-ttu-id="dc769-112">이 참조 하는 어셈블리의 이해 하기 쉬운 이름을 가져옵니다 `IAssemblyName` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="dc769-112">Gets the human-readable name of the assembly referenced by this `IAssemblyName` object.</span></span>|  
|[<span data-ttu-id="dc769-113">GetName 메서드</span><span class="sxs-lookup"><span data-stu-id="dc769-113">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-getname-method.md)|<span data-ttu-id="dc769-114">이 참조 하는 어셈블리의 단순 하 고 암호화 되지 않은 이름을 가져옵니다 `IAssemblyName` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="dc769-114">Gets the simple, unencrypted name of the assembly referenced by this `IAssemblyName` object.</span></span>|  
|[<span data-ttu-id="dc769-115">GetProperty 메서드</span><span class="sxs-lookup"><span data-stu-id="dc769-115">GetProperty Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-getproperty-method.md)|<span data-ttu-id="dc769-116">지정 된 참조 하는 속성에 대 한 포인터를 가져옵니다 `PropertyId`합니다.</span><span class="sxs-lookup"><span data-stu-id="dc769-116">Gets a pointer to the property referenced by the specified `PropertyId`.</span></span>|  
|[<span data-ttu-id="dc769-117">GetVersion 메서드</span><span class="sxs-lookup"><span data-stu-id="dc769-117">GetVersion Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-getversion-method.md)|<span data-ttu-id="dc769-118">이 참조 하는 어셈블리에 대 한 버전 정보를 가져옵니다 `IAssemblyName` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="dc769-118">Gets the version information for the assembly referenced by this `IAssemblyName` object.</span></span>|  
|[<span data-ttu-id="dc769-119">IsEqual 메서드</span><span class="sxs-lookup"><span data-stu-id="dc769-119">IsEqual Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-isequal-method.md)|<span data-ttu-id="dc769-120">지정 된 있는지 여부를 결정 `IAssemblyName` 개체가 같은지를이 `IAssemblyName`지정된 된 비교 플래그에 따라 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc769-120">Determines whether a specified `IAssemblyName` object is equal to this `IAssemblyName`, based on the specified comparison flags.</span></span>|  
|[<span data-ttu-id="dc769-121">SetProperty 메서드</span><span class="sxs-lookup"><span data-stu-id="dc769-121">SetProperty Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-setproperty-method.md)|<span data-ttu-id="dc769-122">지정 된 참조 하는 속성의 값을 설정 `PropertyId`합니다.</span><span class="sxs-lookup"><span data-stu-id="dc769-122">Sets the value of the property referenced by the specified `PropertyId`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="dc769-123">요구 사항</span><span class="sxs-lookup"><span data-stu-id="dc769-123">Requirements</span></span>  
 <span data-ttu-id="dc769-124">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="dc769-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dc769-125">**헤더:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="dc769-125">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="dc769-126">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dc769-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc769-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dc769-127">See Also</span></span>  
 [<span data-ttu-id="dc769-128">Fusion 인터페이스</span><span class="sxs-lookup"><span data-stu-id="dc769-128">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)  
 [<span data-ttu-id="dc769-129">IAssemblyEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="dc769-129">IAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md)
