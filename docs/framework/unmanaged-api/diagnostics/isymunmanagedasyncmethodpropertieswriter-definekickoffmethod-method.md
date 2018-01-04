---
title: "ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 4662f70d-817b-4374-8da8-e0545585939f
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 691a46e20339b659b5df3136d4dca6c03a69d3d8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefinekickoffmethod-method"></a><span data-ttu-id="68059-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod 메서드</span><span class="sxs-lookup"><span data-stu-id="68059-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod Method</span></span>
<span data-ttu-id="68059-103">비동기 작업을 시작 하는 시작 메서드를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="68059-103">Sets the starting method that initiates the async operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="68059-104">구문</span><span class="sxs-lookup"><span data-stu-id="68059-104">Syntax</span></span>  
  
```idl  
HRESULT DefineKickoffMethod(    [in] mdToken kickoffMethod);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="68059-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="68059-105">Parameters</span></span>  
  
|<span data-ttu-id="68059-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="68059-106">Parameter</span></span>|<span data-ttu-id="68059-107">설명</span><span class="sxs-lookup"><span data-stu-id="68059-107">Description</span></span>|  
|---------------|-----------------|  
|`kickoffMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="68059-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="68059-108">Return Value</span></span>  
 <span data-ttu-id="68059-109">`HRESULT`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="68059-109">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="68059-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="68059-110">Requirements</span></span>  
 <span data-ttu-id="68059-111">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="68059-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68059-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="68059-112">See Also</span></span>  
 [<span data-ttu-id="68059-113">ISymUnmanagedAsyncMethodPropertiesWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="68059-113">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)
