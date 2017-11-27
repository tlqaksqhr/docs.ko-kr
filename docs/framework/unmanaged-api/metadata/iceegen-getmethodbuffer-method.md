---
title: "ICeeGen::GetMethodBuffer 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICeeGen.GetMethodBuffer
api_location: mscoree.dll
api_type: COM
f1_keywords: ICeeGen::GetMethodBuffer
helpviewer_keywords:
- ICeeGen::GetMethodBuffer method [.NET Framework metadata]
- GetMethodBuffer method [.NET Framework metadata]
ms.assetid: c7c5b39a-d4ac-41f1-9d1e-44163f563a49
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: be6b74de649a9b13092e6a5dcd2d2f80a215a16d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="iceegengetmethodbuffer-method"></a><span data-ttu-id="4d597-102">ICeeGen::GetMethodBuffer 메서드</span><span class="sxs-lookup"><span data-stu-id="4d597-102">ICeeGen::GetMethodBuffer Method</span></span>
<span data-ttu-id="4d597-103">지정된 된 상대 가상 주소에서 메서드에 대 한 적절 한 크기의 버퍼를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="4d597-103">Gets a buffer of the appropriate size for the method at the specified relative virtual address.</span></span>  
  
 <span data-ttu-id="4d597-104">이 메서드는 사용 되지 않으며 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4d597-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d597-105">구문</span><span class="sxs-lookup"><span data-stu-id="4d597-105">Syntax</span></span>  
  
```  
HRESULT GetMethodBuffer (  
    [in]  ULONG       RVA,  
    [out] UCHAR       **lpBuffer  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4d597-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="4d597-106">Parameters</span></span>  
 `RVA`  
 <span data-ttu-id="4d597-107">[in] 반환할 버퍼에 대 한 메서드의 상대 가상 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="4d597-107">[in] The relative virtual address of the method for which to return a buffer.</span></span>  
  
 `lpBuffer`  
 <span data-ttu-id="4d597-108">[out] 반환된 된 버퍼에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="4d597-108">[out] A pointer to the returned buffer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4d597-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4d597-109">Requirements</span></span>  
 <span data-ttu-id="4d597-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4d597-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4d597-111">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="4d597-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4d597-112">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="4d597-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4d597-113">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4d597-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d597-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4d597-114">See Also</span></span>  
 [<span data-ttu-id="4d597-115">ICeeGen 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4d597-115">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
