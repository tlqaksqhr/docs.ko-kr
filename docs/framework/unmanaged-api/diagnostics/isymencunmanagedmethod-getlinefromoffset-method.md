---
title: "ISymENCUnmanagedMethod::GetLineFromOffset 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymENCUnmanagedMethod.GetLineFromOffset
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymENCUnmanagedMethod::GetLineFromOffset
helpviewer_keywords:
- GetLineFromOffset method [.NET Framework debugging]
- ISymENCUnmanagedMethod::GetLineFromOffset method [.NET Framework debugging]
ms.assetid: cc09bad2-fb34-4d13-a521-6ec7b1a1d915
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 535c0310a3220c5691f26c9081f6d2f747196e91
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="isymencunmanagedmethodgetlinefromoffset-method"></a><span data-ttu-id="0b319-102">ISymENCUnmanagedMethod::GetLineFromOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="0b319-102">ISymENCUnmanagedMethod::GetLineFromOffset Method</span></span>
<span data-ttu-id="0b319-103">오프셋와 관련 된 줄 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0b319-103">Gets the line information associated with an offset.</span></span> <span data-ttu-id="0b319-104">경우 offset 매개 변수 (`dwOffset`) 시퀀스 위치가 아닙니다.이 메서드는 이전 오프셋과와 관련 된 줄 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0b319-104">If the offset parameter (`dwOffset`) is not a sequence point, this method gets the line information associated with the previous offset.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b319-105">구문</span><span class="sxs-lookup"><span data-stu-id="0b319-105">Syntax</span></span>  
  
```  
HRESULT GetLineFromOffset(  
     [in]  ULONG32   dwOffset,  
     [out] ULONG32*  pline,  
     [out] ULONG32*  pcolumn,  
     [out] ULONG32*  pendLine,  
     [out] ULONG32*  pendColumn,  
     [out] ULONG32*  pdwStartOffset);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0b319-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0b319-106">Parameters</span></span>  
 `dwOffset`  
 <span data-ttu-id="0b319-107">[in] A `ULONG32` 오프셋을 포함 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b319-107">[in] A `ULONG32` that contains the offset.</span></span>  
  
 `pline`  
 <span data-ttu-id="0b319-108">[out] 에 대 한 포인터는 `ULONG32` 줄에 받는입니다.</span><span class="sxs-lookup"><span data-stu-id="0b319-108">[out] A pointer to a `ULONG32` that receives the line.</span></span>  
  
 `pcolumn`  
 <span data-ttu-id="0b319-109">[out] 에 대 한 포인터는 `ULONG32` 을 받는 열입니다.</span><span class="sxs-lookup"><span data-stu-id="0b319-109">[out] A pointer to a `ULONG32` that receives the column.</span></span>  
  
 `pendLine`  
 <span data-ttu-id="0b319-110">[out] 에 대 한 포인터는 `ULONG32` 줄 끝을 받는입니다.</span><span class="sxs-lookup"><span data-stu-id="0b319-110">[out] A pointer to a `ULONG32` that receives the end line.</span></span>  
  
 `pendColumn`  
 <span data-ttu-id="0b319-111">[out] 에 대 한 포인터는 `ULONG32` 받는 끝 열입니다.</span><span class="sxs-lookup"><span data-stu-id="0b319-111">[out] A pointer to a `ULONG32` that receives the end column.</span></span>  
  
 `pdwStartOffset`  
 <span data-ttu-id="0b319-112">[out] 에 대 한 포인터는 `ULONG32` 연결된 된 시퀀스 위치를 받는입니다.</span><span class="sxs-lookup"><span data-stu-id="0b319-112">[out] A pointer to a `ULONG32` that receives the associated sequence point.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0b319-113">반환 값</span><span class="sxs-lookup"><span data-stu-id="0b319-113">Return Value</span></span>  
 <span data-ttu-id="0b319-114">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 기타 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="0b319-114">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0b319-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0b319-115">Requirements</span></span>  
 <span data-ttu-id="0b319-116">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="0b319-116">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b319-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0b319-117">See Also</span></span>  
 [<span data-ttu-id="0b319-118">ISymENCUnmanagedMethod 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0b319-118">ISymENCUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-interface.md)
