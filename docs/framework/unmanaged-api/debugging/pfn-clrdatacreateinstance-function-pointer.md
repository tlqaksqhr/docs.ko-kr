---
title: "PFN_CLRDataCreateInstance 함수 포인터"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: PFN_CLRDataCreateInstance
api_location: mscordbi.dll
api_type: COM
f1_keywords: PFN_CLRDataCreateInstance
helpviewer_keywords: PFN_CLRDataCreateInstance function pointer [.NET Framework debugging]
ms.assetid: 5c66ac57-d751-4de5-af9f-26ceb949af8b
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 98a966434332549d9ceb7f29de81e19fa1b2108f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="pfnclrdatacreateinstance-function-pointer"></a><span data-ttu-id="266e8-102">PFN_CLRDataCreateInstance 함수 포인터</span><span class="sxs-lookup"><span data-stu-id="266e8-102">PFN_CLRDataCreateInstance Function Pointer</span></span>
<span data-ttu-id="266e8-103">지정 된 대상 항목에 대 한 인터페이스 개체를 만드는 함수를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="266e8-103">Points to a function that creates an interface object for the specified target item.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="266e8-104">구문</span><span class="sxs-lookup"><span data-stu-id="266e8-104">Syntax</span></span>  
  
```  
typedef HRESULT (STDAPICALLTYPE* PFN_CLRDataCreateInstance) (  
    [in]  REFIID           iid,  
    [in]  ICLRDataTarget  *target,  
    [out] void           **iface  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="266e8-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="266e8-105">Parameters</span></span>  
 `iid`  
 <span data-ttu-id="266e8-106">[in] 인스턴스화할 인터페이스의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="266e8-106">[in] The identifier of the interface to be instantiated.</span></span>  
  
 `target`  
 <span data-ttu-id="266e8-107">[in] 사용자가 구현에 대 한 포인터 [ICLRDataTarget](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md) 인터페이스 개체를 대상 항목을 나타내는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="266e8-107">[in] A pointer to a user-implemented [ICLRDataTarget](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md) object that represents the target item for which to create the interface object.</span></span>  
  
 `iface`  
 <span data-ttu-id="266e8-108">[out] 반환 된 인터페이스 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="266e8-108">[out] A pointer to the address of the returned interface object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="266e8-109">설명</span><span class="sxs-lookup"><span data-stu-id="266e8-109">Remarks</span></span>  
 <span data-ttu-id="266e8-110">`ICLRDataTarget` 개체는 디버깅 응용 프로그램의 작성자에 의해 구현 됩니다.</span><span class="sxs-lookup"><span data-stu-id="266e8-110">The `ICLRDataTarget` object is implemented by the writer of the debugging application.</span></span> <span data-ttu-id="266e8-111">구현에서는 표시 되는 대상 항목의 형식에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="266e8-111">The implementation depends on the type of target item being represented.</span></span> <span data-ttu-id="266e8-112">프로세스, 메모리 덤프, 원격 컴퓨터 및 등 대상 항목 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="266e8-112">The target item may be a process, memory dump, remote machine, and so on.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="266e8-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="266e8-113">Requirements</span></span>  
 <span data-ttu-id="266e8-114">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="266e8-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="266e8-115">**헤더:** ClrData.idl</span><span class="sxs-lookup"><span data-stu-id="266e8-115">**Header:** ClrData.idl</span></span>  
  
 <span data-ttu-id="266e8-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="266e8-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="266e8-117">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="266e8-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="266e8-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="266e8-118">See Also</span></span>  
 [<span data-ttu-id="266e8-119">디버깅 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="266e8-119">Debugging Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)
