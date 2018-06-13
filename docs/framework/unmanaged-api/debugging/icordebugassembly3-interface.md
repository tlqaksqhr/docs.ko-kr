---
title: ICorDebugAssembly3 인터페이스
ms.date: 03/30/2017
ms.assetid: 17fc5d76-75a9-4933-83f0-594de7f973f3
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5042f59b3716d077cc441585004e075b765c0cfb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33407857"
---
# <a name="icordebugassembly3-interface"></a><span data-ttu-id="5b26c-102">ICorDebugAssembly3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5b26c-102">ICorDebugAssembly3 Interface</span></span>
<span data-ttu-id="5b26c-103">컨테이너 어셈블리 및 해당 포함 된에 대 한 지원을 제공 하기 위한 ICorDebugAssembly 인터페이스를 논리적으로 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b26c-103">Logically extends the ICorDebugAssembly interface to provide support for container assemblies and their contained assemblies.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5b26c-104">메서드</span><span class="sxs-lookup"><span data-stu-id="5b26c-104">Methods</span></span>  
  
|<span data-ttu-id="5b26c-105">메서드</span><span class="sxs-lookup"><span data-stu-id="5b26c-105">Method</span></span>|<span data-ttu-id="5b26c-106">설명</span><span class="sxs-lookup"><span data-stu-id="5b26c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5b26c-107">EnumerateContainedAssemblies 메서드</span><span class="sxs-lookup"><span data-stu-id="5b26c-107">EnumerateContainedAssemblies Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly3-enumeratecontainedassemblies-method.md)|<span data-ttu-id="5b26c-108">이 어셈블리에 포함된 어셈블리에 대한 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5b26c-108">Gets an enumerator for the assemblies contained in this assembly.</span></span>|  
|[<span data-ttu-id="5b26c-109">GetContainerAssembly 메서드</span><span class="sxs-lookup"><span data-stu-id="5b26c-109">GetContainerAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly3-getcontainerassembly-method.md)|<span data-ttu-id="5b26c-110">이 `ICorDebugAssembly3` 개체의 컨테이너 어셈블리를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="5b26c-110">Returns the container assembly of this `ICorDebugAssembly3` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5b26c-111">설명</span><span class="sxs-lookup"><span data-stu-id="5b26c-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5b26c-112">이 인터페이스는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b26c-112">The interface is available with .NET Native only.</span></span> <span data-ttu-id="5b26c-113">.NET 네이티브 외부의 ICorDebug 시나리오에 대해 `QueryInterface`를 호출하여 인터페이스 포인터를 검색하려고 하면 `E_NOINTERFACE`가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="5b26c-113">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5b26c-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5b26c-114">Requirements</span></span>  
 <span data-ttu-id="5b26c-115">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5b26c-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5b26c-116">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5b26c-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5b26c-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5b26c-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5b26c-118">**.NET framework 버전:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5b26c-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b26c-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5b26c-119">See Also</span></span>  
 [<span data-ttu-id="5b26c-120">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5b26c-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="5b26c-121">디버깅</span><span class="sxs-lookup"><span data-stu-id="5b26c-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
