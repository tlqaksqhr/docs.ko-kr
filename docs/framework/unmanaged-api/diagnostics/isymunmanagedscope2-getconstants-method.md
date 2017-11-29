---
title: "ISymUnmanagedScope2::GetConstants 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedScope2.GetConstants
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedScope2::GetConstants
helpviewer_keywords:
- ISymUnmanagedScope2::GetConstants method [.NET Framework debugging]
- GetConstants method [.NET Framework debugging]
ms.assetid: f241b620-9ec5-42fd-92ef-3b22329db72a
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 4287e34828662840d1bac0d565c0d642e21de6c9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedscope2getconstants-method"></a><span data-ttu-id="d46ce-102">ISymUnmanagedScope2::GetConstants 메서드</span><span class="sxs-lookup"><span data-stu-id="d46ce-102">ISymUnmanagedScope2::GetConstants Method</span></span>
<span data-ttu-id="d46ce-103">이 범위 내에 정의 된 지역 상수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d46ce-103">Gets the local constants defined within this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d46ce-104">구문</span><span class="sxs-lookup"><span data-stu-id="d46ce-104">Syntax</span></span>  
  
```  
HRESULT GetConstants(  
     [in]  ULONG32  cConstants,  
     [out] ULONG32  *pcConstants,  
     [out, size_is(cConstants),  
         length_is(*pcConstants)] ISymUnmanagedConstant*   
             constants[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d46ce-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d46ce-105">Parameters</span></span>  
 `cConstants`  
 <span data-ttu-id="d46ce-106">[in] 버퍼의 길이는 `pcConstants` 매개 변수를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="d46ce-106">[in] The length of the buffer that the `pcConstants` parameter points to.</span></span>  
  
 `pcConstants`  
 <span data-ttu-id="d46ce-107">[out] 에 대 한 포인터는 `ULONG32` 문자 상수를 포함 하는 데 필요한 버퍼 크기를 받는 합니다.</span><span class="sxs-lookup"><span data-stu-id="d46ce-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the constants.</span></span>  
  
 `constants`  
 <span data-ttu-id="d46ce-108">[out] 상수를 저장 하는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="d46ce-108">[out] The buffer that stores the constants.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d46ce-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="d46ce-109">Return Value</span></span>  
 <span data-ttu-id="d46ce-110">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 기타 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="d46ce-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d46ce-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d46ce-111">Requirements</span></span>  
 <span data-ttu-id="d46ce-112">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="d46ce-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d46ce-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d46ce-113">See Also</span></span>  
 [<span data-ttu-id="d46ce-114">ISymUnmanagedScope2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d46ce-114">ISymUnmanagedScope2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-interface.md)
