---
title: "ISymUnmanagedWriter::DefineSequencePoints 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter.DefineSequencePoints
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter::DefineSequencePoints
helpviewer_keywords:
- DefineSequencePoints method [.NET Framework debugging]
- ISymUnmanagedWriter::DefineSequencePoints method [.NET Framework debugging]
ms.assetid: 64202baf-be6b-40ba-8162-8cc6c0c9b8e1
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2e1dcc427a6d034ce108ca66f71cc24b1050a72f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedwriterdefinesequencepoints-method"></a><span data-ttu-id="1ee98-102">ISymUnmanagedWriter::DefineSequencePoints 메서드</span><span class="sxs-lookup"><span data-stu-id="1ee98-102">ISymUnmanagedWriter::DefineSequencePoints Method</span></span>
<span data-ttu-id="1ee98-103">현재 메서드 내에서 시퀀스 위치 그룹을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="1ee98-103">Defines a group of sequence points within the current method.</span></span> <span data-ttu-id="1ee98-104">각 시작 줄 및 시작 열 메서드 내에서 문의 시작을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ee98-104">Each starting line and starting column define the start of a statement within a method.</span></span> <span data-ttu-id="1ee98-105">각각 끝 줄과 끝 열 메서드 내에서 문의 끝을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ee98-105">Each ending line and ending column define the end of a statement within a method.</span></span> <span data-ttu-id="1ee98-106">배열은 오프셋의 오름차순으로 정렬 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ee98-106">The arrays should be sorted in increasing order of offsets.</span></span> <span data-ttu-id="1ee98-107">오프셋은 항상 바이트 단위로 메서드의 시작 부분에서 측정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1ee98-107">The offset is always measured from the start of the method, in bytes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ee98-108">구문</span><span class="sxs-lookup"><span data-stu-id="1ee98-108">Syntax</span></span>  
  
```  
HRESULT DefineSequencePoints(  
    [in] ISymUnmanagedDocumentWriter*  document,  
    [in] ULONG32 spCount,  
    [in, size_is(spCount)] ULONG32     offsets[],  
    [in, size_is(spCount)] ULONG32     lines[],  
    [in, size_is(spCount)] ULONG32     columns[],  
    [in, size_is(spCount)] ULONG32     endLines[],  
    [in, size_is(spCount)] ULONG32     endColumns[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1ee98-109">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1ee98-109">Parameters</span></span>  
 `document`  
 <span data-ttu-id="1ee98-110">[in] 시퀀스 위치를 정의 하는 문서 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="1ee98-110">[in] The document object for which the sequence points are being defined.</span></span>  
  
 `spCount`  
 <span data-ttu-id="1ee98-111">[in] A `ULONG32` 각각의 크기를 표시 하는 `offsets`, `lines`, `columns`, `endLines`, 및 `endColumns` 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="1ee98-111">[in] A `ULONG32` that that indicates the size of each of the `offsets`, `lines`, `columns`, `endLines`, and `endColumns` buffers.</span></span>  
  
 `offsets`  
 <span data-ttu-id="1ee98-112">[in] 메서드의 시작 부분에서 측정 한 시퀀스 위치 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="1ee98-112">[in] The offset of the sequence points measured from the beginning of the method.</span></span>  
  
 `lines`  
 <span data-ttu-id="1ee98-113">[in] 시퀀스 위치의 시작 줄 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="1ee98-113">[in] The starting line numbers of the sequence points.</span></span>  
  
 `columns`  
 <span data-ttu-id="1ee98-114">[in] 시퀀스 위치의 시작 열 번호를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ee98-114">[in] The starting column numbers of the sequence points.</span></span>  
  
 `endLines`  
 <span data-ttu-id="1ee98-115">[in] 시퀀스 위치의 끝 줄 번호를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ee98-115">[in] The ending line numbers of the sequence points.</span></span> <span data-ttu-id="1ee98-116">이 매개 변수는 선택적 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="1ee98-116">This parameter is optional.</span></span>  
  
 `endColumns`  
 <span data-ttu-id="1ee98-117">[in] 시퀀스 위치의 끝 열 번호를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ee98-117">[in] The ending column numbers of the sequence points.</span></span> <span data-ttu-id="1ee98-118">이 매개 변수는 선택적 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="1ee98-118">This parameter is optional.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1ee98-119">반환 값</span><span class="sxs-lookup"><span data-stu-id="1ee98-119">Return Value</span></span>  
 <span data-ttu-id="1ee98-120">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 기타 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="1ee98-120">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1ee98-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1ee98-121">Requirements</span></span>  
 <span data-ttu-id="1ee98-122">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="1ee98-122">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ee98-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1ee98-123">See Also</span></span>  
 [<span data-ttu-id="1ee98-124">ISymUnmanagedWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1ee98-124">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
