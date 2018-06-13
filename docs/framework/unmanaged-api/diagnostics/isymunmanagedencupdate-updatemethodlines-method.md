---
title: ISymUnmanagedENCUpdate::UpdateMethodLines 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedENCUpdate.UpdateMethodLines
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedENCUpdate::UpdateMethodLines
helpviewer_keywords:
- UpdateMethodLines method [.NET Framework debugging]
- ISymUnmanagedENCUpdate::UpdateMethodLines method [.NET Framework debugging]
ms.assetid: 275ef87b-0b53-49f9-af6b-58506335dc06
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 50d9ac08b01a67df68ff077721ff5421fbc27707
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33424276"
---
# <a name="isymunmanagedencupdateupdatemethodlines-method"></a><span data-ttu-id="2b6f8-102">ISymUnmanagedENCUpdate::UpdateMethodLines 메서드</span><span class="sxs-lookup"><span data-stu-id="2b6f8-102">ISymUnmanagedENCUpdate::UpdateMethodLines Method</span></span>
<span data-ttu-id="2b6f8-103">다시 컴파일되지 않은, 하지만 해당 줄 독립적으로 이동 하는 방법에 대 한 줄 정보를 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b6f8-103">Allows updating the line information for a method that has not been recompiled, but whose lines have moved independently.</span></span> <span data-ttu-id="2b6f8-104">각 문에 대 한 델타 허용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b6f8-104">A delta for each statement is allowed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b6f8-105">구문</span><span class="sxs-lookup"><span data-stu-id="2b6f8-105">Syntax</span></span>  
  
```  
HRESULT UpdateMethodLines(  
    [in]  mdMethodDef  mdMethodToken,  
    [in, size_is(cDeltas)] INT32*  pDeltas,  
    [in]  ULONG        cDeltas);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2b6f8-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2b6f8-106">Parameters</span></span>  
 `mdMethodToken`  
 <span data-ttu-id="2b6f8-107">[in] 메타 데이터 메서드 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="2b6f8-107">[in] The metadata of the method token.</span></span>  
  
 `pDeltas`  
 <span data-ttu-id="2b6f8-108">[in] 배열 `INT32` 델타 메서드가 각 시퀀스 요소를 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="2b6f8-108">[in] An array of `INT32` values that indicates deltas for each sequence point in the method.</span></span>  
  
 `cDeltas`  
 <span data-ttu-id="2b6f8-109">[in] A `ULONG` 크기를 포함 하는 `pDeltas` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="2b6f8-109">[in] A `ULONG` containing the size of the `pDeltas` parameter.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2b6f8-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="2b6f8-110">Return Value</span></span>  
 <span data-ttu-id="2b6f8-111">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 기타 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="2b6f8-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2b6f8-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2b6f8-112">Requirements</span></span>  
 <span data-ttu-id="2b6f8-113">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="2b6f8-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b6f8-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2b6f8-114">See Also</span></span>  
 [<span data-ttu-id="2b6f8-115">ISymUnmanagedENCUpdate 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2b6f8-115">ISymUnmanagedENCUpdate Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-interface.md)
