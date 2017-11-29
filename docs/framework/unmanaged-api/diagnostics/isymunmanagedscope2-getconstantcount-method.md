---
title: "ISymUnmanagedScope2::GetConstantCount 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedScope2.GetConstantCount
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedScope2::GetConstantCount
helpviewer_keywords:
- ISymUnmanagedScope2::GetConstantCount method [.NET Framework debugging]
- GetConstantCount method [.NET Framework debugging]
ms.assetid: 1e1f0be6-c4e8-4d6c-98cd-d5fa9f686e87
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 26ce28c3542af80f033cc765c3e462a34e4fb3e4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedscope2getconstantcount-method"></a><span data-ttu-id="46717-102">ISymUnmanagedScope2::GetConstantCount 메서드</span><span class="sxs-lookup"><span data-stu-id="46717-102">ISymUnmanagedScope2::GetConstantCount Method</span></span>
<span data-ttu-id="46717-103">이 범위 내에서 정의 된 상수 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="46717-103">Gets a count of the constants defined within this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46717-104">구문</span><span class="sxs-lookup"><span data-stu-id="46717-104">Syntax</span></span>  
  
```  
HRESULT GetConstantCount(  
    [out, retval] ULONG32 *pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="46717-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="46717-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="46717-106">[out] 에 대 한 포인터는 `ULONG32` 문자 상수를 포함 하는 데 필요한 버퍼 크기를 받는 합니다.</span><span class="sxs-lookup"><span data-stu-id="46717-106">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the constants.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="46717-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="46717-107">Return Value</span></span>  
 <span data-ttu-id="46717-108">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 기타 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="46717-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="46717-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="46717-109">Requirements</span></span>  
 <span data-ttu-id="46717-110">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="46717-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46717-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="46717-111">See Also</span></span>  
 [<span data-ttu-id="46717-112">ISymUnmanagedScope2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="46717-112">ISymUnmanagedScope2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-interface.md)
