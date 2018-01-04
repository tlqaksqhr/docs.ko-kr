---
title: "ISymUnmanagedAsyncMethod::GetAsyncStepInfo 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 3ef5b4b8-4ac7-4906-849b-f932c5e3db07
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f999e8cfba38ff4b4b15baea7ca9fa89606cb0ce
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedasyncmethodgetasyncstepinfo-method"></a><span data-ttu-id="0ef34-102">ISymUnmanagedAsyncMethod::GetAsyncStepInfo 메서드</span><span class="sxs-lookup"><span data-stu-id="0ef34-102">ISymUnmanagedAsyncMethod::GetAsyncStepInfo Method</span></span>
<span data-ttu-id="0ef34-103">참조 [DefineAsyncStepInfo 메서드](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0ef34-103">See [DefineAsyncStepInfo Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ef34-104">구문</span><span class="sxs-lookup"><span data-stu-id="0ef34-104">Syntax</span></span>  
  
```idl  
HRESULT GetAsyncStepInfo(    [in] ULONG32 cStepInfo,    [out] ULONG32 *pcStepInfo,    [in, size_is(cStepInfo)] ULONG32 yieldOffsets[],    [in, size_is(cStepInfo)] ULONG32 breakpointOffset[],    [in, size_is(cStepInfo)] mdToken breakpointMethod[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0ef34-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0ef34-105">Parameters</span></span>  
  
|<span data-ttu-id="0ef34-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0ef34-106">Parameter</span></span>|<span data-ttu-id="0ef34-107">설명</span><span class="sxs-lookup"><span data-stu-id="0ef34-107">Description</span></span>|  
|---------------|-----------------|  
|`cStepInfo`||  
|`pcStepInfo`||  
|`yieldOffsets`||  
|`breakpointOffset`||  
|`breakpointMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="0ef34-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="0ef34-108">Return Value</span></span>  
 <span data-ttu-id="0ef34-109">`HRESULT`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="0ef34-109">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0ef34-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0ef34-110">Requirements</span></span>  
 <span data-ttu-id="0ef34-111">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="0ef34-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ef34-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0ef34-112">See Also</span></span>  
 [<span data-ttu-id="0ef34-113">ISymUnmanagedAsyncMethod 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0ef34-113">ISymUnmanagedAsyncMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)
