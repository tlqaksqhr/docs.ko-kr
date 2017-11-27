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
ms.openlocfilehash: ce91552d7468579d9941c1da75c4d281999d66fd
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedasyncmethodisasyncmethod-method"></a><span data-ttu-id="18072-102">ISymUnmanagedAsyncMethod::IsAsyncMethod 메서드</span><span class="sxs-lookup"><span data-stu-id="18072-102">ISymUnmanagedAsyncMethod::IsAsyncMethod Method</span></span>
<span data-ttu-id="18072-103">여부는 메서드는 비동기 정보를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="18072-103">Checks if the method has async information or not.</span></span>  
  
 <span data-ttu-id="18072-104">이 메서드가 반환 하는 경우 `FALSE` 이 인터페이스에서 다른 메서드를 호출 하는 데 유효한 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="18072-104">If this method returns `FALSE` then it is invalid to call any other methods in this interface.</span></span> <span data-ttu-id="18072-105">모든 return가 `E_UNEXPECTED` 이 경우.</span><span class="sxs-lookup"><span data-stu-id="18072-105">They will all return `E_UNEXPECTED` in this case.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18072-106">구문</span><span class="sxs-lookup"><span data-stu-id="18072-106">Syntax</span></span>  
  
```idl  
HRESULT IsAsyncMethod(    [out, retval] BOOL* pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="18072-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="18072-107">Parameters</span></span>  
  
|<span data-ttu-id="18072-108">매개 변수</span><span class="sxs-lookup"><span data-stu-id="18072-108">Parameter</span></span>|<span data-ttu-id="18072-109">설명</span><span class="sxs-lookup"><span data-stu-id="18072-109">Description</span></span>|  
|---------------|-----------------|  
|`pRetVal`||  
  
## <a name="return-value"></a><span data-ttu-id="18072-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="18072-110">Return Value</span></span>  
 <span data-ttu-id="18072-111">`HRESULT`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="18072-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="18072-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="18072-112">Requirements</span></span>  
 <span data-ttu-id="18072-113">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="18072-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18072-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="18072-114">See Also</span></span>  
 [<span data-ttu-id="18072-115">ISymUnmanagedAsyncMethod 인터페이스</span><span class="sxs-lookup"><span data-stu-id="18072-115">ISymUnmanagedAsyncMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)
