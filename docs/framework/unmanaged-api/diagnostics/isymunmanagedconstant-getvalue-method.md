---
title: "ISymUnmanagedConstant::GetValue 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedConstant.GetValue
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedConstant::GetValue
helpviewer_keywords:
- GetValue method, ISymUnmanagedConstant interface [.NET Framework debugging]
- ISymUnmanagedConstant::GetValue method [.NET Framework debugging]
ms.assetid: 0036fc10-e768-47a8-b9cf-bf47faf8d194
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 15ae3e9f2e680c7e85d3b8daa0d6010773797258
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedconstantgetvalue-method"></a><span data-ttu-id="8bc58-102">ISymUnmanagedConstant::GetValue 메서드</span><span class="sxs-lookup"><span data-stu-id="8bc58-102">ISymUnmanagedConstant::GetValue Method</span></span>
<span data-ttu-id="8bc58-103">상수 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8bc58-103">Gets the value of the constant.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8bc58-104">구문</span><span class="sxs-lookup"><span data-stu-id="8bc58-104">Syntax</span></span>  
  
```  
HRESULT GetValue(  
    [out]  VARIANT* pValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8bc58-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8bc58-105">Parameters</span></span>  
 `pValue`  
 <span data-ttu-id="8bc58-106">[out] 포인터 값을 수신 하는 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="8bc58-106">[out] A pointer to a variable that receives the value.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8bc58-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="8bc58-107">Return Value</span></span>  
 <span data-ttu-id="8bc58-108">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 기타 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="8bc58-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8bc58-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8bc58-109">Requirements</span></span>  
 <span data-ttu-id="8bc58-110">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="8bc58-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8bc58-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8bc58-111">See Also</span></span>  
 [<span data-ttu-id="8bc58-112">ISymUnmanagedConstant 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8bc58-112">ISymUnmanagedConstant Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-interface.md)  
 [<span data-ttu-id="8bc58-113">GetName 메서드</span><span class="sxs-lookup"><span data-stu-id="8bc58-113">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-getname-method.md)  
 [<span data-ttu-id="8bc58-114">GetSignature 메서드</span><span class="sxs-lookup"><span data-stu-id="8bc58-114">GetSignature Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-getsignature-method.md)
