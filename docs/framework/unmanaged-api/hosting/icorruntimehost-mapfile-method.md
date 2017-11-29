---
title: "ICorRuntimeHost::MapFile 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorRuntimeHost.MapFile
api_location: mscoree.dll
api_type: COM
f1_keywords: ICorRuntimeHost::MapFile
helpviewer_keywords:
- ICorRuntimeHost::MapFile method [.NET Framework hosting]
- MapFile method [.NET Framework hosting]
ms.assetid: 45ae0502-0a31-4342-b7e3-f36e1cf738f3
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: fd156aac23cdca446bcf2666ce36e91fef6d5392
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="icorruntimehostmapfile-method"></a><span data-ttu-id="7c922-102">ICorRuntimeHost::MapFile 메서드</span><span class="sxs-lookup"><span data-stu-id="7c922-102">ICorRuntimeHost::MapFile Method</span></span>
<span data-ttu-id="7c922-103">지정된 된 파일을 메모리에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="7c922-103">Maps the specified file into memory.</span></span> <span data-ttu-id="7c922-104">이 메서드는 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7c922-104">This method is obsolete.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c922-105">구문</span><span class="sxs-lookup"><span data-stu-id="7c922-105">Syntax</span></span>  
  
```  
HRESULT MapFile(  
    [in]  HANDLE    hFile,  
    [out] HMODULE*  hMapAddress  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7c922-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7c922-106">Parameters</span></span>  
 `hFile`  
 <span data-ttu-id="7c922-107">[in] 매핑할 파일의 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="7c922-107">[in] The handle of the file to be mapped.</span></span>  
  
 `hMapAddress`  
 <span data-ttu-id="7c922-108">[out] 매핑 파일을 시작 하는 시작 메모리 주소를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c922-108">[out] The starting memory address at which to begin mapping the file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7c922-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7c922-109">Requirements</span></span>  
 <span data-ttu-id="7c922-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7c922-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c922-111">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="7c922-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7c922-112">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="7c922-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7c922-113">**.NET framework 버전:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="7c922-113">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c922-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7c922-114">See Also</span></span>  
 [<span data-ttu-id="7c922-115">ICorRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7c922-115">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
