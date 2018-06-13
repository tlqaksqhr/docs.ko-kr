---
title: ISymUnmanagedReader::GetMethod 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetMethod
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetMethod
helpviewer_keywords:
- GetMethod method, ISymUnmanagedReader interface [.NET Framework debugging]
- ISymUnmanagedReader::GetMethod method [.NET Framework debugging]
ms.assetid: ae6cfb29-bc2c-4606-af86-1d32ebd31020
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e9f1056d8d5ec4486e748d3b079507943a8a72ef
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33430640"
---
# <a name="isymunmanagedreadergetmethod-method"></a><span data-ttu-id="93795-102">ISymUnmanagedReader::GetMethod 메서드</span><span class="sxs-lookup"><span data-stu-id="93795-102">ISymUnmanagedReader::GetMethod Method</span></span>
<span data-ttu-id="93795-103">메서드 토큰이 지정 된 기호 판독기 메서드를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="93795-103">Gets a symbol reader method, given a method token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="93795-104">구문</span><span class="sxs-lookup"><span data-stu-id="93795-104">Syntax</span></span>  
  
```  
HRESULT GetMethod (  
    [in]  mdMethodDef  token,  
    [out, retval] ISymUnmanagedMethod**  pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="93795-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="93795-105">Parameters</span></span>  
 `token`  
 <span data-ttu-id="93795-106">[in] 메서드 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="93795-106">[in] The method token.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="93795-107">[out] 반환 되는 인터페이스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="93795-107">[out] A pointer to the returned interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="93795-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="93795-108">Return Value</span></span>  
 <span data-ttu-id="93795-109">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 기타 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="93795-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="93795-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="93795-110">Requirements</span></span>  
 <span data-ttu-id="93795-111">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="93795-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93795-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="93795-112">See Also</span></span>  
 [<span data-ttu-id="93795-113">ISymUnmanagedReader 인터페이스</span><span class="sxs-lookup"><span data-stu-id="93795-113">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
