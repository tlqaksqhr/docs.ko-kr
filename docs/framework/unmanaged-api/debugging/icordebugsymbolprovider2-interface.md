---
title: "ICorDebugSymbolProvider2 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 1c9c3d92-f0de-4d4d-87f1-0c702a4808af
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 5ff0446ba8646620cb7322f74a81769e41f35b0d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugsymbolprovider2-interface"></a><span data-ttu-id="01bca-102">ICorDebugSymbolProvider2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="01bca-102">ICorDebugSymbolProvider2 Interface</span></span>
<span data-ttu-id="01bca-103">논리적으로 확장 된 [ICorDebugSymbolProvider](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md) 추가 디버그 기호 정보를 검색 하는 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="01bca-103">Logically extends the [ICorDebugSymbolProvider](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md) interface to retrieve additional debug symbol information.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="01bca-104">메서드</span><span class="sxs-lookup"><span data-stu-id="01bca-104">Methods</span></span>  
  
|<span data-ttu-id="01bca-105">메서드</span><span class="sxs-lookup"><span data-stu-id="01bca-105">Method</span></span>|<span data-ttu-id="01bca-106">설명</span><span class="sxs-lookup"><span data-stu-id="01bca-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="01bca-107">GetFrameProps 메서드</span><span class="sxs-lookup"><span data-stu-id="01bca-107">GetFrameProps Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider2-getframeprops-method.md)|<span data-ttu-id="01bca-108">메서드의 메서드 시작 상대 가상 주소 및 코드 상대 가상 주소가 지정된 부모 프레임을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="01bca-108">Returns the method starting relative virtual address of a method and the parent frame given a code relative virtual address.</span></span>|  
|[<span data-ttu-id="01bca-109">GetGenericDictionaryInfo 메서드</span><span class="sxs-lookup"><span data-stu-id="01bca-109">GetGenericDictionaryInfo Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider2-getgenericdictionaryinfo-method.md)|<span data-ttu-id="01bca-110">제네릭 사전 맵을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="01bca-110">Retrieves a generic dictionary map.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="01bca-111">설명</span><span class="sxs-lookup"><span data-stu-id="01bca-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="01bca-112">이 인터페이스는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01bca-112">This interface is available with .NET Native only.</span></span> <span data-ttu-id="01bca-113">.NET 네이티브 외부의 ICorDebug 시나리오에 대해 이 인터페이스를 구현하는 경우 공용 언어 런타임에서 이 인터페이스를 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="01bca-113">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="01bca-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="01bca-114">Requirements</span></span>  
 <span data-ttu-id="01bca-115">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="01bca-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="01bca-116">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="01bca-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="01bca-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="01bca-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="01bca-118">**.NET framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="01bca-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01bca-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="01bca-119">See Also</span></span>  
 [<span data-ttu-id="01bca-120">ICorDebugSymbolProvider 인터페이스</span><span class="sxs-lookup"><span data-stu-id="01bca-120">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)  
 [<span data-ttu-id="01bca-121">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="01bca-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="01bca-122">디버깅</span><span class="sxs-lookup"><span data-stu-id="01bca-122">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
