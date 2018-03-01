---
title: "ISymENCUnmanagedMethod::GetDocumentsForMethodCount 메서드"
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
- ISymENCUnmanagedMethod.GetDocumentsForMethodCount
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymENCUnmanagedMethod::GetDocumentsForMethodCount
helpviewer_keywords:
- GetDocumentsForMethodCount method [.NET Framework debugging]
- ISymENCUnmanagedMethod::GetDocumentsForMethodCount method [.NET Framework debugging]
ms.assetid: cc1a823a-3ff3-4a33-b641-96edc93d2b17
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 804c760c22860aa3f9ded6c8a8fa9ad9b011e9a3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="isymencunmanagedmethodgetdocumentsformethodcount-method"></a><span data-ttu-id="43e09-102">ISymENCUnmanagedMethod::GetDocumentsForMethodCount 메서드</span><span class="sxs-lookup"><span data-stu-id="43e09-102">ISymENCUnmanagedMethod::GetDocumentsForMethodCount Method</span></span>
<span data-ttu-id="43e09-103">이 메서드에 문서 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="43e09-103">Gets the number of documents that this method has lines in.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43e09-104">구문</span><span class="sxs-lookup"><span data-stu-id="43e09-104">Syntax</span></span>  
  
```  
HRESULT GetDocumentsForMethodCount(  
    [out, retval] ULONG32* pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="43e09-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="43e09-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="43e09-106">[out] 에 대 한 포인터는 `ULONG32` 문서를 포함 하는 데 필요한 버퍼의 크기를 받는 합니다.</span><span class="sxs-lookup"><span data-stu-id="43e09-106">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the documents.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="43e09-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="43e09-107">Return Value</span></span>  
 <span data-ttu-id="43e09-108">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 기타 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="43e09-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="43e09-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="43e09-109">Requirements</span></span>  
 <span data-ttu-id="43e09-110">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="43e09-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43e09-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="43e09-111">See Also</span></span>  
 [<span data-ttu-id="43e09-112">ISymENCUnmanagedMethod 인터페이스</span><span class="sxs-lookup"><span data-stu-id="43e09-112">ISymENCUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-interface.md)
