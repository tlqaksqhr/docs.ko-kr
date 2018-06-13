---
title: ISymUnmanagedAsyncMethod::IsAsyncMethod 메서드
ms.date: 03/30/2017
ms.assetid: 670a7653-dac6-4171-98ee-d669e3adf4b2
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3f5bf8252986ffa90ea5380d5342595cb91e5419
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33424943"
---
# <a name="isymunmanagedasyncmethodisasyncmethod-method"></a><span data-ttu-id="7bbc9-102">ISymUnmanagedAsyncMethod::IsAsyncMethod 메서드</span><span class="sxs-lookup"><span data-stu-id="7bbc9-102">ISymUnmanagedAsyncMethod::IsAsyncMethod Method</span></span>
<span data-ttu-id="7bbc9-103">여부는 메서드는 비동기 정보를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="7bbc9-103">Checks if the method has async information or not.</span></span>  
  
 <span data-ttu-id="7bbc9-104">이 메서드가 반환 하는 경우 `FALSE` 이 인터페이스에서 다른 메서드를 호출 하는 데 유효한 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7bbc9-104">If this method returns `FALSE` then it is invalid to call any other methods in this interface.</span></span> <span data-ttu-id="7bbc9-105">모든 return가 `E_UNEXPECTED` 이 경우.</span><span class="sxs-lookup"><span data-stu-id="7bbc9-105">They will all return `E_UNEXPECTED` in this case.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7bbc9-106">구문</span><span class="sxs-lookup"><span data-stu-id="7bbc9-106">Syntax</span></span>  
  
```idl  
HRESULT IsAsyncMethod(    [out, retval] BOOL* pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7bbc9-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7bbc9-107">Parameters</span></span>  
  
|<span data-ttu-id="7bbc9-108">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7bbc9-108">Parameter</span></span>|<span data-ttu-id="7bbc9-109">설명</span><span class="sxs-lookup"><span data-stu-id="7bbc9-109">Description</span></span>|  
|---------------|-----------------|  
|`pRetVal`||  
  
## <a name="return-value"></a><span data-ttu-id="7bbc9-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="7bbc9-110">Return Value</span></span>  
 <span data-ttu-id="7bbc9-111">`HRESULT`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="7bbc9-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7bbc9-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7bbc9-112">Requirements</span></span>  
 <span data-ttu-id="7bbc9-113">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="7bbc9-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7bbc9-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7bbc9-114">See Also</span></span>  
 [<span data-ttu-id="7bbc9-115">ISymUnmanagedAsyncMethod 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7bbc9-115">ISymUnmanagedAsyncMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)
