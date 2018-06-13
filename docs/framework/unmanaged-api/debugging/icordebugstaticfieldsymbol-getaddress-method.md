---
title: ICorDebugStaticFieldSymbol::GetAddress 메서드
ms.date: 03/30/2017
ms.assetid: 5a6c9a5a-ec72-4c40-a9c3-cee7baa63687
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b877bde80b59b7d2074e4d799653dedd5aaacf39
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33419255"
---
# <a name="icordebugstaticfieldsymbolgetaddress-method"></a><span data-ttu-id="7d205-102">ICorDebugStaticFieldSymbol::GetAddress 메서드</span><span class="sxs-lookup"><span data-stu-id="7d205-102">ICorDebugStaticFieldSymbol::GetAddress Method</span></span>
<span data-ttu-id="7d205-103">정적 필드의 주소를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7d205-103">Gets the address of a static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d205-104">구문</span><span class="sxs-lookup"><span data-stu-id="7d205-104">Syntax</span></span>  
  
```  
HRESULT GetAddress(  
   [out] CORDB_ADDRESS *pRVA  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7d205-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7d205-105">Parameters</span></span>  
 <span data-ttu-id="7d205-106">pRVA</span><span class="sxs-lookup"><span data-stu-id="7d205-106">pRVA</span></span>  
 <span data-ttu-id="7d205-107">[out] 정적 필드의 RVA(상대 가상 주소)에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="7d205-107">[out] A pointer to the relative virtual address (RVA) of the static field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7d205-108">설명</span><span class="sxs-lookup"><span data-stu-id="7d205-108">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7d205-109">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d205-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7d205-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7d205-110">Requirements</span></span>  
 <span data-ttu-id="7d205-111">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7d205-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7d205-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7d205-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7d205-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7d205-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7d205-114">**.NET framework 버전:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7d205-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d205-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7d205-115">See Also</span></span>  
 [<span data-ttu-id="7d205-116">ICorDebugStaticFieldSymbol 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7d205-116">ICorDebugStaticFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md)  
 [<span data-ttu-id="7d205-117">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7d205-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
