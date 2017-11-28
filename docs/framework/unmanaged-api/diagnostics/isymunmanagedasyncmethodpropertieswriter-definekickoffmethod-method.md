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
ms.openlocfilehash: 68c5d6662d8cbecca06268bd5010878c4e476f47
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefinekickoffmethod-method"></a><span data-ttu-id="b4b0b-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod 메서드</span><span class="sxs-lookup"><span data-stu-id="b4b0b-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod Method</span></span>
<span data-ttu-id="b4b0b-103">비동기 작업을 시작 하는 시작 메서드를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4b0b-103">Sets the starting method that initiates the async operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4b0b-104">구문</span><span class="sxs-lookup"><span data-stu-id="b4b0b-104">Syntax</span></span>  
  
```idl  
HRESULT DefineKickoffMethod(    [in] mdToken kickoffMethod);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b4b0b-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b4b0b-105">Parameters</span></span>  
  
|<span data-ttu-id="b4b0b-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b4b0b-106">Parameter</span></span>|<span data-ttu-id="b4b0b-107">설명</span><span class="sxs-lookup"><span data-stu-id="b4b0b-107">Description</span></span>|  
|---------------|-----------------|  
|`kickoffMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="b4b0b-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="b4b0b-108">Return Value</span></span>  
 <span data-ttu-id="b4b0b-109">`HRESULT`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="b4b0b-109">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b4b0b-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b4b0b-110">Requirements</span></span>  
 <span data-ttu-id="b4b0b-111">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="b4b0b-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4b0b-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b4b0b-112">See Also</span></span>  
 [<span data-ttu-id="b4b0b-113">ISymUnmanagedAsyncMethodPropertiesWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b4b0b-113">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)
