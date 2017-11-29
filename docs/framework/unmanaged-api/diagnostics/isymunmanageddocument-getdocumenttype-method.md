---
title: "ISymUnmanagedDocument::GetDocumentType 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedDocument.GetDocumentType
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedDocument::GetDocumentType
helpviewer_keywords:
- ISymUnmanagedDocument::GetDocumentType method [.NET Framework debugging]
- GetDocumentType method [.NET Framework debugging]
ms.assetid: 2d381ab1-7e7c-4281-af2b-e54d879b3ef8
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 71b173562412a185b562e86045456a3ce781f4c9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanageddocumentgetdocumenttype-method"></a><span data-ttu-id="8adf4-102">ISymUnmanagedDocument::GetDocumentType 메서드</span><span class="sxs-lookup"><span data-stu-id="8adf4-102">ISymUnmanagedDocument::GetDocumentType Method</span></span>
<span data-ttu-id="8adf4-103">이 문서의 문서 유형을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8adf4-103">Gets the document type of this document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8adf4-104">구문</span><span class="sxs-lookup"><span data-stu-id="8adf4-104">Syntax</span></span>  
  
```  
HRESULT GetDocumentType(  
    [out, retval] GUID*  pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8adf4-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8adf4-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="8adf4-106">[out] 문서 종류를 수신 하는 변수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="8adf4-106">[out] Pointer to a variable that receives the document type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8adf4-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="8adf4-107">Return Value</span></span>  
 <span data-ttu-id="8adf4-108">메서드가 성공 하면 S_OK입니다.</span><span class="sxs-lookup"><span data-stu-id="8adf4-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8adf4-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8adf4-109">See Also</span></span>  
 [<span data-ttu-id="8adf4-110">ISymUnmanagedDocument 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8adf4-110">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
