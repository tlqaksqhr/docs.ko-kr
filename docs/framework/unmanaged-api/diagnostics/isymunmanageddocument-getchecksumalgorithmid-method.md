---
title: "ISymUnmanagedDocument::GetCheckSumAlgorithmId 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedDocument.GetCheckSumAlgorithmId
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedDocument::GetCheckSumAlgorithmId
helpviewer_keywords:
- ISymUnmanagedDocument::GetCheckSumAlgorithmId method [.NET Framework debugging]
- GetCheckSumAlgorithmId method [.NET Framework debugging]
ms.assetid: c7f941cd-e25b-4b85-b1ce-5f77c9208fa9
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 268951d70fec1096fc9cafaeeb6da3b83bc0acf2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanageddocumentgetchecksumalgorithmid-method"></a><span data-ttu-id="c36c3-102">ISymUnmanagedDocument::GetCheckSumAlgorithmId 메서드</span><span class="sxs-lookup"><span data-stu-id="c36c3-102">ISymUnmanagedDocument::GetCheckSumAlgorithmId Method</span></span>
<span data-ttu-id="c36c3-103">체크섬이 없는 경우에 모두 0으로 GUID를 반환 하거나 체크섬 알고리즘 식별자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c36c3-103">Gets the checksum algorithm identifier, or returns a GUID of all zeros if there is no checksum.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c36c3-104">구문</span><span class="sxs-lookup"><span data-stu-id="c36c3-104">Syntax</span></span>  
  
```  
HRESULT GetCheckSumAlgorithmId(  
    [out, retval] GUID*  pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c36c3-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c36c3-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="c36c3-106">[out] 체크섬 알고리즘 식별자를 수신 하는 변수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="c36c3-106">[out] A pointer to a variable that receives the checksum algorithm identifier.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c36c3-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="c36c3-107">Return Value</span></span>  
 <span data-ttu-id="c36c3-108">메서드가 성공 하면 S_OK입니다.</span><span class="sxs-lookup"><span data-stu-id="c36c3-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c36c3-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c36c3-109">See Also</span></span>  
 [<span data-ttu-id="c36c3-110">ISymUnmanagedDocument 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c36c3-110">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
