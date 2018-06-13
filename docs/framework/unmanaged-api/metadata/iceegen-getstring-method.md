---
title: ICeeGen::GetString 메서드
ms.date: 03/30/2017
api_name:
- ICeeGen.GetString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::GetString
helpviewer_keywords:
- ICeeGen::GetString method [.NET Framework metadata]
- GetString method, ICeeGen interface [.NET Framework metadata]
ms.assetid: 7cc22562-128c-440a-9147-55ff20f173d7
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f7ac5ef95ca3705b11cfda51d7fd1aca7400abc4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33443075"
---
# <a name="iceegengetstring-method"></a><span data-ttu-id="bda2a-102">ICeeGen::GetString 메서드</span><span class="sxs-lookup"><span data-stu-id="bda2a-102">ICeeGen::GetString Method</span></span>
<span data-ttu-id="bda2a-103">지정된 된 상대 가상 주소에 저장 된 문자열을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="bda2a-103">Gets the string stored at the specified relative virtual address.</span></span>  
  
 <span data-ttu-id="bda2a-104">이 메서드는 사용 되지 않으며 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bda2a-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bda2a-105">구문</span><span class="sxs-lookup"><span data-stu-id="bda2a-105">Syntax</span></span>  
  
```  
HRESULT GetString (  
    [in]  ULONG      RVA,   
    [out] LPWSTR     *lpString  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bda2a-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="bda2a-106">Parameters</span></span>  
 `RVA`  
 <span data-ttu-id="bda2a-107">[in] 반환할 문자열의 상대 가상 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="bda2a-107">[in] The relative virtual address of the string to return.</span></span>  
  
 `lpString`  
 <span data-ttu-id="bda2a-108">[out] 반환 된 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="bda2a-108">[out] The returned string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bda2a-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="bda2a-109">Requirements</span></span>  
 <span data-ttu-id="bda2a-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="bda2a-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bda2a-111">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="bda2a-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="bda2a-112">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="bda2a-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="bda2a-113">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bda2a-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bda2a-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bda2a-114">See Also</span></span>  
 [<span data-ttu-id="bda2a-115">ICeeGen 인터페이스</span><span class="sxs-lookup"><span data-stu-id="bda2a-115">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
