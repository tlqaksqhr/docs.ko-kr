---
title: ISymUnmanagedMethod::GetOffset 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetOffset
helpviewer_keywords:
- GetOffset method, ISymUnmanagedMethod interface [.NET Framework debugging]
- ISymUnmanagedMethod::GetOffset method [.NET Framework debugging]
ms.assetid: 8bf3cb62-89bf-4159-ad53-de606aba89e8
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6d88e9279f70c36fd8a9c626972e33305cded5fb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33424393"
---
# <a name="isymunmanagedmethodgetoffset-method"></a><span data-ttu-id="301a3-102">ISymUnmanagedMethod::GetOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="301a3-102">ISymUnmanagedMethod::GetOffset Method</span></span>
<span data-ttu-id="301a3-103">문서 내에서 지정된 된 위치에 해당 하는이 메서드 내에서 오프셋을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="301a3-103">Returns the offset within this method that corresponds to a given position within a document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="301a3-104">구문</span><span class="sxs-lookup"><span data-stu-id="301a3-104">Syntax</span></span>  
  
```  
HRESULT GetOffset(  
    [in]  ISymUnmanagedDocument*  document,  
    [in]  ULONG32                 line,  
    [in]  ULONG32                 column,  
    [out, retval] ULONG32*        pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="301a3-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="301a3-105">Parameters</span></span>  
 `document`  
 <span data-ttu-id="301a3-106">[in] 오프셋이 요청 된 문서에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="301a3-106">[in] A pointer to the document for which the offset is requested.</span></span>  
  
 `line`  
 <span data-ttu-id="301a3-107">[in] 오프셋이 요청 된 문서 줄.</span><span class="sxs-lookup"><span data-stu-id="301a3-107">[in] The document line for which the offset is requested.</span></span>  
  
 `column`  
 <span data-ttu-id="301a3-108">[in] 오프셋이 요청 된 문서 열입니다.</span><span class="sxs-lookup"><span data-stu-id="301a3-108">[in] The document column for which the offset is requested.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="301a3-109">[out] 에 대 한 포인터는 `ULONG32` 받는 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="301a3-109">[out] A pointer to a `ULONG32` that receives the offsets.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="301a3-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="301a3-110">Return Value</span></span>  
 <span data-ttu-id="301a3-111">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 기타 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="301a3-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="301a3-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="301a3-112">Requirements</span></span>  
 <span data-ttu-id="301a3-113">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="301a3-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="301a3-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="301a3-114">See Also</span></span>  
 [<span data-ttu-id="301a3-115">ISymUnmanagedMethod 인터페이스</span><span class="sxs-lookup"><span data-stu-id="301a3-115">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
