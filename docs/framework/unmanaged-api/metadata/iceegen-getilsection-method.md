---
title: "ICeeGen::GetIlSection 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICeeGen.GetIlSection
api_location: mscoree.dll
api_type: COM
f1_keywords: ICeeGen::GetIlSection
helpviewer_keywords:
- GetIlSection method [.NET Framework metadata]
- ICeeGen::GetIlSection method [.NET Framework metadata]
ms.assetid: 6f2db2ca-203f-4ac3-9530-208642ca385e
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4805e9421a80954c01ba1ffb6e04332c07e5d84e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="iceegengetilsection-method"></a><span data-ttu-id="1d8e0-102">ICeeGen::GetIlSection 메서드</span><span class="sxs-lookup"><span data-stu-id="1d8e0-102">ICeeGen::GetIlSection Method</span></span>
<span data-ttu-id="1d8e0-103">지정된 된 핸들에서 참조 하는 기본 중간 언어 코드의 섹션을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1d8e0-103">Gets the section of the intermediate language code base referenced by the specified handle.</span></span>  
  
 <span data-ttu-id="1d8e0-104">이 메서드는 사용 되지 않으며 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1d8e0-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d8e0-105">구문</span><span class="sxs-lookup"><span data-stu-id="1d8e0-105">Syntax</span></span>  
  
```  
HRESULT GetIlSection (  
    [in] HCEESECTION  *section  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1d8e0-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1d8e0-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="1d8e0-107">[in] 가져올 섹션에 대 한 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="1d8e0-107">[in] The handle to the section to get.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1d8e0-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1d8e0-108">Requirements</span></span>  
 <span data-ttu-id="1d8e0-109">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8e0-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1d8e0-110">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="1d8e0-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1d8e0-111">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="1d8e0-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="1d8e0-112">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1d8e0-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d8e0-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1d8e0-113">See Also</span></span>  
 [<span data-ttu-id="1d8e0-114">ICeeGen 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1d8e0-114">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
