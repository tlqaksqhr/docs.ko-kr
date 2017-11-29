---
title: "ISymUnmanagedDocument::HasEmbeddedSource 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedDocument.HasEmbeddedSource
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedDocument::HasEmbeddedSource
helpviewer_keywords:
- HasEmbeddedSource method [.NET Framework debugging]
- ISymUnmanagedDocument::HasEmbeddedSource method [.NET Framework debugging]
ms.assetid: 385fc4d3-365c-4645-b7b0-6c4c5344b79f
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 383b2070dcc5407e6033021cef20beed19319e65
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanageddocumenthasembeddedsource-method"></a><span data-ttu-id="c7043-102">ISymUnmanagedDocument::HasEmbeddedSource 메서드</span><span class="sxs-lookup"><span data-stu-id="c7043-102">ISymUnmanagedDocument::HasEmbeddedSource Method</span></span>
<span data-ttu-id="c7043-103">반환 `true` 문서 소스 디버깅 기호;에 대해 포함 된 경우는 그렇지 않으면 반환 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="c7043-103">Returns `true` if the document has source embedded in the debugging symbols; otherwise, returns `false`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7043-104">구문</span><span class="sxs-lookup"><span data-stu-id="c7043-104">Syntax</span></span>  
  
```  
HRESULT HasEmbeddedSource(  
   [out, retval]  BOOL  *pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c7043-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c7043-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="c7043-106">[out] 문서 소스 디버깅 기호에 포함 되어 있는지 여부를 나타내는 변수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="c7043-106">[out] A pointer to a variable that indicates whether the document has source embedded in the debugging symbols.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c7043-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="c7043-107">Return Value</span></span>  
 <span data-ttu-id="c7043-108">메서드가 성공 하면 S_OK입니다.</span><span class="sxs-lookup"><span data-stu-id="c7043-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7043-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c7043-109">See Also</span></span>  
 [<span data-ttu-id="c7043-110">ISymUnmanagedDocument 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c7043-110">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
