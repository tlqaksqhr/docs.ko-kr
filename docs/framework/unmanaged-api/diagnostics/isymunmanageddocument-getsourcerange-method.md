---
title: "ISymUnmanagedDocument::GetSourceRange 메서드"
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
- ISymUnmanagedDocument.GetSourceRange
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::GetSourceRange
helpviewer_keywords:
- ISymUnmanagedDocument::GetSourceRange method [.NET Framework debugging]
- GetSourceRange method [.NET Framework debugging]
ms.assetid: 20fefee7-1040-41ba-93dc-bd42f68b90c2
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: dcddebbca74bb94bd2411038a02b900b2f64f2d5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanageddocumentgetsourcerange-method"></a><span data-ttu-id="320b2-102">ISymUnmanagedDocument::GetSourceRange 메서드</span><span class="sxs-lookup"><span data-stu-id="320b2-102">ISymUnmanagedDocument::GetSourceRange Method</span></span>
<span data-ttu-id="320b2-103">지정 된 버퍼로 포함된 리소스의 지정된 된 범위를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="320b2-103">Returns the specified range of the embedded source into the given buffer.</span></span> <span data-ttu-id="320b2-104">버퍼 소스를 저장할 수 있을 만큼 크기가 커야 합니다.</span><span class="sxs-lookup"><span data-stu-id="320b2-104">The buffer must be large enough to hold the source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="320b2-105">구문</span><span class="sxs-lookup"><span data-stu-id="320b2-105">Syntax</span></span>  
  
```  
HRESULT GetSourceRange(  
    [in]  ULONG32  startLine,  
    [in]  ULONG32  startColumn,  
    [in]  ULONG32  endLine,  
    [in]  ULONG32  endColumn,  
    [in]  ULONG32  cSourceBytes,  
    [out] ULONG32  *pcSourceBytes,  
    [out, size_is(cSourceBytes),  
        length_is(*pcSourceBytes)] BYTE source[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="320b2-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="320b2-106">Parameters</span></span>  
 `startLine`  
 <span data-ttu-id="320b2-107">[in] 현재 문서의 시작 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="320b2-107">[in] The starting line in the current document.</span></span>  
  
 `startColumn`  
 <span data-ttu-id="320b2-108">[in] 현재 문서의 시작 열입니다.</span><span class="sxs-lookup"><span data-stu-id="320b2-108">[in] The starting column in the current document.</span></span>  
  
 `endLine`  
 <span data-ttu-id="320b2-109">[in] 현재 문서에서 마지막 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="320b2-109">[in] The final line in the current document.</span></span>  
  
 `endColumn`  
 <span data-ttu-id="320b2-110">[in] 현재 문서에서 마지막 열입니다.</span><span class="sxs-lookup"><span data-stu-id="320b2-110">[in] The final column in the current document.</span></span>  
  
 `cSourceBytes`  
 <span data-ttu-id="320b2-111">[in] 원본 바이트의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="320b2-111">[in] The size of the source, in bytes.</span></span>  
  
 `pcSourceBytes`  
 <span data-ttu-id="320b2-112">[out] 원본 크기를 받는 변수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="320b2-112">[out] A pointer to a variable that receives the source size.</span></span>  
  
 `source`  
 <span data-ttu-id="320b2-113">[out] 크기와 소스 문서의 바이트 단위로 지정 된 범위의 길이입니다.</span><span class="sxs-lookup"><span data-stu-id="320b2-113">[out] The size and length of the specified range of the source document, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="320b2-114">반환 값</span><span class="sxs-lookup"><span data-stu-id="320b2-114">Return Value</span></span>  
 <span data-ttu-id="320b2-115">메서드가 성공 하면 S_OK입니다.</span><span class="sxs-lookup"><span data-stu-id="320b2-115">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="320b2-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="320b2-116">See Also</span></span>  
 [<span data-ttu-id="320b2-117">ISymUnmanagedDocument 인터페이스</span><span class="sxs-lookup"><span data-stu-id="320b2-117">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
