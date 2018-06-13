---
title: _CorExeMain2 함수
ms.date: 03/30/2017
api_name:
- _CorExeMain2
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- _CorExeMain2
helpviewer_keywords:
- _CorExeMain2 function [.NET Framework hosting]
ms.assetid: 72ea68b4-689f-4733-9416-9664b75e8892
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 573336b32040f44ff1b59fcbb75b59aa00976b5c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33430181"
---
# <a name="corexemain2-function"></a><span data-ttu-id="6e0e0-102">_CorExeMain2 함수</span><span class="sxs-lookup"><span data-stu-id="6e0e0-102">_CorExeMain2 Function</span></span>
<span data-ttu-id="6e0e0-103">지정된 된 메모리 매핑된 코드에서 진입점을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="6e0e0-103">Executes the entry point in the specified memory-mapped code.</span></span> <span data-ttu-id="6e0e0-104">이 함수는 운영 체제 로더에 의해 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e0e0-104">This function is called by the operating system loader.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e0e0-105">구문</span><span class="sxs-lookup"><span data-stu-id="6e0e0-105">Syntax</span></span>  
  
```  
__int32 STDMETHODCALLTYPE _CorExeMain2 (  
   [in] PBYTE           pUnmappedPE,  
   [in] DWORD           cUnmappedPE,  
   [in] __in LPWSTR     pImageNameIn,  
   [in] __in LPWSTR     pLoadersFileName,  
   [in] __in LPWSTR     pCmdLine  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6e0e0-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6e0e0-106">Parameters</span></span>  
 `pUnmappedPE`  
 <span data-ttu-id="6e0e0-107">[in] 메모리 매핑된 코드에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="6e0e0-107">[in] A pointer to the memory-mapped code.</span></span>  
  
 `cUnmappedPE`  
 <span data-ttu-id="6e0e0-108">[in] 요소 수가 `pUnmappedPE` 보유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e0e0-108">[in] The number of elements `pUnmappedPE` can hold.</span></span>  
  
 `pImageNameIn`  
 <span data-ttu-id="6e0e0-109">[in] 실행 가능 이미지의 이름에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="6e0e0-109">[in] A pointer to the name of the executable image.</span></span>  
  
 `pLoadersFileName`  
 <span data-ttu-id="6e0e0-110">[in] 로더 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="6e0e0-110">[in] The name of the loader file.</span></span>  
  
 `pCmdLine`  
 <span data-ttu-id="6e0e0-111">[in] 명령줄 매개 변수가 있는 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="6e0e0-111">[in] Command-line parameters, if any.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6e0e0-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6e0e0-112">Requirements</span></span>  
 <span data-ttu-id="6e0e0-113">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6e0e0-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6e0e0-114">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="6e0e0-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6e0e0-115">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="6e0e0-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6e0e0-116">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6e0e0-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e0e0-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6e0e0-117">See Also</span></span>  
 [<span data-ttu-id="6e0e0-118">메타데이터 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="6e0e0-118">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
