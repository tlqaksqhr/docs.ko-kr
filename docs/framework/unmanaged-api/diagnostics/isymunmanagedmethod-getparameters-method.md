---
title: "ISymUnmanagedMethod::GetParameters 메서드"
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
- ISymUnmanagedMethod.GetParameters
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetParameters
helpviewer_keywords:
- ISymUnmanagedMethod::GetParameters method [.NET Framework debugging]
- GetParameters method [.NET Framework debugging]
ms.assetid: 3a8074f1-facc-4a3f-bb9b-d6574fc2fc74
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1a2e3471b63f819bfe1879b87e42ff9258036356
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedmethodgetparameters-method"></a><span data-ttu-id="b5940-102">ISymUnmanagedMethod::GetParameters 메서드</span><span class="sxs-lookup"><span data-stu-id="b5940-102">ISymUnmanagedMethod::GetParameters Method</span></span>
<span data-ttu-id="b5940-103">이 메서드에 대 한 매개 변수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b5940-103">Gets the parameters for this method.</span></span> <span data-ttu-id="b5940-104">매개 변수는 메서드의 서명 내에서 정의 된 순서 대로 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b5940-104">The parameters are returned in the order in which they are defined within the method's signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5940-105">구문</span><span class="sxs-lookup"><span data-stu-id="b5940-105">Syntax</span></span>  
  
```  
HRESULT GetParameters(  
    [in]  ULONG32  cParams,  
    [out] ULONG32  *pcParams,  
    [out, size_is(cParams),  
        length_is(*pcParams)] ISymUnmanagedVariable*  params[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b5940-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b5940-106">Parameters</span></span>  
 `cParams`  
 <span data-ttu-id="b5940-107">[in] `params` 배열의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="b5940-107">[in] The size of the `params` array.</span></span>  
  
 `pcParams`  
 <span data-ttu-id="b5940-108">[in] 에 대 한 포인터는 `ULONG32` 매개 변수를 포함 하는 데 필요한 버퍼의 크기를 받는 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5940-108">[in] A pointer to a `ULONG32` that receives the size of the buffer that is required to contain the parameters.</span></span>  
  
 `params`  
 <span data-ttu-id="b5940-109">[out] 매개 변수를 받는 버퍼에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="b5940-109">[out] A pointer to the buffer that receives the parameters.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b5940-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="b5940-110">Return Value</span></span>  
 <span data-ttu-id="b5940-111">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 기타 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="b5940-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b5940-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b5940-112">Requirements</span></span>  
 <span data-ttu-id="b5940-113">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="b5940-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5940-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b5940-114">See Also</span></span>  
 [<span data-ttu-id="b5940-115">ISymUnmanagedMethod 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b5940-115">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
