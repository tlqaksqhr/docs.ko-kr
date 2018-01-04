---
title: "ISymUnmanagedReader::GetMethodVersion 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedReader.GetMethodVersion
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedReader::GetMethodVersion
helpviewer_keywords:
- GetMethodVersion method [.NET Framework debugging]
- ISymUnmanagedReader::GetMethodVersion method [.NET Framework debugging]
ms.assetid: d6f9ac84-302a-4f5e-b990-e76f4269fceb
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 713b8a89c9519abe407ac1d68adb2552cd012b1f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedreadergetmethodversion-method"></a><span data-ttu-id="af52a-102">ISymUnmanagedReader::GetMethodVersion 메서드</span><span class="sxs-lookup"><span data-stu-id="af52a-102">ISymUnmanagedReader::GetMethodVersion Method</span></span>
<span data-ttu-id="af52a-103">메서드 버전을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="af52a-103">Gets the method version.</span></span> <span data-ttu-id="af52a-104">메서드 버전은 1에서 시작 하 고 메서드가 다시 컴파일될 때마다 증가 합니다.</span><span class="sxs-lookup"><span data-stu-id="af52a-104">The method version starts at 1 and is incremented each time the method is recompiled.</span></span> <span data-ttu-id="af52a-105">메서드를 변경 하지 않고 컴파일할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af52a-105">Recompilation can happen without changes to the method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af52a-106">구문</span><span class="sxs-lookup"><span data-stu-id="af52a-106">Syntax</span></span>  
  
```  
HRESULT GetMethodVersion (  
    [in]  ISymUnmanagedMethod* pMethod,  
    [out] int* version);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="af52a-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="af52a-107">Parameters</span></span>  
 `pMethod`  
 <span data-ttu-id="af52a-108">[in] 버전을 가져오는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="af52a-108">[in] The method for which to get the version.</span></span>  
  
 `version`  
 <span data-ttu-id="af52a-109">[out] 포인터 메서드 버전을 수신 하는 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="af52a-109">[out] A pointer to a variable that receives the method version.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="af52a-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="af52a-110">Return Value</span></span>  
 <span data-ttu-id="af52a-111">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 기타 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="af52a-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="af52a-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="af52a-112">Requirements</span></span>  
 <span data-ttu-id="af52a-113">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="af52a-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af52a-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="af52a-114">See Also</span></span>  
 [<span data-ttu-id="af52a-115">ISymUnmanagedReader 인터페이스</span><span class="sxs-lookup"><span data-stu-id="af52a-115">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
