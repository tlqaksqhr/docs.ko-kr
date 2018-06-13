---
title: ICorDebugAssembly3::GetContainerAssembly 메서드
ms.date: 03/30/2017
ms.assetid: f5fddeb6-b82e-4ebb-b432-849ce8513c77
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: acb34ac2568ac88797441306820e6e762b5ac46e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33409729"
---
# <a name="icordebugassembly3getcontainerassembly-method"></a><span data-ttu-id="749ea-102">ICorDebugAssembly3::GetContainerAssembly 메서드</span><span class="sxs-lookup"><span data-stu-id="749ea-102">ICorDebugAssembly3::GetContainerAssembly Method</span></span>
<span data-ttu-id="749ea-103">이 `ICorDebugAssembly3` 개체의 컨테이너 어셈블리를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="749ea-103">Returns the container assembly of this `ICorDebugAssembly3` object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="749ea-104">구문</span><span class="sxs-lookup"><span data-stu-id="749ea-104">Syntax</span></span>  
  
```  
HRESULT GetContainerAssembly(  
    ICorDebugAssembly **ppAssembly  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="749ea-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="749ea-105">Parameters</span></span>  
 `ppAssembly`  
 <span data-ttu-id="749ea-106">컨테이너 어셈블리를 나타내는 ICorDebugAssembly 개체의 주소에 대 한 포인터 또는 **null** 메서드 호출이 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="749ea-106">A pointer to the address of an ICorDebugAssembly object that represents the container assembly, or **null** if the method call fails.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="749ea-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="749ea-107">Return Value</span></span>  
 <span data-ttu-id="749ea-108">`S_OK` 메서드 호출이 성공 하면 그렇지 않으면 `S_FALSE`, 및 `ppAssembly` 은 **null**합니다.</span><span class="sxs-lookup"><span data-stu-id="749ea-108">`S_OK` if the method call succeeds; otherwise, `S_FALSE`, and `ppAssembly` is **null**.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="749ea-109">설명</span><span class="sxs-lookup"><span data-stu-id="749ea-109">Remarks</span></span>  
 <span data-ttu-id="749ea-110">이 어셈블리를 단일 컨테이너 어셈블리 내의 다른 어셈블리와 병합한 경우 이 메서드는 컨테이너 어셈블리를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="749ea-110">If this assembly has been merged with others inside a single container assembly, this method returns the container assembly.</span></span> <span data-ttu-id="749ea-111">자세한 내용 및 용어에 대 한 참조는 [icordebugprocess6:: Enablevirtualmodulesplitting](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-enablevirtualmodulesplitting-method.md) 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="749ea-111">For more information and terminology, see the [ICorDebugProcess6::EnableVirtualModuleSplitting](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-enablevirtualmodulesplitting-method.md) topic.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="749ea-112">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="749ea-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="749ea-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="749ea-113">Requirements</span></span>  
 <span data-ttu-id="749ea-114">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="749ea-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="749ea-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="749ea-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="749ea-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="749ea-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="749ea-117">**.NET framework 버전:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="749ea-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="749ea-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="749ea-118">See Also</span></span>  
 [<span data-ttu-id="749ea-119">ICorDebugAssembly3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="749ea-119">ICorDebugAssembly3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly3-interface.md)  
 [<span data-ttu-id="749ea-120">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="749ea-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
