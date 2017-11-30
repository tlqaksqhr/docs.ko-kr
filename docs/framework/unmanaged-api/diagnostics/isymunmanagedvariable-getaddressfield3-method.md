---
title: "ISymUnmanagedVariable::GetAddressField3 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedVariable.GetAddressField3
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedVariable::GetAddressField3
helpviewer_keywords:
- ISymUnmanagedVariable::GetAddressField3 method [.NET Framework debugging]
- GetAddressField3 method [.NET Framework debugging]
ms.assetid: 4d834721-ad8d-439d-b356-c6b4aef022fc
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 1dfeb3f02b0c767dfc200a625fa4c617692dc11f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="isymunmanagedvariablegetaddressfield3-method"></a><span data-ttu-id="064ed-102">ISymUnmanagedVariable::GetAddressField3 메서드</span><span class="sxs-lookup"><span data-stu-id="064ed-102">ISymUnmanagedVariable::GetAddressField3 Method</span></span>
<span data-ttu-id="064ed-103">이 변수에 대 한 세 번째 주소 필드를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="064ed-103">Gets the third address field for this variable.</span></span> <span data-ttu-id="064ed-104">해당 의미 주소의 종류에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="064ed-104">Its meaning depends on the kind of address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="064ed-105">구문</span><span class="sxs-lookup"><span data-stu-id="064ed-105">Syntax</span></span>  
  
```  
HRESULT GetAddressField3(  
    [out, retval] ULONG32* pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="064ed-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="064ed-106">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="064ed-107">[out] 에 대 한 포인터는 `ULONG32` 세 번째 필드에 주소를 받는입니다.</span><span class="sxs-lookup"><span data-stu-id="064ed-107">[out] A pointer to a `ULONG32` that receives the third address field.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="064ed-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="064ed-108">Return Value</span></span>  
 <span data-ttu-id="064ed-109">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 기타 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="064ed-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="064ed-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="064ed-110">Requirements</span></span>  
 <span data-ttu-id="064ed-111">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="064ed-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="064ed-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="064ed-112">See Also</span></span>  
 [<span data-ttu-id="064ed-113">ISymUnmanagedVariable 인터페이스</span><span class="sxs-lookup"><span data-stu-id="064ed-113">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)  
 [<span data-ttu-id="064ed-114">GetAddressField1 메서드</span><span class="sxs-lookup"><span data-stu-id="064ed-114">GetAddressField1 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield1-method.md)  
 [<span data-ttu-id="064ed-115">GetAddressField2 메서드</span><span class="sxs-lookup"><span data-stu-id="064ed-115">GetAddressField2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield2-method.md)  
 [<span data-ttu-id="064ed-116">GetAddressKind 메서드</span><span class="sxs-lookup"><span data-stu-id="064ed-116">GetAddressKind Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddresskind-method.md)
