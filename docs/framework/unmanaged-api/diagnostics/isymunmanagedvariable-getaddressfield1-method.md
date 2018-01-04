---
title: "ISymUnmanagedVariable::GetAddressField1 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedVariable.GetAddressField1
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedVariable::GetAddressField1
helpviewer_keywords:
- GetAddressField1 method [.NET Framework debugging]
- ISymUnmanagedVariable::GetAddressField1 method [.NET Framework debugging]
ms.assetid: 25788ed1-0ce3-4b97-96fc-88f8997812a3
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8085deb0cdb0b16eddfa39663277ceecdde10341
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedvariablegetaddressfield1-method"></a><span data-ttu-id="edd13-102">ISymUnmanagedVariable::GetAddressField1 메서드</span><span class="sxs-lookup"><span data-stu-id="edd13-102">ISymUnmanagedVariable::GetAddressField1 Method</span></span>
<span data-ttu-id="edd13-103">이 변수에 대 한 첫 번째 주소 필드를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="edd13-103">Gets the first address field for this variable.</span></span> <span data-ttu-id="edd13-104">해당 의미 주소의 종류에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="edd13-104">Its meaning depends on the kind of address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="edd13-105">구문</span><span class="sxs-lookup"><span data-stu-id="edd13-105">Syntax</span></span>  
  
```  
HRESULT GetAddressField1(  
    [out, retval] ULONG32* pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="edd13-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="edd13-106">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="edd13-107">[out] 에 대 한 포인터는 `ULONG32` 받는 첫 번째 주소 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="edd13-107">[out] A pointer to a `ULONG32` that receives the first address field.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="edd13-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="edd13-108">Return Value</span></span>  
 <span data-ttu-id="edd13-109">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 기타 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="edd13-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="edd13-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="edd13-110">Requirements</span></span>  
 <span data-ttu-id="edd13-111">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="edd13-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="edd13-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="edd13-112">See Also</span></span>  
 [<span data-ttu-id="edd13-113">ISymUnmanagedVariable 인터페이스</span><span class="sxs-lookup"><span data-stu-id="edd13-113">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)  
 [<span data-ttu-id="edd13-114">GetAddressField2 메서드</span><span class="sxs-lookup"><span data-stu-id="edd13-114">GetAddressField2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield2-method.md)  
 [<span data-ttu-id="edd13-115">GetAddressField3 메서드</span><span class="sxs-lookup"><span data-stu-id="edd13-115">GetAddressField3 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield3-method.md)  
 [<span data-ttu-id="edd13-116">GetAddressKind 메서드</span><span class="sxs-lookup"><span data-stu-id="edd13-116">GetAddressKind Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddresskind-method.md)
