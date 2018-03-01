---
title: "ISymENCUnmanagedMethod::GetFileNameFromOffset 메서드"
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
- ISymENCUnmanagedMethod.GetFileNameFromOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymENCUnmanagedMethod::GetFileNameFromOffset
helpviewer_keywords:
- GetFileNameFromOffset method [.NET Framework debugging]
- ISymENCUnmanagedMethod::GetFileNameFromOffset method [.NET Framework debugging]
ms.assetid: 00e2e194-12f5-436e-a997-2b9d3e844d4f
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 5f4b760f2782cf75cf0ab0879eb77e185a93b8b2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="isymencunmanagedmethodgetfilenamefromoffset-method"></a><span data-ttu-id="05688-102">ISymENCUnmanagedMethod::GetFileNameFromOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="05688-102">ISymENCUnmanagedMethod::GetFileNameFromOffset Method</span></span>
<span data-ttu-id="05688-103">오프셋와 관련 된 선에 대 한 파일 이름을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="05688-103">Gets the file name for the line associated with an offset.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05688-104">구문</span><span class="sxs-lookup"><span data-stu-id="05688-104">Syntax</span></span>  
  
```  
HRESULT GetFileNameFromOffset(  
    [in]  ULONG32  dwOffset,  
    [in]  ULONG32  cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName),  
       length_is(*pcchName)] WCHAR szName[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="05688-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="05688-105">Parameters</span></span>  
 `dwOffset`  
 <span data-ttu-id="05688-106">[in] A `ULONG32` 오프셋을 포함 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="05688-106">[in] A `ULONG32` that contains the offset.</span></span>  
  
 `cchName`  
 <span data-ttu-id="05688-107">[in] A `ULONG32` 크기를 표시 하는 `szName` 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="05688-107">[in] A `ULONG32` that indicates the size of the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="05688-108">[out] 에 대 한 포인터는 `ULONG32` 문자의 파일 이름을 포함 하는 데 필요한 버퍼 크기를 받는 합니다.</span><span class="sxs-lookup"><span data-stu-id="05688-108">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the file names.</span></span>  
  
 `szName`  
 <span data-ttu-id="05688-109">[out] 파일 이름을 포함 하는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="05688-109">[out] The buffer that contains the file names.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="05688-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="05688-110">Return Value</span></span>  
 <span data-ttu-id="05688-111">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 기타 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="05688-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="05688-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="05688-112">Requirements</span></span>  
 <span data-ttu-id="05688-113">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="05688-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05688-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="05688-114">See Also</span></span>  
 [<span data-ttu-id="05688-115">ISymENCUnmanagedMethod 인터페이스</span><span class="sxs-lookup"><span data-stu-id="05688-115">ISymENCUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-interface.md)
