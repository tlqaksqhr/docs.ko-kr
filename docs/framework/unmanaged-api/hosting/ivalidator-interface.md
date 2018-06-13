---
title: IValidator 인터페이스
ms.date: 03/30/2017
api_name:
- IValidator
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IValidator
helpviewer_keywords:
- IValidator interface [.NET Framework hosting]
ms.assetid: b297e3b0-20f9-478f-b707-5e2eecb2b5b2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9e79a69bf71aee035fb1f9a0178879d7c19e62b9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33448923"
---
# <a name="ivalidator-interface"></a><span data-ttu-id="e8360-102">IValidator 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e8360-102">IValidator Interface</span></span>
<span data-ttu-id="e8360-103">이식 가능한 실행 (PE) 이미지 유효성 검사 및 유효성 검사 오류를 보고에 대 한 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8360-103">Provides methods for validating portable executable (PE) images and reporting validation errors.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e8360-104">메서드</span><span class="sxs-lookup"><span data-stu-id="e8360-104">Methods</span></span>  
  
|<span data-ttu-id="e8360-105">메서드</span><span class="sxs-lookup"><span data-stu-id="e8360-105">Method</span></span>|<span data-ttu-id="e8360-106">설명</span><span class="sxs-lookup"><span data-stu-id="e8360-106">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="e8360-107">Validate</span><span class="sxs-lookup"><span data-stu-id="e8360-107">Validate</span></span>|<span data-ttu-id="e8360-108">지정된 된 PE 또는 Microsoft MSIL (intermediate language) 파일의 유효성을 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8360-108">Validates the specified PE or Microsoft intermediate language (MSIL) file.</span></span>|  
|<span data-ttu-id="e8360-109">FormatEventInfo</span><span class="sxs-lookup"><span data-stu-id="e8360-109">FormatEventInfo</span></span>|<span data-ttu-id="e8360-110">지정 된 유효성 검사 오류에 해당 하는 오류 메시지를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e8360-110">Gets the error message corresponding to the specified validation error.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e8360-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e8360-111">Requirements</span></span>  
 <span data-ttu-id="e8360-112">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e8360-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e8360-113">**헤더:** IValidator.idl, IValidator.h</span><span class="sxs-lookup"><span data-stu-id="e8360-113">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="e8360-114">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="e8360-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e8360-115">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e8360-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8360-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e8360-116">See Also</span></span>  
 [<span data-ttu-id="e8360-117">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e8360-117">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="e8360-118">CorRuntimeHost Coclass</span><span class="sxs-lookup"><span data-stu-id="e8360-118">CorRuntimeHost Coclass</span></span>](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)
