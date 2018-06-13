---
title: ISymUnmanagedDocument::FindClosestLine 메서드
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f31dad53f42fdd8f7ac3a0cb995b507ecc3590d5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33424445"
---
# <a name="isymunmanageddocumentfindclosestline-method"></a><span data-ttu-id="7c7bb-102">ISymUnmanagedDocument::FindClosestLine 메서드</span><span class="sxs-lookup"><span data-stu-id="7c7bb-102">ISymUnmanagedDocument::FindClosestLine Method</span></span>
<span data-ttu-id="7c7bb-103">시퀀스 포인트가 아닐 수 있는이 문서의 줄이 제공 된 시퀀스 위치가 되는 가장 가까운 줄을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c7bb-103">Returns the closest line that is a sequence point, given a line in this document that may or may not be a sequence point.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c7bb-104">구문</span><span class="sxs-lookup"><span data-stu-id="7c7bb-104">Syntax</span></span>  
  
```  
HRESULT FindClosestLine(  
    [in]  ULONG32  line,  
    [out, retval] ULONG32*  pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7c7bb-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7c7bb-105">Parameters</span></span>  
 `line`  
 <span data-ttu-id="7c7bb-106">[in] 이 문서에는 선입니다.</span><span class="sxs-lookup"><span data-stu-id="7c7bb-106">[in] A line in this document.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="7c7bb-107">[out] 포인터 줄을 수신 하는 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="7c7bb-107">[out] A pointer to a variable that receives the line.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7c7bb-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="7c7bb-108">Return Value</span></span>  
 <span data-ttu-id="7c7bb-109">메서드가 성공 하면 s_ok이 고 그렇지 않으면 오류 코드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c7bb-109">S_OK if the method succeeds; otherwise, an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c7bb-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7c7bb-110">See Also</span></span>  
 [<span data-ttu-id="7c7bb-111">ISymUnmanagedDocument 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7c7bb-111">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
