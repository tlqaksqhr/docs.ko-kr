---
title: "LinkResource 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IALink.LinkResource
api_location: alink.dll
api_type: COM
f1_keywords: LinkResource
helpviewer_keywords: LinkResource method
ms.assetid: c404acb3-4c59-4100-9a4c-483cbdb1d736
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 8cb1f985c1d735fa20507ab90d478e97025c9e2c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="linkresource-method"></a><span data-ttu-id="d8a51-102">LinkResource 메서드</span><span class="sxs-lookup"><span data-stu-id="d8a51-102">LinkResource Method</span></span>
<span data-ttu-id="d8a51-103">리소스의 링크를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8a51-103">Links in a resource.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8a51-104">구문</span><span class="sxs-lookup"><span data-stu-id="d8a51-104">Syntax</span></span>  
  
```  
HRESULT LinkResource(  
    mdAssembly  AssemblyID,  
    LPCWSTR     pszFileName,  
    LPCWSTR     pszNewLocation,  
    LPCWSTR     pszResourceName,  
    DWORD       dwFlags  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d8a51-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d8a51-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="d8a51-106">어셈블리의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="d8a51-106">ID of the assembly.</span></span>  
  
 `pszFileName`  
 <span data-ttu-id="d8a51-107">파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d8a51-107">Name of the file.</span></span>  
  
 `pszNewLocation`  
 <span data-ttu-id="d8a51-108">(옵션) 새 파일 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d8a51-108">Optional new file name.</span></span> <span data-ttu-id="d8a51-109">Null이 아닌 `pszFileName` pszNewLocation에 복사 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8a51-109">If non-NULL, `pszFileName` will be copied to pszNewLocation.</span></span>  
  
 `pszResourceName`  
 <span data-ttu-id="d8a51-110">리소스의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d8a51-110">Name of the resource.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="d8a51-111">내게 필요한 옵션 플래그와 같은 `mrPublic` 및 `mrPrivate`합니다.</span><span class="sxs-lookup"><span data-stu-id="d8a51-111">Accessibility flags such as `mrPublic` and `mrPrivate`.</span></span> <span data-ttu-id="d8a51-112">이 매개 변수 전달 될 수 있습니다 [DefineManifestResource 메서드](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definemanifestresource-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d8a51-112">This parameter may be passed to [DefineManifestResource Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definemanifestresource-method.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d8a51-113">반환 값</span><span class="sxs-lookup"><span data-stu-id="d8a51-113">Return Value</span></span>  
 <span data-ttu-id="d8a51-114">메서드가 성공 하면 S_OK를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8a51-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d8a51-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d8a51-115">Requirements</span></span>  
 <span data-ttu-id="d8a51-116">Alink.h가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d8a51-116">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8a51-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d8a51-117">See Also</span></span>  
 [<span data-ttu-id="d8a51-118">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d8a51-118">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="d8a51-119">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d8a51-119">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="d8a51-120">ALink API</span><span class="sxs-lookup"><span data-stu-id="d8a51-120">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
