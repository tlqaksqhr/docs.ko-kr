---
title: ISymUnmanagedMethod::GetSequencePointCount 메서드
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c1a9ef59cfe63ba745e6f5eba3ba2c3f3f983886
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33425394"
---
# <a name="isymunmanagedmethodgetsequencepointcount-method"></a><span data-ttu-id="aefc4-102">ISymUnmanagedMethod::GetSequencePointCount 메서드</span><span class="sxs-lookup"><span data-stu-id="aefc4-102">ISymUnmanagedMethod::GetSequencePointCount Method</span></span>
<span data-ttu-id="aefc4-103">이 메서드 내에서 시퀀스 위치 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="aefc4-103">Gets the count of sequence points within this method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aefc4-104">구문</span><span class="sxs-lookup"><span data-stu-id="aefc4-104">Syntax</span></span>  
  
```  
HRESULT GetSequencePointCount(  
    [out, retval] ULONG32* pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="aefc4-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="aefc4-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="aefc4-106">[out] 에 대 한 포인터는 `ULONG32` 시퀀스 위치를 포함 하는 데 필요한 버퍼의 크기를 받는입니다.</span><span class="sxs-lookup"><span data-stu-id="aefc4-106">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the sequence points.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="aefc4-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="aefc4-107">Return Value</span></span>  
 <span data-ttu-id="aefc4-108">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 기타 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="aefc4-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aefc4-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="aefc4-109">Requirements</span></span>  
 <span data-ttu-id="aefc4-110">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="aefc4-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aefc4-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="aefc4-111">See Also</span></span>  
 [<span data-ttu-id="aefc4-112">ISymUnmanagedMethod 인터페이스</span><span class="sxs-lookup"><span data-stu-id="aefc4-112">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
