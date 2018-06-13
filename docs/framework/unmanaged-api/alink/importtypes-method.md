---
title: ImportTypes 메서드
ms.date: 03/30/2017
api_name:
- IALink.ImportTypes
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportTypes
helpviewer_keywords:
- ImportTypes method
ms.assetid: 351d4b4c-c939-486d-9471-51914a55f471
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 321038a148c27086ca499e2f448eb50cb93525ec
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33405514"
---
# <a name="importtypes-method"></a><span data-ttu-id="d1f89-102">ImportTypes 메서드</span><span class="sxs-lookup"><span data-stu-id="d1f89-102">ImportTypes Method</span></span>
<span data-ttu-id="d1f89-103">형식을 통해 가져온 각 범위에서 가져오기를 시작 [ImportFile 메서드](../../../../docs/framework/unmanaged-api/alink/importfile-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f89-103">Initiates the importing of types from each scope imported via [ImportFile Method](../../../../docs/framework/unmanaged-api/alink/importfile-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1f89-104">구문</span><span class="sxs-lookup"><span data-stu-id="d1f89-104">Syntax</span></span>  
  
```  
HRESULT ImportTypes(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    HALINKENUM* phEnum,  
    IMetaDataImport** ppImportScope,  
    DWORD* pdwCountOfTypes  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d1f89-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d1f89-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="d1f89-106">가져올 어셈블리의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="d1f89-106">ID of the assembly to import to.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="d1f89-107">가져올 파일의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="d1f89-107">ID of the file to import from.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="d1f89-108">가져올 범위 0부터 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f89-108">Zero-based scope to import.</span></span>  
  
 `phEnum`  
 <span data-ttu-id="d1f89-109">이 범위에는 형식에 대 한 열거자 핸들을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="d1f89-109">Receives enumerator handle for the types in this scope.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="d1f89-110">필요에 따라 받는 [IMetaDataImport 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="d1f89-110">Optionally receives [IMetaDataImport Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interface.</span></span>  
  
 `pdwCountOfTypes`  
 <span data-ttu-id="d1f89-111">필요에 따라 표시 된 범위의 형식의 수를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="d1f89-111">Optionally receives count of types in the indicated scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d1f89-112">반환 값</span><span class="sxs-lookup"><span data-stu-id="d1f89-112">Return Value</span></span>  
 <span data-ttu-id="d1f89-113">메서드가 성공 하면 S_OK를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f89-113">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d1f89-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d1f89-114">Requirements</span></span>  
 <span data-ttu-id="d1f89-115">Alink.h 필요</span><span class="sxs-lookup"><span data-stu-id="d1f89-115">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1f89-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d1f89-116">See Also</span></span>  
 [<span data-ttu-id="d1f89-117">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d1f89-117">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="d1f89-118">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d1f89-118">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="d1f89-119">ALink API</span><span class="sxs-lookup"><span data-stu-id="d1f89-119">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
