---
title: "ISymUnmanagedSymbolSearchInfo::GetHRESULT 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedSymbolSearchInfo.GetHRESULT
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedSymbolSearchInfo::GetHRESULT
helpviewer_keywords:
- ISymUnmanagedSymbolSearchInfo::GetHRESULT method [.NET Framework debugging]
- GetHRESULT method [.NET Framework debugging]
ms.assetid: 6999dc3d-65d7-4bf6-bb0a-6efc0fc72588
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c4987aeff8a5006bad93db72a04c4195b40ab1a4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedsymbolsearchinfogethresult-method"></a><span data-ttu-id="0fea1-102">ISymUnmanagedSymbolSearchInfo::GetHRESULT 메서드</span><span class="sxs-lookup"><span data-stu-id="0fea1-102">ISymUnmanagedSymbolSearchInfo::GetHRESULT Method</span></span>
<span data-ttu-id="0fea1-103">HRESULT를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0fea1-103">Gets the HRESULT.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0fea1-104">구문</span><span class="sxs-lookup"><span data-stu-id="0fea1-104">Syntax</span></span>  
  
```  
HRESULT GetHRESULT(  
    [out] HRESULT *phr);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0fea1-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0fea1-105">Parameters</span></span>  
 `phr`  
 <span data-ttu-id="0fea1-106">[out] HRESULT에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="0fea1-106">[out] A pointer to the HRESULT.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0fea1-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="0fea1-107">Return Value</span></span>  
 <span data-ttu-id="0fea1-108">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 기타 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="0fea1-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0fea1-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0fea1-109">Requirements</span></span>  
 <span data-ttu-id="0fea1-110">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="0fea1-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0fea1-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0fea1-111">See Also</span></span>  
 [<span data-ttu-id="0fea1-112">ISymUnmanagedSymbolSearchInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0fea1-112">ISymUnmanagedSymbolSearchInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-interface.md)
