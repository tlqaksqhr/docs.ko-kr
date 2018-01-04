---
title: "ISymUnmanagedConstant::GetName 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedConstant.GetName
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedConstant::GetName
helpviewer_keywords:
- ISymUnmanagedConstant::GetName method [.NET Framework debugging]
- GetName method, ISymUnmanagedConstant interface [.NET Framework debugging]
ms.assetid: cbaca4e1-4473-459b-ba34-f1f59ce7c0ba
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d312329a2e59376c94937cf3d9bc08a8e6e0e862
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedconstantgetname-method"></a><span data-ttu-id="648a6-102">ISymUnmanagedConstant::GetName 메서드</span><span class="sxs-lookup"><span data-stu-id="648a6-102">ISymUnmanagedConstant::GetName Method</span></span>
<span data-ttu-id="648a6-103">상수의 이름을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="648a6-103">Gets the name of the constant.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="648a6-104">구문</span><span class="sxs-lookup"><span data-stu-id="648a6-104">Syntax</span></span>  
  
```  
HRESULT GetName(  
    [in]  ULONG32  cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName),  
        length_is(*pcchName)] WCHAR szName[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="648a6-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="648a6-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="648a6-106">[in] 버퍼의 길이는 `szName` 매개 변수를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="648a6-106">[in] The length of the buffer that the `szName` parameter points to.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="648a6-107">[out] 에 대 한 포인터는 `ULONG32` 문자의 null 종결을 포함 하 여 이름을 포함 하는 데 필요한 버퍼 크기를 받는 합니다.</span><span class="sxs-lookup"><span data-stu-id="648a6-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the name, including the null termination.</span></span>  
  
 `szName`  
 <span data-ttu-id="648a6-108">[out] 이름을 저장 하는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="648a6-108">[out] The buffer that stores the name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="648a6-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="648a6-109">Return Value</span></span>  
 <span data-ttu-id="648a6-110">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 기타 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="648a6-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="648a6-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="648a6-111">Requirements</span></span>  
 <span data-ttu-id="648a6-112">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="648a6-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="648a6-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="648a6-113">See Also</span></span>  
 [<span data-ttu-id="648a6-114">ISymUnmanagedConstant 인터페이스</span><span class="sxs-lookup"><span data-stu-id="648a6-114">ISymUnmanagedConstant Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-interface.md)  
 [<span data-ttu-id="648a6-115">GetSignature 메서드</span><span class="sxs-lookup"><span data-stu-id="648a6-115">GetSignature Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-getsignature-method.md)  
 [<span data-ttu-id="648a6-116">GetValue 메서드</span><span class="sxs-lookup"><span data-stu-id="648a6-116">GetValue Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-getvalue-method.md)
