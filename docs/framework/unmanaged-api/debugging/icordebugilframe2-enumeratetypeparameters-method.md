---
title: "ICorDebugILFrame2::EnumerateTypeParameters 메서드"
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
- ICorDebugILFrame2.EnumerateTypeParameters
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame2::EnumerateTypeParameters
helpviewer_keywords:
- EnumerateTypeParameters method, ICorDebugILFrame2 interface [.NET Framework debugging]
- ICorDebugILFrame2::EnumerateTypeParameters method [.NET Framework debugging]
ms.assetid: 722d0d74-e0df-491f-98c4-62d501dfaf6f
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 9180ea68dde667ffe0dc8e15b98cb82efaa667ba
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugilframe2enumeratetypeparameters-method"></a><span data-ttu-id="bc862-102">ICorDebugILFrame2::EnumerateTypeParameters 메서드</span><span class="sxs-lookup"><span data-stu-id="bc862-102">ICorDebugILFrame2::EnumerateTypeParameters Method</span></span>
<span data-ttu-id="bc862-103">포함 된 ICorDebugTypeEnum 개체를 가져옵니다는 <xref:System.Type> 이 프레임에서 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="bc862-103">Gets an ICorDebugTypeEnum object that contains the <xref:System.Type> parameters in this frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc862-104">구문</span><span class="sxs-lookup"><span data-stu-id="bc862-104">Syntax</span></span>  
  
```  
HRESULT EnumerateTypeParameters (  
    [out] ICorDebugTypeEnum    **ppTyParEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bc862-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="bc862-105">Parameters</span></span>  
 `ppTyParEnum`  
 <span data-ttu-id="bc862-106">열거형의 형식 매개 변수를 허용 하는 ICorDebugTypeEnum 인터페이스 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="bc862-106">A pointer to the address of a ICorDebugTypeEnum interface object that allows enumeration of type parameters.</span></span>  
  
 <span data-ttu-id="bc862-107">형식 매개 변수 목록 클래스 형식 매개 변수 (있는 경우) 메서드 형식 매개 변수 뒤에 (있는 경우)를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc862-107">The list of type parameters include the class type parameters (if any) followed by the method type parameters (if any).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bc862-108">설명</span><span class="sxs-lookup"><span data-stu-id="bc862-108">Remarks</span></span>  
 <span data-ttu-id="bc862-109">사용 하 여는 [imetadataimport2:: Enumgenericparams](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-enumgenericparams-method.md) 수 클래스 형식 매개 변수 및 메서드 입력이 목록에 포함 하는 매개 변수를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc862-109">Use the [IMetaDataImport2::EnumGenericParams](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-enumgenericparams-method.md) method to determine how many class type parameters and method type parameters this list contains.</span></span>  
  
 <span data-ttu-id="bc862-110">형식 매개 변수는 항상 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc862-110">The type parameters are not always available.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bc862-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="bc862-111">Requirements</span></span>  
 <span data-ttu-id="bc862-112">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="bc862-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bc862-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bc862-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bc862-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bc862-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bc862-115">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bc862-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
