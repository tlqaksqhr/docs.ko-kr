---
title: EnumImportTypes 메서드
ms.date: 03/30/2017
api_name:
- EnumImportTypes
- IALink.EnumImportTypes
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EnumImportTypes
helpviewer_keywords:
- EnumImportTypes method
ms.assetid: 83a0e4e7-ec06-40cb-9b63-700b9695bb04
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 90319886dfe149a3d2d76451c1a8526299cf5b89
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33401650"
---
# <a name="enumimporttypes-method"></a><span data-ttu-id="ec1fe-102">EnumImportTypes 메서드</span><span class="sxs-lookup"><span data-stu-id="ec1fe-102">EnumImportTypes Method</span></span>
<span data-ttu-id="ec1fe-103">각 범위에서 각 유형을 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="ec1fe-103">Enumerates each type in each scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec1fe-104">구문</span><span class="sxs-lookup"><span data-stu-id="ec1fe-104">Syntax</span></span>  
  
```  
HRESULT EnumImportTypes(  
    HALINKENUM   hEnum,  
    DWORD        dwMax,  
    mdTypeDef    aTypeDefs[],  
    DWORD*       pdwCount  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ec1fe-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ec1fe-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="ec1fe-106">열거자에 대 한 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="ec1fe-106">Handle for enumerator.</span></span>  
  
 `dwMax`  
 <span data-ttu-id="ec1fe-107">검색할 형식의 최대 수입니다.</span><span class="sxs-lookup"><span data-stu-id="ec1fe-107">Maximum number of types to retrieve.</span></span>  
  
 `aTypeDefs`  
 <span data-ttu-id="ec1fe-108">형식 토큰을 넘지 받습니다 `dwMax`합니다.</span><span class="sxs-lookup"><span data-stu-id="ec1fe-108">Recieves type tokens, not to exceed `dwMax`.</span></span>  
  
 `pdwCount`  
 <span data-ttu-id="ec1fe-109">형식의 실제 수를 받는 `aTypeDefs`합니다.</span><span class="sxs-lookup"><span data-stu-id="ec1fe-109">Receives actual number of type in `aTypeDefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ec1fe-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="ec1fe-110">Return Value</span></span>  
 <span data-ttu-id="ec1fe-111">메서드가 성공 하면 S_OK를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec1fe-111">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ec1fe-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ec1fe-112">Requirements</span></span>  
 <span data-ttu-id="ec1fe-113">Alink.h 필요</span><span class="sxs-lookup"><span data-stu-id="ec1fe-113">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec1fe-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ec1fe-114">See Also</span></span>  
 [<span data-ttu-id="ec1fe-115">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ec1fe-115">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="ec1fe-116">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ec1fe-116">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="ec1fe-117">ALink API</span><span class="sxs-lookup"><span data-stu-id="ec1fe-117">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
