---
title: IAssemblyCache::InstallAssembly 메서드
ms.date: 03/30/2017
api_name:
- IAssemblyCache.InstallAssembly
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyCache::InstallAssembly
helpviewer_keywords:
- InstallAssembly method [.NET Framework fusion]
- IAssemblyCache::InstallAssembly method [.NET Framework fusion]
ms.assetid: 33c1d269-c85e-4cb1-b0e6-1c510c8fb5fa
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 726a4ed8ee3d451687e0af671d948eb7648f7f58
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33430026"
---
# <a name="iassemblycacheinstallassembly-method"></a><span data-ttu-id="06a7b-102">IAssemblyCache::InstallAssembly 메서드</span><span class="sxs-lookup"><span data-stu-id="06a7b-102">IAssemblyCache::InstallAssembly Method</span></span>
<span data-ttu-id="06a7b-103">전역 어셈블리 캐시에 지정된 된 어셈블리를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="06a7b-103">Installs the specified assembly in the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06a7b-104">구문</span><span class="sxs-lookup"><span data-stu-id="06a7b-104">Syntax</span></span>  
  
```  
HRESULT InstallAssembly (  
    [in] DWORD dwFlags,  
    [in] LPCWSTR pszManifestFilePath,  
    [in] LPCFUSION_INSTALL_REFERENCE pRefData  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="06a7b-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="06a7b-105">Parameters</span></span>  
 `dwFlags`  
 <span data-ttu-id="06a7b-106">[in] 값에 정의 된 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="06a7b-106">[in] Flags defined in Fusion.idl.</span></span> <span data-ttu-id="06a7b-107">다음 값이 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="06a7b-107">The following values are supported:</span></span>  
  
-   <span data-ttu-id="06a7b-108">IASSEMBLYCACHE_INSTALL_FLAG_REFRESH (0X00000001)</span><span class="sxs-lookup"><span data-stu-id="06a7b-108">IASSEMBLYCACHE_INSTALL_FLAG_REFRESH (0x00000001)</span></span>  
  
-   <span data-ttu-id="06a7b-109">IASSEMBLYCACHE_INSTALL_FLAG_FORCE_REFRESH (0X00000002)</span><span class="sxs-lookup"><span data-stu-id="06a7b-109">IASSEMBLYCACHE_INSTALL_FLAG_FORCE_REFRESH (0x00000002)</span></span>  
  
 `pszManifestFilePath`  
 <span data-ttu-id="06a7b-110">[in] 설치 하려면 어셈블리에 대 한 매니페스트에 대 한 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="06a7b-110">[in] The path to the manifest for the assembly to install.</span></span>  
  
 `pRefData`  
 <span data-ttu-id="06a7b-111">[in] A [FUSION_INSTALL_REFERENCE](../../../../docs/framework/unmanaged-api/fusion/fusion-install-reference-structure.md) 설치에 대 한 데이터가 포함 된 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="06a7b-111">[in] A [FUSION_INSTALL_REFERENCE](../../../../docs/framework/unmanaged-api/fusion/fusion-install-reference-structure.md) structure that contains data for the installation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="06a7b-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="06a7b-112">Requirements</span></span>  
 <span data-ttu-id="06a7b-113">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="06a7b-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="06a7b-114">**헤더:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="06a7b-114">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="06a7b-115">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="06a7b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06a7b-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="06a7b-116">See Also</span></span>  
 [<span data-ttu-id="06a7b-117">IAssemblyCache 인터페이스</span><span class="sxs-lookup"><span data-stu-id="06a7b-117">IAssemblyCache Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md)
