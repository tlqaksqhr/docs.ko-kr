---
title: CreateApplicationContext 함수
ms.date: 03/30/2017
api_name:
- CreateApplicationContext
api_location:
- fusion.dll
api_type:
- DLLExport
f1_keywords:
- CreateApplicationContext
helpviewer_keywords:
- CreateApplicationContext function [.NET Framework fusion]
ms.assetid: 7bf8a141-b2c0-4058-9885-1cef7dcaa811
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 80012d030d0ea51ab3d150a7fd346b78e29dbde5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33430102"
---
# <a name="createapplicationcontext-function"></a><span data-ttu-id="b32de-102">CreateApplicationContext 함수</span><span class="sxs-lookup"><span data-stu-id="b32de-102">CreateApplicationContext Function</span></span>
<span data-ttu-id="b32de-103">이 함수는.NET Framework 인프라를 지원 하며 사용자 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b32de-103">This function supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b32de-104">구문</span><span class="sxs-lookup"><span data-stu-id="b32de-104">Syntax</span></span>  
  
```  
HRESULT CreateApplicationContext (  
    [in]  IAssemblyName  *pName,  
    [out] LPPAPPLICATIONCONTEXT  *ppCtx  
 );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b32de-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b32de-105">Parameters</span></span>  
 `pName`  
 <span data-ttu-id="b32de-106">[in] 이름에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="b32de-106">[in] A pointer to a friendly name.</span></span>  
  
 `ppCtx`  
 <span data-ttu-id="b32de-107">[out] 응용 프로그램 컨텍스트에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="b32de-107">[out] A pointer to an application context.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b32de-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b32de-108">Requirements</span></span>  
 <span data-ttu-id="b32de-109">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b32de-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b32de-110">**헤더:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="b32de-110">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="b32de-111">**라이브러리:** 의 Fusion.dll 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="b32de-111">**Library:** Included as a resource in Fusion.dll</span></span>  
  
 <span data-ttu-id="b32de-112">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b32de-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b32de-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b32de-113">See Also</span></span>  
 [<span data-ttu-id="b32de-114">IAssemblyCache 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b32de-114">IAssemblyCache Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md)  
 [<span data-ttu-id="b32de-115">Fusion 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="b32de-115">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)  
 [<span data-ttu-id="b32de-116">전역 어셈블리 캐시</span><span class="sxs-lookup"><span data-stu-id="b32de-116">Global Assembly Cache</span></span>](../../../../docs/framework/app-domains/gac.md)
