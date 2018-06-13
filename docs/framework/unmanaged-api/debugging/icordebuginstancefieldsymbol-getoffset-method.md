---
title: ICorDebugInstanceFieldSymbol::GetOffset 메서드
ms.date: 03/30/2017
ms.assetid: 7e470150-2b92-4425-989c-315f48964fd2
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c77ac2eac1022fa591066901f48eaf609b5367af
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33413565"
---
# <a name="icordebuginstancefieldsymbolgetoffset-method"></a><span data-ttu-id="897da-102">ICorDebugInstanceFieldSymbol::GetOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="897da-102">ICorDebugInstanceFieldSymbol::GetOffset Method</span></span>
<span data-ttu-id="897da-103">부모 클래스에서 이 인스턴스 필드의 오프셋(바이트)을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="897da-103">Gets the offset in bytes of this instance field in its parent class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="897da-104">구문</span><span class="sxs-lookup"><span data-stu-id="897da-104">Syntax</span></span>  
  
```  
HRESULT GetOffset(  
   [out] ULONG32 *pcbOffset  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="897da-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="897da-105">Parameters</span></span>  
 `pcbOffset`  
 <span data-ttu-id="897da-106">부모 클래스에서 이 인스턴스 필드가 오프셋되는 바이트 수에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="897da-106">A pointer to the number of bytes that this instance field is offset in its parent class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="897da-107">설명</span><span class="sxs-lookup"><span data-stu-id="897da-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="897da-108">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="897da-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="897da-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="897da-109">Requirements</span></span>  
 <span data-ttu-id="897da-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="897da-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="897da-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="897da-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="897da-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="897da-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="897da-113">**.NET framework 버전:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="897da-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="897da-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="897da-114">See Also</span></span>  
 [<span data-ttu-id="897da-115">ICorDebugInstanceFieldSymbol 인터페이스</span><span class="sxs-lookup"><span data-stu-id="897da-115">ICorDebugInstanceFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-interface.md)  
 [<span data-ttu-id="897da-116">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="897da-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
