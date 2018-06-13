---
title: ISymUnmanagedConstant::GetValue 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedConstant.GetValue
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedConstant::GetValue
helpviewer_keywords:
- GetValue method, ISymUnmanagedConstant interface [.NET Framework debugging]
- ISymUnmanagedConstant::GetValue method [.NET Framework debugging]
ms.assetid: 0036fc10-e768-47a8-b9cf-bf47faf8d194
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f51a41e8f00a0cf88b11078468ba5a8511fd1391
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33424741"
---
# <a name="isymunmanagedconstantgetvalue-method"></a><span data-ttu-id="a799d-102">ISymUnmanagedConstant::GetValue 메서드</span><span class="sxs-lookup"><span data-stu-id="a799d-102">ISymUnmanagedConstant::GetValue Method</span></span>
<span data-ttu-id="a799d-103">상수 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a799d-103">Gets the value of the constant.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a799d-104">구문</span><span class="sxs-lookup"><span data-stu-id="a799d-104">Syntax</span></span>  
  
```  
HRESULT GetValue(  
    [out]  VARIANT* pValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a799d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a799d-105">Parameters</span></span>  
 `pValue`  
 <span data-ttu-id="a799d-106">[out] 포인터 값을 수신 하는 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="a799d-106">[out] A pointer to a variable that receives the value.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a799d-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="a799d-107">Return Value</span></span>  
 <span data-ttu-id="a799d-108">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 기타 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="a799d-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a799d-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a799d-109">Requirements</span></span>  
 <span data-ttu-id="a799d-110">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="a799d-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a799d-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a799d-111">See Also</span></span>  
 [<span data-ttu-id="a799d-112">ISymUnmanagedConstant 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a799d-112">ISymUnmanagedConstant Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-interface.md)  
 [<span data-ttu-id="a799d-113">GetName 메서드</span><span class="sxs-lookup"><span data-stu-id="a799d-113">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-getname-method.md)  
 [<span data-ttu-id="a799d-114">GetSignature 메서드</span><span class="sxs-lookup"><span data-stu-id="a799d-114">GetSignature Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-getsignature-method.md)
