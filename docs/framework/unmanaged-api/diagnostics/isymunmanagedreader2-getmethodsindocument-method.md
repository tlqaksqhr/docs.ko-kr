---
title: ISymUnmanagedReader2::GetMethodsInDocument 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader2.GetMethodsInDocument
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader2::GetMethodsInDocument
helpviewer_keywords:
- ISymUnmanagedReader2::GetMethodsInDocument method [.NET Framework debugging]
- GetMethodsInDocument method [.NET Framework debugging]
ms.assetid: c7ae84d6-81e8-4cb7-a1f9-d48b6cde5d79
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 762649e260817c43291de416d2f1a92a8f03afb5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33427371"
---
# <a name="isymunmanagedreader2getmethodsindocument-method"></a><span data-ttu-id="37ff2-102">ISymUnmanagedReader2::GetMethodsInDocument 메서드</span><span class="sxs-lookup"><span data-stu-id="37ff2-102">ISymUnmanagedReader2::GetMethodsInDocument Method</span></span>
<span data-ttu-id="37ff2-103">줄 정보를 제공된 된 문서에 있는 모든 메서드를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="37ff2-103">Gets every method that has line information in the provided document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="37ff2-104">구문</span><span class="sxs-lookup"><span data-stu-id="37ff2-104">Syntax</span></span>  
  
```  
HRESULT GetMethodsInDocument(  
    [in]  ISymUnmanagedDocument *document,  
    [in]  ULONG32 cMethod,  
    [out] ULONG32* pcMethod,  
    [out, size_is(cMethod),  
        length_is(*pcMethod)] ISymUnmanagedMethod* pRetVal[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="37ff2-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="37ff2-105">Parameters</span></span>  
 `document`  
 <span data-ttu-id="37ff2-106">[in] 문서에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="37ff2-106">[in] A pointer to the document.</span></span>  
  
 `cMethod`  
 <span data-ttu-id="37ff2-107">[in] A `ULONG32` 크기를 표시 하는 `pRetVal` 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="37ff2-107">[in] A `ULONG32` that indicates the size of the  `pRetVal` array.</span></span>  
  
 `pcMethod`  
 <span data-ttu-id="37ff2-108">[out] 에 대 한 포인터는 `ULONG32` 메서드를 포함 하는 데 필요한 버퍼의 크기를 받는 합니다.</span><span class="sxs-lookup"><span data-stu-id="37ff2-108">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the methods.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="37ff2-109">[out] 메서드를 수신 하는 버퍼에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="37ff2-109">[out] A pointer to the buffer that receives the methods.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="37ff2-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="37ff2-110">Return Value</span></span>  
 <span data-ttu-id="37ff2-111">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 기타 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="37ff2-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="37ff2-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="37ff2-112">Requirements</span></span>  
 <span data-ttu-id="37ff2-113">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="37ff2-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37ff2-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="37ff2-114">See Also</span></span>  
 [<span data-ttu-id="37ff2-115">ISymUnmanagedReader2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="37ff2-115">ISymUnmanagedReader2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-interface.md)
