---
title: "ISymUnmanagedDocument::FindClosestLine 메서드"
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
- ISymUnmanagedDocument.FindClosestLine
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::FindClosestLine
helpviewer_keywords:
- FindClosestLine method [.NET Framework debugging]
- ISymUnmanagedDocument::FindClosestLine method [.NET Framework debugging]
ms.assetid: 628f2a04-e529-407d-841e-3b3da219a9cb
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a5467f7d500719e8849b85a57195e98c6eeb7fb3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanageddocumentfindclosestline-method"></a><span data-ttu-id="90d7f-102">ISymUnmanagedDocument::FindClosestLine 메서드</span><span class="sxs-lookup"><span data-stu-id="90d7f-102">ISymUnmanagedDocument::FindClosestLine Method</span></span>
<span data-ttu-id="90d7f-103">시퀀스 포인트가 아닐 수 있는이 문서의 줄이 제공 된 시퀀스 위치가 되는 가장 가까운 줄을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="90d7f-103">Returns the closest line that is a sequence point, given a line in this document that may or may not be a sequence point.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90d7f-104">구문</span><span class="sxs-lookup"><span data-stu-id="90d7f-104">Syntax</span></span>  
  
```  
HRESULT FindClosestLine(  
    [in]  ULONG32  line,  
    [out, retval] ULONG32*  pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="90d7f-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="90d7f-105">Parameters</span></span>  
 `line`  
 <span data-ttu-id="90d7f-106">[in] 이 문서에는 선입니다.</span><span class="sxs-lookup"><span data-stu-id="90d7f-106">[in] A line in this document.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="90d7f-107">[out] 포인터 줄을 수신 하는 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="90d7f-107">[out] A pointer to a variable that receives the line.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="90d7f-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="90d7f-108">Return Value</span></span>  
 <span data-ttu-id="90d7f-109">메서드가 성공 하면 s_ok이 고 그렇지 않으면 오류 코드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="90d7f-109">S_OK if the method succeeds; otherwise, an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90d7f-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="90d7f-110">See Also</span></span>  
 [<span data-ttu-id="90d7f-111">ISymUnmanagedDocument 인터페이스</span><span class="sxs-lookup"><span data-stu-id="90d7f-111">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
