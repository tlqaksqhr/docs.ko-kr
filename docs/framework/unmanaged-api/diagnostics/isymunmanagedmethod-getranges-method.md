---
title: ISymUnmanagedMethod::GetRanges 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetRanges
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetRanges
helpviewer_keywords:
- ISymUnmanagedMethod::GetRanges method [.NET Framework debugging]
- GetRanges method [.NET Framework debugging]
ms.assetid: a85283d8-379c-417a-9736-ddeeef9bcf50
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 32036058924aaf79fa7282144ced75040bc1f825
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33426022"
---
# <a name="isymunmanagedmethodgetranges-method"></a><span data-ttu-id="cb3cc-102">ISymUnmanagedMethod::GetRanges 메서드</span><span class="sxs-lookup"><span data-stu-id="cb3cc-102">ISymUnmanagedMethod::GetRanges Method</span></span>
<span data-ttu-id="cb3cc-103">제공 되는 위치가 문서에는 위치가이 메서드에 설명 되어 있는 Microsoft intermediate language (MSIL)의 범위에 해당 하는 시작 및 종료 오프셋된 쌍의 배열을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb3cc-103">Given a position in a document, returns an array of start and end offset pairs that correspond to the ranges of Microsoft intermediate language (MSIL) that the position covers within this method.</span></span> <span data-ttu-id="cb3cc-104">배열 정수 배열이 고 [시작, 끝, 시작, 끝] 형식.</span><span class="sxs-lookup"><span data-stu-id="cb3cc-104">The array is an array of integers and has the format [start, end, start, end].</span></span> <span data-ttu-id="cb3cc-105">범위 쌍의 수에는 2로 나눈 값 배열의 길이입니다.</span><span class="sxs-lookup"><span data-stu-id="cb3cc-105">The number of range pairs is the length of the array divided by 2.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb3cc-106">구문</span><span class="sxs-lookup"><span data-stu-id="cb3cc-106">Syntax</span></span>  
  
```  
HRESULT GetRanges(  
    [in]  ISymUnmanagedDocument* document,  
    [in]  ULONG32                line,  
    [in]  ULONG32                column,  
    [in]  ULONG32                cRanges,  
    [out] ULONG32                *pcRanges,  
    [out, size_is(cRanges),  
        length_is(*pcRanges)] ULONG32 ranges[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cb3cc-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cb3cc-107">Parameters</span></span>  
 `document`  
 <span data-ttu-id="cb3cc-108">[in] 오프셋이 요청 된 문서입니다.</span><span class="sxs-lookup"><span data-stu-id="cb3cc-108">[in] The document for which the offset is requested.</span></span>  
  
 `line`  
 <span data-ttu-id="cb3cc-109">[in] 범위에 해당 하는 문서 줄.</span><span class="sxs-lookup"><span data-stu-id="cb3cc-109">[in] The document line corresponding to the ranges.</span></span>  
  
 `column`  
 <span data-ttu-id="cb3cc-110">[in] 범위에 해당 하는 문서 열입니다.</span><span class="sxs-lookup"><span data-stu-id="cb3cc-110">[in] The document column corresponding to the ranges.</span></span>  
  
 `cRanges`  
 <span data-ttu-id="cb3cc-111">[in] `ranges` 배열의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="cb3cc-111">[in] The size of the `ranges` array.</span></span>  
  
 `pcRanges`  
 <span data-ttu-id="cb3cc-112">[out] 에 대 한 포인터는 `ULONG32` 범위를 포함 하는 데 필요한 버퍼의 크기를 받는 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb3cc-112">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the ranges.</span></span>  
  
 `ranges`  
 <span data-ttu-id="cb3cc-113">[out] 범위를 받는 버퍼에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="cb3cc-113">[out] A pointer to the buffer that receives the ranges.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cb3cc-114">반환 값</span><span class="sxs-lookup"><span data-stu-id="cb3cc-114">Return Value</span></span>  
 <span data-ttu-id="cb3cc-115">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 기타 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="cb3cc-115">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cb3cc-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cb3cc-116">Requirements</span></span>  
 <span data-ttu-id="cb3cc-117">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="cb3cc-117">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb3cc-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cb3cc-118">See Also</span></span>  
 [<span data-ttu-id="cb3cc-119">ISymUnmanagedMethod 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cb3cc-119">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
