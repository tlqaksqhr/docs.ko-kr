---
title: "FreeWin32ResBlob 메서드"
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
- IALink.FreeWin32ResBlob
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- FreeWin32ResBlob
helpviewer_keywords:
- FreeWin32ResBlob method
ms.assetid: d941102b-2679-4c49-b15e-c0fc9c53e11f
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: cdecedf319ad235bd635dd1d2edf600b0d00dbb7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="freewin32resblob-method"></a><span data-ttu-id="c97cd-102">FreeWin32ResBlob 메서드</span><span class="sxs-lookup"><span data-stu-id="c97cd-102">FreeWin32ResBlob Method</span></span>
<span data-ttu-id="c97cd-103">Win32 리소스 blob와 연결 된 리소스를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="c97cd-103">Releases the Win32 resource blob and associated resources.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c97cd-104">구문</span><span class="sxs-lookup"><span data-stu-id="c97cd-104">Syntax</span></span>  
  
```  
HRESULT FreeWin32ResBlob(  
    const void** ppResBlob  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c97cd-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c97cd-105">Parameters</span></span>  
 `ppResBlob`  
 <span data-ttu-id="c97cd-106">릴리스될 리소스 blob입니다.</span><span class="sxs-lookup"><span data-stu-id="c97cd-106">The resource blob to be released.</span></span> <span data-ttu-id="c97cd-107">이 메서드는 NULL로 blob 파일에 대 한 포인터를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="c97cd-107">This method assigns the blob pointer to NULL.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c97cd-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="c97cd-108">Return Value</span></span>  
 <span data-ttu-id="c97cd-109">메서드가 성공 하면 S_OK를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="c97cd-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c97cd-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c97cd-110">Requirements</span></span>  
 <span data-ttu-id="c97cd-111">Alink.h 필요</span><span class="sxs-lookup"><span data-stu-id="c97cd-111">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c97cd-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c97cd-112">See Also</span></span>  
 [<span data-ttu-id="c97cd-113">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c97cd-113">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="c97cd-114">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c97cd-114">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="c97cd-115">ALink API</span><span class="sxs-lookup"><span data-stu-id="c97cd-115">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
