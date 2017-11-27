---
title: "ISymUnmanagedWriter::Close 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter.Close
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter::Close
helpviewer_keywords:
- Close method, ISymUnmanagedWriter interface [.NET Framework debugging]
- ISymUnmanagedWriter::Close method [.NET Framework debugging]
ms.assetid: 4cce59e1-80b9-4fc4-b3aa-126f1c5876bc
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: ad0cec59531a7e22d0a4d2220cb2dfcdd8f27596
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedwriterclose-method"></a><span data-ttu-id="8245c-102">ISymUnmanagedWriter::Close 메서드</span><span class="sxs-lookup"><span data-stu-id="8245c-102">ISymUnmanagedWriter::Close Method</span></span>
<span data-ttu-id="8245c-103">기호를 기호 저장소에 커밋한 후 기호 작성기를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="8245c-103">Closes the symbol writer after committing the symbols to the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8245c-104">구문</span><span class="sxs-lookup"><span data-stu-id="8245c-104">Syntax</span></span>  
  
```  
HRESULT Close();  
```  
  
## <a name="return-value"></a><span data-ttu-id="8245c-105">반환 값</span><span class="sxs-lookup"><span data-stu-id="8245c-105">Return Value</span></span>  
 <span data-ttu-id="8245c-106">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 기타 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="8245c-106">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8245c-107">설명</span><span class="sxs-lookup"><span data-stu-id="8245c-107">Remarks</span></span>  
 <span data-ttu-id="8245c-108">이 호출 후 기호 작성기 추가로 업데이트할 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8245c-108">After this call, the symbol writer becomes invalid for further updates.</span></span> <span data-ttu-id="8245c-109">사용 하 여 기호를 커밋하지 않고 기호 작성기를 닫으려면는 [isymunmanagedwriter:: Abort](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-abort-method.md) 메서드 대신 합니다.</span><span class="sxs-lookup"><span data-stu-id="8245c-109">To close the symbol writer without committing the symbols, use the [ISymUnmanagedWriter::Abort](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-abort-method.md) method instead.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8245c-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8245c-110">Requirements</span></span>  
 <span data-ttu-id="8245c-111">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="8245c-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8245c-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8245c-112">See Also</span></span>  
 [<span data-ttu-id="8245c-113">ISymUnmanagedWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8245c-113">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
