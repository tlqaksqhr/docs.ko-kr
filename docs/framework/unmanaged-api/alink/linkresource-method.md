---
title: LinkResource 메서드
ms.date: 03/30/2017
api_name:
- IALink.LinkResource
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- LinkResource
helpviewer_keywords:
- LinkResource method
ms.assetid: c404acb3-4c59-4100-9a4c-483cbdb1d736
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4f75ebc3a40bddbaf2347b9ef559139888f83900
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33401110"
---
# <a name="linkresource-method"></a><span data-ttu-id="eff73-102">LinkResource 메서드</span><span class="sxs-lookup"><span data-stu-id="eff73-102">LinkResource Method</span></span>
<span data-ttu-id="eff73-103">리소스의 링크를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="eff73-103">Links in a resource.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eff73-104">구문</span><span class="sxs-lookup"><span data-stu-id="eff73-104">Syntax</span></span>  
  
```  
HRESULT LinkResource(  
    mdAssembly  AssemblyID,  
    LPCWSTR     pszFileName,  
    LPCWSTR     pszNewLocation,  
    LPCWSTR     pszResourceName,  
    DWORD       dwFlags  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="eff73-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="eff73-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="eff73-106">어셈블리의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="eff73-106">ID of the assembly.</span></span>  
  
 `pszFileName`  
 <span data-ttu-id="eff73-107">파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="eff73-107">Name of the file.</span></span>  
  
 `pszNewLocation`  
 <span data-ttu-id="eff73-108">(옵션) 새 파일 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="eff73-108">Optional new file name.</span></span> <span data-ttu-id="eff73-109">Null이 아닌 `pszFileName` pszNewLocation에 복사 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eff73-109">If non-NULL, `pszFileName` will be copied to pszNewLocation.</span></span>  
  
 `pszResourceName`  
 <span data-ttu-id="eff73-110">리소스의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="eff73-110">Name of the resource.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="eff73-111">내게 필요한 옵션 플래그와 같은 `mrPublic` 및 `mrPrivate`합니다.</span><span class="sxs-lookup"><span data-stu-id="eff73-111">Accessibility flags such as `mrPublic` and `mrPrivate`.</span></span> <span data-ttu-id="eff73-112">이 매개 변수 전달 될 수 있습니다 [DefineManifestResource 메서드](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definemanifestresource-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="eff73-112">This parameter may be passed to [DefineManifestResource Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definemanifestresource-method.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="eff73-113">반환 값</span><span class="sxs-lookup"><span data-stu-id="eff73-113">Return Value</span></span>  
 <span data-ttu-id="eff73-114">메서드가 성공 하면 S_OK를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="eff73-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eff73-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="eff73-115">Requirements</span></span>  
 <span data-ttu-id="eff73-116">Alink.h가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="eff73-116">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eff73-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="eff73-117">See Also</span></span>  
 [<span data-ttu-id="eff73-118">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="eff73-118">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="eff73-119">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="eff73-119">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="eff73-120">ALink API</span><span class="sxs-lookup"><span data-stu-id="eff73-120">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
