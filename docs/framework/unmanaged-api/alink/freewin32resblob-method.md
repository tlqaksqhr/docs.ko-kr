---
title: FreeWin32ResBlob 메서드
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d124ce5dd38bed7eb439a055ff9e30a75efe5891
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33400746"
---
# <a name="freewin32resblob-method"></a><span data-ttu-id="0429b-102">FreeWin32ResBlob 메서드</span><span class="sxs-lookup"><span data-stu-id="0429b-102">FreeWin32ResBlob Method</span></span>
<span data-ttu-id="0429b-103">Win32 리소스 blob와 연결 된 리소스를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="0429b-103">Releases the Win32 resource blob and associated resources.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0429b-104">구문</span><span class="sxs-lookup"><span data-stu-id="0429b-104">Syntax</span></span>  
  
```  
HRESULT FreeWin32ResBlob(  
    const void** ppResBlob  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0429b-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0429b-105">Parameters</span></span>  
 `ppResBlob`  
 <span data-ttu-id="0429b-106">릴리스될 리소스 blob입니다.</span><span class="sxs-lookup"><span data-stu-id="0429b-106">The resource blob to be released.</span></span> <span data-ttu-id="0429b-107">이 메서드는 NULL로 blob 파일에 대 한 포인터를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="0429b-107">This method assigns the blob pointer to NULL.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0429b-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="0429b-108">Return Value</span></span>  
 <span data-ttu-id="0429b-109">메서드가 성공 하면 S_OK를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="0429b-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0429b-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0429b-110">Requirements</span></span>  
 <span data-ttu-id="0429b-111">Alink.h 필요</span><span class="sxs-lookup"><span data-stu-id="0429b-111">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0429b-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0429b-112">See Also</span></span>  
 [<span data-ttu-id="0429b-113">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0429b-113">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="0429b-114">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0429b-114">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="0429b-115">ALink API</span><span class="sxs-lookup"><span data-stu-id="0429b-115">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
