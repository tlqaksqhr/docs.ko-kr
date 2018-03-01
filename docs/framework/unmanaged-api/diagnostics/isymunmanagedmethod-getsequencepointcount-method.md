---
title: "ISymUnmanagedMethod::GetSequencePointCount 메서드"
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
- ISymUnmanagedMethod.GetSequencePointCount
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetSequencePointCount
helpviewer_keywords:
- ISymUnmanagedMethod::GetSequencePointCount method [.NET Framework debugging]
- GetSequencePointCount method [.NET Framework debugging]
ms.assetid: 836133e8-6108-4b9b-b0a9-bce4e08dccda
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: cf09a754c168a740942b60416b2c9589b12e7700
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedmethodgetsequencepointcount-method"></a><span data-ttu-id="f5c82-102">ISymUnmanagedMethod::GetSequencePointCount 메서드</span><span class="sxs-lookup"><span data-stu-id="f5c82-102">ISymUnmanagedMethod::GetSequencePointCount Method</span></span>
<span data-ttu-id="f5c82-103">이 메서드 내에서 시퀀스 위치 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f5c82-103">Gets the count of sequence points within this method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5c82-104">구문</span><span class="sxs-lookup"><span data-stu-id="f5c82-104">Syntax</span></span>  
  
```  
HRESULT GetSequencePointCount(  
    [out, retval] ULONG32* pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f5c82-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f5c82-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="f5c82-106">[out] 에 대 한 포인터는 `ULONG32` 시퀀스 위치를 포함 하는 데 필요한 버퍼의 크기를 받는입니다.</span><span class="sxs-lookup"><span data-stu-id="f5c82-106">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the sequence points.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f5c82-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="f5c82-107">Return Value</span></span>  
 <span data-ttu-id="f5c82-108">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 기타 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="f5c82-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f5c82-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f5c82-109">Requirements</span></span>  
 <span data-ttu-id="f5c82-110">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="f5c82-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5c82-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f5c82-111">See Also</span></span>  
 [<span data-ttu-id="f5c82-112">ISymUnmanagedMethod 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f5c82-112">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
