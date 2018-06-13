---
title: ICorDebugInstanceFieldSymbol 인터페이스
ms.date: 03/30/2017
ms.assetid: a4a8f259-b83a-4425-ae8b-72b067dbc0d9
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 82f6ccd43059f33a69b8b052f9efa34c4e4f2c1e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33417718"
---
# <a name="icordebuginstancefieldsymbol-interface"></a><span data-ttu-id="1f0b0-102">ICorDebugInstanceFieldSymbol 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1f0b0-102">ICorDebugInstanceFieldSymbol Interface</span></span>
<span data-ttu-id="1f0b0-103">인스턴스 필드에 대한 디버그 기호 정보를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1f0b0-103">Represents the debug symbol information for an instance field.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1f0b0-104">메서드</span><span class="sxs-lookup"><span data-stu-id="1f0b0-104">Methods</span></span>  
  
|<span data-ttu-id="1f0b0-105">메서드</span><span class="sxs-lookup"><span data-stu-id="1f0b0-105">Method</span></span>|<span data-ttu-id="1f0b0-106">설명</span><span class="sxs-lookup"><span data-stu-id="1f0b0-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1f0b0-107">GetName 메서드</span><span class="sxs-lookup"><span data-stu-id="1f0b0-107">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-getname-method.md)|<span data-ttu-id="1f0b0-108">인스턴스 필드의 이름을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1f0b0-108">Gets the name of the instance field.</span></span>|  
|[<span data-ttu-id="1f0b0-109">GetOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="1f0b0-109">GetOffset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-getoffset-method.md)|<span data-ttu-id="1f0b0-110">부모 클래스에서 이 인스턴스 필드의 오프셋(바이트)을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1f0b0-110">Gets the offset in bytes of this instance field in its parent class.</span></span>|  
|[<span data-ttu-id="1f0b0-111">GetSize 메서드</span><span class="sxs-lookup"><span data-stu-id="1f0b0-111">GetSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-getsize-method.md)|<span data-ttu-id="1f0b0-112">인스턴스 필드의 크기(바이트)를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1f0b0-112">Gets the size in bytes of the instance field.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1f0b0-113">설명</span><span class="sxs-lookup"><span data-stu-id="1f0b0-113">Remarks</span></span>  
 <span data-ttu-id="1f0b0-114">`ICorDebugInstanceFieldSymbol` 인터페이스는 인스턴스 필드에 대한 디버그 기호 정보를 검색하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f0b0-114">The `ICorDebugInstanceFieldSymbol` interface is used to retrieve the debug symbol information for an instance field.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1f0b0-115">이 인터페이스는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f0b0-115">This interface is available with .NET Native only.</span></span> <span data-ttu-id="1f0b0-116">.NET 네이티브 외부의 ICorDebug 시나리오에 대해 이 인터페이스를 구현하는 경우 공용 언어 런타임에서 이 인터페이스를 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="1f0b0-116">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1f0b0-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1f0b0-117">Requirements</span></span>  
 <span data-ttu-id="1f0b0-118">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1f0b0-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1f0b0-119">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1f0b0-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1f0b0-120">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1f0b0-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1f0b0-121">**.NET framework 버전:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1f0b0-121">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f0b0-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1f0b0-122">See Also</span></span>  
 [<span data-ttu-id="1f0b0-123">ICorDebugStaticFieldSymbol 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1f0b0-123">ICorDebugStaticFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md)  
 [<span data-ttu-id="1f0b0-124">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1f0b0-124">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="1f0b0-125">디버깅</span><span class="sxs-lookup"><span data-stu-id="1f0b0-125">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
