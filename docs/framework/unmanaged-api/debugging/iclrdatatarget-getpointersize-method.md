---
title: "ICLRDataTarget::GetPointerSize 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICLRDataTarget.GetPointerSize
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::GetPointerSize
helpviewer_keywords:
- GetPointerSize method [.NET Framework debugging]
- ICLRDataTarget::GetPointerSize method [.NET Framework debugging]
ms.assetid: 51d9f4a4-81a7-4527-8537-5212bdb05c70
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 4ca35246b82ed4adc982b6e7b157398d230dabe4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="iclrdatatargetgetpointersize-method"></a><span data-ttu-id="12523-102">ICLRDataTarget::GetPointerSize 메서드</span><span class="sxs-lookup"><span data-stu-id="12523-102">ICLRDataTarget::GetPointerSize Method</span></span>
<span data-ttu-id="12523-103">대상 프로세스를 사용 하는 포인터 형식을 바이트 단위로 크기를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="12523-103">Gets the size, in bytes, of the pointer type that the target process uses.</span></span> <span data-ttu-id="12523-104">이 메서드는 공용 언어 런타임 데이터 액세스 서비스에 의해 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="12523-104">This method is called by the common language runtime data access services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12523-105">구문</span><span class="sxs-lookup"><span data-stu-id="12523-105">Syntax</span></span>  
  
```  
HRESULT GetPointerSize (  
    [out] ULONG32     *pointerSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="12523-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="12523-106">Parameters</span></span>  
 `pointerSize`  
 <span data-ttu-id="12523-107">[out] 대상 프로세스에 대 한 포인터를 바이트 단위로 크기를 지정 하는 정수 값에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="12523-107">[out] A pointer to an integer value that specifies the size, in bytes, of a pointer on the target process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="12523-108">설명</span><span class="sxs-lookup"><span data-stu-id="12523-108">Remarks</span></span>  
 <span data-ttu-id="12523-109">이 메서드는 디버깅 응용 프로그램의 작성자가 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="12523-109">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="12523-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="12523-110">Requirements</span></span>  
 <span data-ttu-id="12523-111">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="12523-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="12523-112">**헤더:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="12523-112">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="12523-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="12523-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="12523-114">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="12523-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12523-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="12523-115">See Also</span></span>  
 [<span data-ttu-id="12523-116">ICLRDataTarget 인터페이스</span><span class="sxs-lookup"><span data-stu-id="12523-116">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
