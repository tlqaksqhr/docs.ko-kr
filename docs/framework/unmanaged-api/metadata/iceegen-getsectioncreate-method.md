---
title: ICeeGen::GetSectionCreate 메서드
ms.date: 03/30/2017
api_name:
- ICeeGen.GetSectionCreate
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::GetSectionCreate
helpviewer_keywords:
- ICeeGen::GetSectionCreate method [.NET Framework metadata]
- GetSectionCreate method [.NET Framework metadata]
ms.assetid: 154b2460-59ce-4874-a9f2-1b3353486ac5
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 857462c380ce51994e13dab5cfe3c28bba0f38be
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33443341"
---
# <a name="iceegengetsectioncreate-method"></a><span data-ttu-id="36170-102">ICeeGen::GetSectionCreate 메서드</span><span class="sxs-lookup"><span data-stu-id="36170-102">ICeeGen::GetSectionCreate Method</span></span>
<span data-ttu-id="36170-103">생성 하 고 지정한 이름 및 플래그 값을 사용 하는 코드 섹션을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="36170-103">Generates and gets a code section using the specified name and flag values.</span></span>  
  
 <span data-ttu-id="36170-104">이 메서드는 사용 되지 않으며 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="36170-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36170-105">구문</span><span class="sxs-lookup"><span data-stu-id="36170-105">Syntax</span></span>  
  
```  
HRESULT GetSectionCreate (  
    [in]  const char     *name,  
    [in]  DWORD          flags,  
    [out] HCEESECTION    *section  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="36170-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="36170-106">Parameters</span></span>  
 `name`  
 <span data-ttu-id="36170-107">[in] 만들 섹션의 이름을 지정 하는 문자열에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="36170-107">[in] A pointer to a string that specifies the name of the section to be created.</span></span>  
  
 `flags`  
 <span data-ttu-id="36170-108">[in] 옵션을 지정 하는 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="36170-108">[in] Flags that specify options.</span></span>  
  
 `section`  
 <span data-ttu-id="36170-109">[out] 새로 생성된 된 코드 섹션에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="36170-109">[out] A pointer to the newly created code section.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="36170-110">설명</span><span class="sxs-lookup"><span data-stu-id="36170-110">Remarks</span></span>  
 <span data-ttu-id="36170-111">호출 `GetSectionCreate` 다른 방법으로 처리 되지 않는 섹션 특별 한 요구 사항이 있는 경우에 합니다.</span><span class="sxs-lookup"><span data-stu-id="36170-111">Call `GetSectionCreate` only if you have special section requirements that are not handled by other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="36170-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="36170-112">Requirements</span></span>  
 <span data-ttu-id="36170-113">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="36170-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="36170-114">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="36170-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="36170-115">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="36170-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="36170-116">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="36170-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36170-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="36170-117">See Also</span></span>  
 [<span data-ttu-id="36170-118">ICeeGen 인터페이스</span><span class="sxs-lookup"><span data-stu-id="36170-118">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
