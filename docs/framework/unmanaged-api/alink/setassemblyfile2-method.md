---
title: "SetAssemblyFile2 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IALink2.SetAssemblyFile2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- SetAssemblyFile2
helpviewer_keywords:
- SetAssemblyFile2 method
ms.assetid: eedb9125-1ef1-4000-abfc-7de86e5a1f17
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 671fb857015a5babd388366066d282cb87462c18
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="setassemblyfile2-method"></a><span data-ttu-id="527b8-102">SetAssemblyFile2 메서드</span><span class="sxs-lookup"><span data-stu-id="527b8-102">SetAssemblyFile2 Method</span></span>
<span data-ttu-id="527b8-103">이름 및 새 어셈블리에 대 한 옵션을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="527b8-103">Sets the name of and options for a new assembly.</span></span> <span data-ttu-id="527b8-104">바인딩되지 않은 모듈을 생성 하는 경우에이 메서드를 호출 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="527b8-104">Do not call this method when you produce unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="527b8-105">구문</span><span class="sxs-lookup"><span data-stu-id="527b8-105">Syntax</span></span>  
  
```  
HRESULT SetAssemblyFile2(  
    LPCWSTR pszFilename,  
    IMetaDataEmit2* pEmitter,  
    AssemblyFlags   afFlags,  
    mdAssembly* pAssemblyID  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="527b8-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="527b8-106">Parameters</span></span>  
 `pszFilename`  
 <span data-ttu-id="527b8-107">매니페스트 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="527b8-107">Name of manifest file.</span></span>  
  
 `pEmitter`  
 <span data-ttu-id="527b8-108">[IMetaDataEmit2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md) 이 파일에 대 한 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="527b8-108">[IMetaDataEmit2 Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md) interface for this file.</span></span>  
  
 `afFlags`  
 <span data-ttu-id="527b8-109">옵션 표시 [AssemblyFlags 열거형](../../../../docs/framework/unmanaged-api/metadata/assemblyflags-enumeration.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="527b8-109">Options represented by [AssemblyFlags Enumeration](../../../../docs/framework/unmanaged-api/metadata/assemblyflags-enumeration.md).</span></span>  
  
 `pAssemblyID`  
 <span data-ttu-id="527b8-110">생성 된 어셈블리에 대 한 고유 ID를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="527b8-110">Receives unique ID for the assembly being constructed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="527b8-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="527b8-111">Return Value</span></span>  
 <span data-ttu-id="527b8-112">메서드가 성공 하면 S_OK를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="527b8-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="527b8-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="527b8-113">Requirements</span></span>  
 <span data-ttu-id="527b8-114">Alink.h가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="527b8-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="527b8-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="527b8-115">See Also</span></span>  
 [<span data-ttu-id="527b8-116">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="527b8-116">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="527b8-117">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="527b8-117">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="527b8-118">ALink API</span><span class="sxs-lookup"><span data-stu-id="527b8-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
