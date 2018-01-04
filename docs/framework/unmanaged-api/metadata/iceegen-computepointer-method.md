---
title: "ICeeGen::ComputePointer 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICeeGen.ComputePointer
api_location: mscoree.dll
api_type: COM
f1_keywords: ICeeGen::ComputePointer
helpviewer_keywords:
- ICeeGen::ComputePointer method [.NET Framework metadata]
- ComputePointer method [.NET Framework metadata]
ms.assetid: b6b95c04-0f2c-4fcc-a8bc-3b1dcbdba731
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0b027615f7697b9ea103d44bea0ec44834fe3f04
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="iceegencomputepointer-method"></a><span data-ttu-id="194da-102">ICeeGen::ComputePointer 메서드</span><span class="sxs-lookup"><span data-stu-id="194da-102">ICeeGen::ComputePointer Method</span></span>
<span data-ttu-id="194da-103">지정 된 코드 섹션에 대 한 버퍼를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="194da-103">Determines the buffer for the specified code section.</span></span>  
  
 <span data-ttu-id="194da-104">이 메서드는 사용 되지 않으며 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="194da-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="194da-105">구문</span><span class="sxs-lookup"><span data-stu-id="194da-105">Syntax</span></span>  
  
```  
HRESULT ComputePointer (  
    [in]  HCEESECTION  section,  
    [in]  ULONG        RVA,   
    [out] UCHAR        **lpBuffer  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="194da-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="194da-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="194da-107">[in] 반환할 버퍼에 대 한 코드 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="194da-107">[in] The code section for which to return a buffer.</span></span>  
  
 `RVA`  
 <span data-ttu-id="194da-108">[in] 포인터를 얻으려면 메서드 상대 가상 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="194da-108">[in] The relative virtual address of the method for which to get a pointer.</span></span>  
  
 `lpBuffer`  
 <span data-ttu-id="194da-109">[out] 반환된 된 버퍼에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="194da-109">[out] A pointer to the returned buffer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="194da-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="194da-110">Requirements</span></span>  
 <span data-ttu-id="194da-111">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="194da-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="194da-112">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="194da-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="194da-113">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="194da-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="194da-114">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="194da-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="194da-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="194da-115">See Also</span></span>  
 [<span data-ttu-id="194da-116">ICeeGen 인터페이스</span><span class="sxs-lookup"><span data-stu-id="194da-116">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
