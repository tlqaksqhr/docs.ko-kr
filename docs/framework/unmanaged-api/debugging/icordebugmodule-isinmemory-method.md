---
title: "ICorDebugModule::IsInMemory 메서드"
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
- ICorDebugModule.IsInMemory
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::IsInMemory
helpviewer_keywords:
- IsInMemory method [.NET Framework debugging]
- ICorDebugModule::IsInMemory method [.NET Framework debugging]
ms.assetid: 89940711-98e7-4aa6-bffc-5e39e91e1b7d
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 448458874c4de96503261bc0fe34fae160395c49
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmoduleisinmemory-method"></a><span data-ttu-id="04d05-102">ICorDebugModule::IsInMemory 메서드</span><span class="sxs-lookup"><span data-stu-id="04d05-102">ICorDebugModule::IsInMemory Method</span></span>
<span data-ttu-id="04d05-103">메모리에만이 모듈 있는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="04d05-103">Gets a value that indicates whether this module exists only in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04d05-104">구문</span><span class="sxs-lookup"><span data-stu-id="04d05-104">Syntax</span></span>  
  
```  
HRESULT IsInMemory(  
    [out] BOOL *pInMemory  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="04d05-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="04d05-105">Parameters</span></span>  
 `pInMemory`  
 <span data-ttu-id="04d05-106">[out] `true` 메모리에만이 모듈 존재 하는 경우 이렇게 하지 않으면 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="04d05-106">[out] `true` if this module exists only in memory; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="04d05-107">설명</span><span class="sxs-lookup"><span data-stu-id="04d05-107">Remarks</span></span>  
 <span data-ttu-id="04d05-108">공용 언어 런타임 (CLR) 원시 바이트 스트림에서 모듈의 로드를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="04d05-108">The common language runtime (CLR) supports the loading of modules from raw streams of bytes.</span></span> <span data-ttu-id="04d05-109">이러한 모듈은 호출 *메모리 내 모듈* 하며 디스크에 존재 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="04d05-109">Such modules are called *in-memory modules* and do not exist on disk.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="04d05-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="04d05-110">Requirements</span></span>  
 <span data-ttu-id="04d05-111">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="04d05-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="04d05-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="04d05-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="04d05-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="04d05-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="04d05-114">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="04d05-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04d05-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="04d05-115">See Also</span></span>  
    
 
