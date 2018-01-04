---
title: "ISymUnmanagedAsyncMethod::IsAsyncMethod 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 670a7653-dac6-4171-98ee-d669e3adf4b2
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 560690e95e7aa0aef37e3a708183641bd70ee97d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedasyncmethodisasyncmethod-method"></a><span data-ttu-id="dff0d-102">ISymUnmanagedAsyncMethod::IsAsyncMethod 메서드</span><span class="sxs-lookup"><span data-stu-id="dff0d-102">ISymUnmanagedAsyncMethod::IsAsyncMethod Method</span></span>
<span data-ttu-id="dff0d-103">여부는 메서드는 비동기 정보를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="dff0d-103">Checks if the method has async information or not.</span></span>  
  
 <span data-ttu-id="dff0d-104">이 메서드가 반환 하는 경우 `FALSE` 이 인터페이스에서 다른 메서드를 호출 하는 데 유효한 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dff0d-104">If this method returns `FALSE` then it is invalid to call any other methods in this interface.</span></span> <span data-ttu-id="dff0d-105">모든 return가 `E_UNEXPECTED` 이 경우.</span><span class="sxs-lookup"><span data-stu-id="dff0d-105">They will all return `E_UNEXPECTED` in this case.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dff0d-106">구문</span><span class="sxs-lookup"><span data-stu-id="dff0d-106">Syntax</span></span>  
  
```idl  
HRESULT IsAsyncMethod(    [out, retval] BOOL* pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="dff0d-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="dff0d-107">Parameters</span></span>  
  
|<span data-ttu-id="dff0d-108">매개 변수</span><span class="sxs-lookup"><span data-stu-id="dff0d-108">Parameter</span></span>|<span data-ttu-id="dff0d-109">설명</span><span class="sxs-lookup"><span data-stu-id="dff0d-109">Description</span></span>|  
|---------------|-----------------|  
|`pRetVal`||  
  
## <a name="return-value"></a><span data-ttu-id="dff0d-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="dff0d-110">Return Value</span></span>  
 <span data-ttu-id="dff0d-111">`HRESULT`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="dff0d-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dff0d-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="dff0d-112">Requirements</span></span>  
 <span data-ttu-id="dff0d-113">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="dff0d-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dff0d-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dff0d-114">See Also</span></span>  
 [<span data-ttu-id="dff0d-115">ISymUnmanagedAsyncMethod 인터페이스</span><span class="sxs-lookup"><span data-stu-id="dff0d-115">ISymUnmanagedAsyncMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)
