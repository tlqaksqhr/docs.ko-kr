---
title: ISymUnmanagedDocument::HasEmbeddedSource 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.HasEmbeddedSource
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::HasEmbeddedSource
helpviewer_keywords:
- HasEmbeddedSource method [.NET Framework debugging]
- ISymUnmanagedDocument::HasEmbeddedSource method [.NET Framework debugging]
ms.assetid: 385fc4d3-365c-4645-b7b0-6c4c5344b79f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 350aecb9f9c99c9aa44ae6df6d31c7cb69ae5760
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33430347"
---
# <a name="isymunmanageddocumenthasembeddedsource-method"></a><span data-ttu-id="1a974-102">ISymUnmanagedDocument::HasEmbeddedSource 메서드</span><span class="sxs-lookup"><span data-stu-id="1a974-102">ISymUnmanagedDocument::HasEmbeddedSource Method</span></span>
<span data-ttu-id="1a974-103">반환 `true` 문서 소스 디버깅 기호;에 대해 포함 된 경우는 그렇지 않으면 반환 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="1a974-103">Returns `true` if the document has source embedded in the debugging symbols; otherwise, returns `false`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1a974-104">구문</span><span class="sxs-lookup"><span data-stu-id="1a974-104">Syntax</span></span>  
  
```  
HRESULT HasEmbeddedSource(  
   [out, retval]  BOOL  *pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1a974-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1a974-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="1a974-106">[out] 문서 소스 디버깅 기호에 포함 되어 있는지 여부를 나타내는 변수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="1a974-106">[out] A pointer to a variable that indicates whether the document has source embedded in the debugging symbols.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1a974-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="1a974-107">Return Value</span></span>  
 <span data-ttu-id="1a974-108">메서드가 성공 하면 S_OK입니다.</span><span class="sxs-lookup"><span data-stu-id="1a974-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a974-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1a974-109">See Also</span></span>  
 [<span data-ttu-id="1a974-110">ISymUnmanagedDocument 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1a974-110">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
