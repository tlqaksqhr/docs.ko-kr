---
title: "ISymUnmanagedWriter2::DefineConstant2 메서드"
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
- ISymUnmanagedWriter2.DefineConstant2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter2::DefineConstant2
helpviewer_keywords:
- DefineConstant2 method [.NET Framework debugging]
- ISymUnmanagedWriter2::DefineConstant2 method [.NET Framework debugging]
ms.assetid: dd2bc956-7dbe-49fc-a646-daa0d267f2df
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d1b3e5ea28092be1ea8bc2629b4ee6f08cd630b1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedwriter2defineconstant2-method"></a><span data-ttu-id="0028f-102">ISymUnmanagedWriter2::DefineConstant2 메서드</span><span class="sxs-lookup"><span data-stu-id="0028f-102">ISymUnmanagedWriter2::DefineConstant2 Method</span></span>
<span data-ttu-id="0028f-103">상수 값에 대 한 이름을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="0028f-103">Defines a name for a constant value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0028f-104">구문</span><span class="sxs-lookup"><span data-stu-id="0028f-104">Syntax</span></span>  
  
```  
HRESULT DefineConstant2(  
    [in] const WCHAR  *name,  
    [in] VARIANT      value,  
    [in] mdSignature  sigToken);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0028f-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0028f-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="0028f-106">[in] 일정 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="0028f-106">[in] The constant name.</span></span>  
  
 `value`  
 <span data-ttu-id="0028f-107">[in] 상수의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="0028f-107">[in] The value of the constant.</span></span>  
  
 `sigToken`  
 <span data-ttu-id="0028f-108">[in] 상수 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="0028f-108">[in] The metadata token of the constant.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0028f-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="0028f-109">Return Value</span></span>  
 <span data-ttu-id="0028f-110">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 기타 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="0028f-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0028f-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0028f-111">Requirements</span></span>  
 <span data-ttu-id="0028f-112">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="0028f-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0028f-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0028f-113">See Also</span></span>  
 [<span data-ttu-id="0028f-114">ISymUnmanagedWriter2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0028f-114">ISymUnmanagedWriter2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-interface.md)  
 [<span data-ttu-id="0028f-115">DefineConstant 메서드</span><span class="sxs-lookup"><span data-stu-id="0028f-115">DefineConstant Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-defineconstant-method.md)
