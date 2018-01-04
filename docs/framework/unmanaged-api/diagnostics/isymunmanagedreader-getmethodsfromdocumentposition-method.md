---
title: "ISymUnmanagedReader::GetMethodsFromDocumentPosition 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedReader.GetMethodsFromDocumentPosition
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedReader::GetMethodsFromDocumentPosition
helpviewer_keywords:
- GetMethodsFromDocumentPosition method [.NET Framework debugging]
- ISymUnmanagedReader::GetMethodsFromDocumentPosition method [.NET Framework debugging]
ms.assetid: 83605f1e-e4f3-49e6-859b-f13cad68bb54
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: cdf3762c40e5ec4da84a27ed7abcb15981b81379
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedreadergetmethodsfromdocumentposition-method"></a><span data-ttu-id="f29b6-102">ISymUnmanagedReader::GetMethodsFromDocumentPosition 메서드</span><span class="sxs-lookup"><span data-stu-id="f29b6-102">ISymUnmanagedReader::GetMethodsFromDocumentPosition Method</span></span>
<span data-ttu-id="f29b6-103">문서에서 지정된 된 위치에 중단점을 포함 하며 각 방법의 배열을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="f29b6-103">Returns an array of methods, each of which contains the breakpoint at the given position in a document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f29b6-104">구문</span><span class="sxs-lookup"><span data-stu-id="f29b6-104">Syntax</span></span>  
  
```  
HRESULT GetMethodsFromDocumentPosition (  
    [in]  ISymUnmanagedDocument* document,  
    [in]  ULONG32 line,  
    [in]  ULONG32 column,  
    [in]  ULONG32 cMethod,  
    [out] ULONG32* pcMethod,  
    [out, size_is (cMethod),  
        length_is (*pcMethod)] ISymUnmanagedMethod* pRetVal[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f29b6-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f29b6-105">Parameters</span></span>  
 `document`  
 <span data-ttu-id="f29b6-106">[in] 지정 된 문서입니다.</span><span class="sxs-lookup"><span data-stu-id="f29b6-106">[in] The specified document.</span></span>  
  
 `line`  
 <span data-ttu-id="f29b6-107">[in] 지정된 된 문서 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="f29b6-107">[in] The line of the specified document.</span></span>  
  
 `column`  
 <span data-ttu-id="f29b6-108">[in] 지정된 된 문서 열입니다.</span><span class="sxs-lookup"><span data-stu-id="f29b6-108">[in] The column of the specified document.</span></span>  
  
 `cMethod`  
 <span data-ttu-id="f29b6-109">[in] `pRetVal` 배열의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="f29b6-109">[in] The size of the `pRetVal` array.</span></span>  
  
 `pcMethod`  
 <span data-ttu-id="f29b6-110">[out] 반환 되는 요소 수를 받는 변수에 대 한 포인터는 `pRetVal` 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="f29b6-110">[out] A pointer to a variable that receives the number of elements returned in the `pRetVal` array.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="f29b6-111">[out] 각각 가리키는 포인터의 배열은 [ISymUnmanagedMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md) 중단점을 포함 하는 메서드를 나타내는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="f29b6-111">[out] An array of pointers, each of which points to an [ISymUnmanagedMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md) object that represents a method containing the breakpoint.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f29b6-112">반환 값</span><span class="sxs-lookup"><span data-stu-id="f29b6-112">Return Value</span></span>  
 <span data-ttu-id="f29b6-113">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 기타 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="f29b6-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f29b6-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f29b6-114">Requirements</span></span>  
 <span data-ttu-id="f29b6-115">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="f29b6-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f29b6-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f29b6-116">See Also</span></span>  
 [<span data-ttu-id="f29b6-117">ISymUnmanagedReader 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f29b6-117">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
