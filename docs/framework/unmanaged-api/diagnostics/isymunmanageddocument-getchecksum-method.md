---
title: "ISymUnmanagedDocument::GetCheckSum 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedDocument.GetCheckSum
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedDocument::GetCheckSum
helpviewer_keywords:
- ISymUnmanagedDocument::GetCheckSum method [.NET Framework debugging]
- GetCheckSum method [.NET Framework debugging]
ms.assetid: 9bc881b3-e2ce-48a7-ad69-17eaaa304120
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: b0b2ce6facf99b44f54e8880d4436ab7fe96e50a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanageddocumentgetchecksum-method"></a><span data-ttu-id="c59a5-102">ISymUnmanagedDocument::GetCheckSum 메서드</span><span class="sxs-lookup"><span data-stu-id="c59a5-102">ISymUnmanagedDocument::GetCheckSum Method</span></span>
<span data-ttu-id="c59a5-103">체크섬을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c59a5-103">Gets the checksum.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c59a5-104">구문</span><span class="sxs-lookup"><span data-stu-id="c59a5-104">Syntax</span></span>  
  
```  
HRESULT GetCheckSum(  
    [in]  ULONG32  cData,  
    [out] ULONG32  *pcData,  
    [out, size_is(cData), length_is(*pcData)] BYTE data[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c59a5-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c59a5-105">Parameters</span></span>  
 `cData`  
 <span data-ttu-id="c59a5-106">[in] 제공 하는 버퍼의 길이 `data` 매개 변수</span><span class="sxs-lookup"><span data-stu-id="c59a5-106">[in] The length of the buffer provided by the `data` parameter</span></span>  
  
 `pcData`  
 <span data-ttu-id="c59a5-107">[out] 크기와 체크섬 바이트 길이입니다.</span><span class="sxs-lookup"><span data-stu-id="c59a5-107">[out] The size and length of the checksum, in bytes.</span></span>  
  
 `data`  
 <span data-ttu-id="c59a5-108">[out] 체크섬을 수신 하는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="c59a5-108">[out] The buffer that receives the checksum.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c59a5-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="c59a5-109">Return Value</span></span>  
 <span data-ttu-id="c59a5-110">메서드가 성공 하면 s_ok이 고 그렇지 않으면 오류 코드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c59a5-110">S_OK if the method succeeds; otherwise, an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c59a5-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c59a5-111">See Also</span></span>  
 [<span data-ttu-id="c59a5-112">ISymUnmanagedDocument 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c59a5-112">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
