---
title: ICorDebugDataTarget2::GetImageLocation 메서드
ms.date: 03/30/2017
ms.assetid: 696afe71-5852-478d-a33f-b2d2dbc4b91f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c6962c8063479b3b0279d771b1b0cd1df63f696b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33416418"
---
# <a name="icordebugdatatarget2getimagelocation-method"></a><span data-ttu-id="59294-102">ICorDebugDataTarget2::GetImageLocation 메서드</span><span class="sxs-lookup"><span data-stu-id="59294-102">ICorDebugDataTarget2::GetImageLocation Method</span></span>
<span data-ttu-id="59294-103">모듈의 경로를 모듈의 기준 주소에서 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="59294-103">Returns the path of a module from the module's base address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59294-104">구문</span><span class="sxs-lookup"><span data-stu-id="59294-104">Syntax</span></span>  
  
```  
HRESULT GetImageLocation(    [in] CORDB_ADDRESS baseAddress,  
    [in] ULONG32 cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="59294-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="59294-105">Parameters</span></span>  
 `baseAddress`  
 <span data-ttu-id="59294-106">[in] A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) 모듈의 기준 주소를 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="59294-106">[in] A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) value that represents the module's base address.</span></span>  
  
 `cchName`  
 <span data-ttu-id="59294-107">[in] 모듈 경로를 수신할 버퍼의 문자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="59294-107">[in] The number of characters in the buffer that is to receive the module path.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="59294-108">[out] `szName` 버퍼에 기록된 문자 수에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="59294-108">[out] A pointer to the number of characters written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="59294-109">[out] 모듈의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="59294-109">[out] The path of the module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="59294-110">설명</span><span class="sxs-lookup"><span data-stu-id="59294-110">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="59294-111">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59294-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="59294-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="59294-112">Requirements</span></span>  
 <span data-ttu-id="59294-113">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="59294-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="59294-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="59294-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="59294-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="59294-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="59294-116">**.NET framework 버전:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="59294-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59294-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="59294-117">See Also</span></span>  
 [<span data-ttu-id="59294-118">ICorDebugDataTarget2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="59294-118">ICorDebugDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-interface.md)  
 [<span data-ttu-id="59294-119">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="59294-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
