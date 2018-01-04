---
title: "ISymUnmanagedDocument::GetSourceLength 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedDocument.GetSourceLength
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedDocument::GetSourceLength
helpviewer_keywords:
- GetSourceLength method [.NET Framework debugging]
- ISymUnmanagedDocument::GetSourceLength method [.NET Framework debugging]
ms.assetid: e087dbbb-f4fb-4fbe-8292-e4f1a14d0df2
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 61d9bd99a08f428993f38fb5b6889c9659607782
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanageddocumentgetsourcelength-method"></a><span data-ttu-id="18153-102">ISymUnmanagedDocument::GetSourceLength 메서드</span><span class="sxs-lookup"><span data-stu-id="18153-102">ISymUnmanagedDocument::GetSourceLength Method</span></span>
<span data-ttu-id="18153-103">포함 소스의 길이(바이트)를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="18153-103">Gets the length, in bytes, of the embedded source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18153-104">구문</span><span class="sxs-lookup"><span data-stu-id="18153-104">Syntax</span></span>  
  
```  
HRESULT GetSourceLength(  
    [out, retval]  ULONG32*  pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="18153-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="18153-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="18153-106">[out] 포함 소스의 길이 (바이트)를 나타내는 변수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="18153-106">[out] A pointer to a variable that indicates the length, in bytes, of the embedded source.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="18153-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="18153-107">Return Value</span></span>  
 <span data-ttu-id="18153-108">메서드가 성공 하면 S_OK입니다.</span><span class="sxs-lookup"><span data-stu-id="18153-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18153-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="18153-109">See Also</span></span>  
 [<span data-ttu-id="18153-110">ISymUnmanagedDocument 인터페이스</span><span class="sxs-lookup"><span data-stu-id="18153-110">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
