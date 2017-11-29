---
title: "ISymUnmanagedDocumentWriter::SetSource 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedDocumentWriter.SetSource
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedDocumentWriter::SetSource
helpviewer_keywords:
- ISymUnmanagedDocumentWriter::SetSource method [.NET Framework debugging]
- SetSource method [.NET Framework debugging]
ms.assetid: ea5b9d9f-ff06-4bd3-8de5-6435343aba59
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 74b917ff4c2853eb31625af2ab1d2c64ced613e0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanageddocumentwritersetsource-method"></a><span data-ttu-id="c7922-102">ISymUnmanagedDocumentWriter::SetSource 메서드</span><span class="sxs-lookup"><span data-stu-id="c7922-102">ISymUnmanagedDocumentWriter::SetSource Method</span></span>
<span data-ttu-id="c7922-103">포함 된 쓰고 있는 문서에 대 한 소스를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7922-103">Sets embedded source for a document that is being written.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7922-104">구문</span><span class="sxs-lookup"><span data-stu-id="c7922-104">Syntax</span></span>  
  
```  
HRESULT SetSource(  
    [in]  ULONG32  sourceSize,  
    [in, size_is(sourceSize)] BYTE  source[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c7922-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c7922-105">Parameters</span></span>  
 `sourceSize`  
 <span data-ttu-id="c7922-106">[in] A `ULONG32` 의 크기를 포함 하는 `source` 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="c7922-106">[in] A `ULONG32` that contains the size of the `source` buffer.</span></span>  
  
 `source`  
 <span data-ttu-id="c7922-107">[in] 포함된 된 소스를 저장 하는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="c7922-107">[in] The buffer that stores the embedded source.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c7922-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="c7922-108">Return Value</span></span>  
 <span data-ttu-id="c7922-109">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 기타 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="c7922-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c7922-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c7922-110">Requirements</span></span>  
 <span data-ttu-id="c7922-111">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="c7922-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7922-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c7922-112">See Also</span></span>  
 [<span data-ttu-id="c7922-113">ISymUnmanagedDocumentWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c7922-113">ISymUnmanagedDocumentWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocumentwriter-interface.md)
