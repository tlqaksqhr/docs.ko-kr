---
title: "ISymUnmanagedAsyncMethod::GetAsyncStepInfoCount 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 32a4e084-09b2-4946-a4a7-19a1fed9f7cc
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 62b6202949432590a87545f3ae243fd828da31ee
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedasyncmethodgetasyncstepinfocount-method"></a><span data-ttu-id="3ac2d-102">ISymUnmanagedAsyncMethod::GetAsyncStepInfoCount 메서드</span><span class="sxs-lookup"><span data-stu-id="3ac2d-102">ISymUnmanagedAsyncMethod::GetAsyncStepInfoCount Method</span></span>
<span data-ttu-id="3ac2d-103">참조 [DefineAsyncStepInfo 메서드](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3ac2d-103">See [DefineAsyncStepInfo Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ac2d-104">구문</span><span class="sxs-lookup"><span data-stu-id="3ac2d-104">Syntax</span></span>  
  
```idl  
HRESULT GetAsyncStepInfoCount(    [out, retval] ULONG32* pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3ac2d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3ac2d-105">Parameters</span></span>  
  
|<span data-ttu-id="3ac2d-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3ac2d-106">Parameter</span></span>|<span data-ttu-id="3ac2d-107">설명</span><span class="sxs-lookup"><span data-stu-id="3ac2d-107">Description</span></span>|  
|---------------|-----------------|  
|`pRetVal`||  
  
## <a name="return-value"></a><span data-ttu-id="3ac2d-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="3ac2d-108">Return Value</span></span>  
 <span data-ttu-id="3ac2d-109">`HRESULT`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="3ac2d-109">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3ac2d-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3ac2d-110">Requirements</span></span>  
 <span data-ttu-id="3ac2d-111">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="3ac2d-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ac2d-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3ac2d-112">See Also</span></span>  
 [<span data-ttu-id="3ac2d-113">ISymUnmanagedAsyncMethod 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3ac2d-113">ISymUnmanagedAsyncMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)
