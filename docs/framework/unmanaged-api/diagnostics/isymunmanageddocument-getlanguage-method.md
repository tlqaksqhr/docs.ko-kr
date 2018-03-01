---
title: "ISymUnmanagedDocument::GetLanguage 메서드"
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
- ISymUnmanagedDocument.GetLanguage
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::GetLanguage
helpviewer_keywords:
- ISymUnmanagedDocument::GetLanguage method [.NET Framework debugging]
- GetLanguage method [.NET Framework debugging]
ms.assetid: c6639418-e9f2-4a99-8ce2-ec9876e0bc79
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 31fdd2caaf877372fa28693cdc5b09ddf601427c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanageddocumentgetlanguage-method"></a><span data-ttu-id="35309-102">ISymUnmanagedDocument::GetLanguage 메서드</span><span class="sxs-lookup"><span data-stu-id="35309-102">ISymUnmanagedDocument::GetLanguage Method</span></span>
<span data-ttu-id="35309-103">이 문서의 언어 식별자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="35309-103">Gets the language identifier of this document</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35309-104">구문</span><span class="sxs-lookup"><span data-stu-id="35309-104">Syntax</span></span>  
  
```  
HRESULT GetLanguage(  
    [out, retval]  GUID*  pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="35309-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="35309-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="35309-106">[out] 언어 식별자를 수신 하는 변수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="35309-106">[out] A pointer to a variable that receives the language identifier.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="35309-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="35309-107">Return Value</span></span>  
 <span data-ttu-id="35309-108">메서드가 성공 하면 S_OK입니다.</span><span class="sxs-lookup"><span data-stu-id="35309-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35309-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="35309-109">See Also</span></span>  
 [<span data-ttu-id="35309-110">ISymUnmanagedDocument 인터페이스</span><span class="sxs-lookup"><span data-stu-id="35309-110">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
