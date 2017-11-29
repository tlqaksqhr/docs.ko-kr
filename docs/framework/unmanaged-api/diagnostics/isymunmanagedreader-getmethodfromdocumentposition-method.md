---
title: "ISymUnmanagedReader::GetMethodFromDocumentPosition 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedReader.GetMethodFromDocumentPosition
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedReader::GetMethodFromDocumentPosition
helpviewer_keywords:
- GetMethodFromDocumentPosition method [.NET Framework debugging]
- ISymUnmanagedReader::GetMethodFromDocumentPosition method [.NET Framework debugging]
ms.assetid: 55773dbc-9053-46e3-8a3c-86caa9d91fb4
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: ad64d5722df68859e7be9d44b94b95cf1f43823f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedreadergetmethodfromdocumentposition-method"></a><span data-ttu-id="48b3c-102">ISymUnmanagedReader::GetMethodFromDocumentPosition 메서드</span><span class="sxs-lookup"><span data-stu-id="48b3c-102">ISymUnmanagedReader::GetMethodFromDocumentPosition Method</span></span>
<span data-ttu-id="48b3c-103">문서에서 지정된 된 위치에 중단점을 포함 하는 메서드를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="48b3c-103">Returns the method that contains the breakpoint at the given position in a document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48b3c-104">구문</span><span class="sxs-lookup"><span data-stu-id="48b3c-104">Syntax</span></span>  
  
```  
HRESULT GetMethodFromDocumentPosition (  
    [in]  ISymUnmanagedDocument*  document,  
    [in]  ULONG32  line,  
    [in]  ULONG32  column,  
    [out, retval] ISymUnmanagedMethod**  pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="48b3c-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="48b3c-105">Parameters</span></span>  
 `document`  
 <span data-ttu-id="48b3c-106">[in] 지정 된 문서입니다.</span><span class="sxs-lookup"><span data-stu-id="48b3c-106">[in] The specified document.</span></span>  
  
 `line`  
 <span data-ttu-id="48b3c-107">[in] 지정된 된 문서 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="48b3c-107">[in] The line of the specified document.</span></span>  
  
 `column`  
 <span data-ttu-id="48b3c-108">[in] 지정된 된 문서 열입니다.</span><span class="sxs-lookup"><span data-stu-id="48b3c-108">[in] The column of the specified document.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="48b3c-109">[out] 주소에 대 한 포인터는 [ISymUnmanagedMethod 인터페이스](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md) 중단점을 포함 하는 메서드를 나타내는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="48b3c-109">[out] A pointer to the address of a [ISymUnmanagedMethod Interface](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md) object that represents the method containing the breakpoint.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="48b3c-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="48b3c-110">Return Value</span></span>  
 <span data-ttu-id="48b3c-111">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 기타 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="48b3c-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="48b3c-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="48b3c-112">Requirements</span></span>  
 <span data-ttu-id="48b3c-113">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="48b3c-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48b3c-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="48b3c-114">See Also</span></span>  
 [<span data-ttu-id="48b3c-115">ISymUnmanagedReader 인터페이스</span><span class="sxs-lookup"><span data-stu-id="48b3c-115">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
