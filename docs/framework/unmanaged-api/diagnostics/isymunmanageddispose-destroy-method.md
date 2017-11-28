---
title: "ISymUnmanagedDispose::Destroy 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedDispose.Destroy
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedDispose::Destroy
helpviewer_keywords:
- ISymUnmanagedDispose::Destroy method [.NET Framework debugging]
- Destroy method [.NET Framework debugging]
ms.assetid: a854ab9f-d2ba-470e-867f-808c1e7bd07a
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: d808392d883d1168d6aad8d16ab50ce072b1d9f7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanageddisposedestroy-method"></a><span data-ttu-id="39479-102">ISymUnmanagedDispose::Destroy 메서드</span><span class="sxs-lookup"><span data-stu-id="39479-102">ISymUnmanagedDispose::Destroy Method</span></span>
<span data-ttu-id="39479-103">이 인해 기본 개체가 모든 내부 참조를 해제 하 고 이후의 모든 메서드 호출 시 오류를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="39479-103">Causes the underlying object to release all internal references and return failure on any subsequent method calls.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39479-104">구문</span><span class="sxs-lookup"><span data-stu-id="39479-104">Syntax</span></span>  
  
```  
HRESULT Destroy();  
```  
  
## <a name="return-value"></a><span data-ttu-id="39479-105">반환 값</span><span class="sxs-lookup"><span data-stu-id="39479-105">Return Value</span></span>  
 <span data-ttu-id="39479-106">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 기타 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="39479-106">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="39479-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="39479-107">Requirements</span></span>  
 <span data-ttu-id="39479-108">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="39479-108">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39479-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="39479-109">See Also</span></span>  
 [<span data-ttu-id="39479-110">ISymUnmanagedDispose 인터페이스</span><span class="sxs-lookup"><span data-stu-id="39479-110">ISymUnmanagedDispose Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddispose-interface.md)
