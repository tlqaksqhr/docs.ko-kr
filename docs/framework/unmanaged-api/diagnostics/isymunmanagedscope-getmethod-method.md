---
title: ISymUnmanagedScope::GetMethod 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetMethod
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetMethod
helpviewer_keywords:
- GetMethod method, ISymUnmanagedScope interface [.NET Framework debugging]
- ISymUnmanagedScope::GetMethod method [.NET Framework debugging]
ms.assetid: a61866ee-221a-45b9-a1b7-395825b77872
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ebef54baf4e560b364845a521e4b4444ed359395
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33426122"
---
# <a name="isymunmanagedscopegetmethod-method"></a><span data-ttu-id="3c413-102">ISymUnmanagedScope::GetMethod 메서드</span><span class="sxs-lookup"><span data-stu-id="3c413-102">ISymUnmanagedScope::GetMethod Method</span></span>
<span data-ttu-id="3c413-103">이 범위를 포함 하는 메서드를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3c413-103">Gets the method that contains this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c413-104">구문</span><span class="sxs-lookup"><span data-stu-id="3c413-104">Syntax</span></span>  
  
```  
HRESULT GetMethod(  
    [out, retval] ISymUnmanagedMethod** pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3c413-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3c413-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="3c413-106">[out] 반환 된에 대 한 포인터 [ISymUnmanagedMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="3c413-106">[out] A pointer to the returned [ISymUnmanagedMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3c413-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="3c413-107">Return Value</span></span>  
 <span data-ttu-id="3c413-108">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 기타 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="3c413-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3c413-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3c413-109">Requirements</span></span>  
 <span data-ttu-id="3c413-110">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="3c413-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c413-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3c413-111">See Also</span></span>  
 [<span data-ttu-id="3c413-112">ISymUnmanagedScope 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3c413-112">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)
