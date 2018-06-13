---
title: Init 메서드
ms.date: 03/30/2017
api_name:
- IALink.Init
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- Init
helpviewer_keywords:
- Init method
ms.assetid: e48b5c64-049f-4f93-ad87-d07ae9cd5845
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b512389078ab022208c4b163edc8501a900669ac
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33400366"
---
# <a name="init-method"></a><span data-ttu-id="6435e-102">Init 메서드</span><span class="sxs-lookup"><span data-stu-id="6435e-102">Init Method</span></span>
<span data-ttu-id="6435e-103">구현 하는 개체를 준비는 [IALink 인터페이스](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md) 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6435e-103">Prepares objects implementing the [IALink Interface](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md) for use.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6435e-104">구문</span><span class="sxs-lookup"><span data-stu-id="6435e-104">Syntax</span></span>  
  
```  
HRESULT Init(  
    IMetaDataDispenserEx* pDispenser,  
    IMetaDataError* pErrorHandler  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6435e-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6435e-105">Parameters</span></span>  
 `pDispenser`  
 <span data-ttu-id="6435e-106">[IMetaDataDispenserEx 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md) 메타 데이터 디스펜서에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="6435e-106">[IMetaDataDispenserEx Interface](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md) pointer to the metadata dispenser.</span></span>  
  
 `pErrorHandler`  
 <span data-ttu-id="6435e-107">[IMetaDataError 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataerror-interface.md) 인터페이스를 처리 하는 선택적 오류에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="6435e-107">[IMetaDataError Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataerror-interface.md) pointer to an optional error handling interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6435e-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="6435e-108">Return Value</span></span>  
 <span data-ttu-id="6435e-109">메서드가 성공 하면 S_OK를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="6435e-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6435e-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6435e-110">Requirements</span></span>  
 <span data-ttu-id="6435e-111">Alink.h 필요</span><span class="sxs-lookup"><span data-stu-id="6435e-111">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6435e-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6435e-112">See Also</span></span>  
 [<span data-ttu-id="6435e-113">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6435e-113">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="6435e-114">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6435e-114">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="6435e-115">ALink API</span><span class="sxs-lookup"><span data-stu-id="6435e-115">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
