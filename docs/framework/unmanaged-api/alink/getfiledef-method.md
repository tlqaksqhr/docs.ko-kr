---
title: GetFileDef 메서드
ms.date: 03/30/2017
api_name:
- IALink2.GetFileDef
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GetFileDef
helpviewer_keywords:
- GetFileDef method
ms.assetid: 4e3fbe6c-b82a-4181-ab17-7faa1263f5b3
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b772ae37baed44b90e4f5420e0f7724201a56abe
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33401813"
---
# <a name="getfiledef-method"></a><span data-ttu-id="5a743-102">GetFileDef 메서드</span><span class="sxs-lookup"><span data-stu-id="5a743-102">GetFileDef Method</span></span>
<span data-ttu-id="5a743-103">(반대로 ALink에서 할당 된 토큰) 메타 데이터에 사용 되는 실제 FileDef 토큰을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a743-103">Retrieves the actual FileDef token used in metadata (as opposed to the token assigned by ALink).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a743-104">구문</span><span class="sxs-lookup"><span data-stu-id="5a743-104">Syntax</span></span>  
  
```  
HRESULT GetFileDef(  
    mdAssembly AssemblyID,  
    mdFile TargetFile,  
    mdFile* pScope  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5a743-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5a743-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="5a743-106">어셈블리의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="5a743-106">ID of the assembly.</span></span>  
  
 `TargetFile`  
 <span data-ttu-id="5a743-107">토큰 추가 된 파일의 AddFile 메서드 또는 AddImport 메서드에서 검색 된 대로입니다.</span><span class="sxs-lookup"><span data-stu-id="5a743-107">Token of the added file as retrieved from AddFile Method or AddImport Method.</span></span>  
  
 `pScope`  
 <span data-ttu-id="5a743-108">FileDef 토큰을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="5a743-108">Receives the FileDef token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5a743-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="5a743-109">Return Value</span></span>  
 <span data-ttu-id="5a743-110">메서드가 성공 하면 S_OK를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a743-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5a743-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5a743-111">Requirements</span></span>  
 <span data-ttu-id="5a743-112">Alink.h 필요</span><span class="sxs-lookup"><span data-stu-id="5a743-112">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a743-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5a743-113">See Also</span></span>  
 [<span data-ttu-id="5a743-114">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5a743-114">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="5a743-115">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5a743-115">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="5a743-116">ALink API</span><span class="sxs-lookup"><span data-stu-id="5a743-116">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
