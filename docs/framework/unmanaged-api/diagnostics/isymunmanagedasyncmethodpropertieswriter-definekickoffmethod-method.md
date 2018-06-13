---
title: ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod 메서드
ms.date: 03/30/2017
ms.assetid: 4662f70d-817b-4374-8da8-e0545585939f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a476d92486d7f2523dfbcc8b25e9c11e26c55f2d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33425617"
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefinekickoffmethod-method"></a><span data-ttu-id="a5534-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod 메서드</span><span class="sxs-lookup"><span data-stu-id="a5534-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod Method</span></span>
<span data-ttu-id="a5534-103">비동기 작업을 시작 하는 시작 메서드를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5534-103">Sets the starting method that initiates the async operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5534-104">구문</span><span class="sxs-lookup"><span data-stu-id="a5534-104">Syntax</span></span>  
  
```idl  
HRESULT DefineKickoffMethod(    [in] mdToken kickoffMethod);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a5534-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a5534-105">Parameters</span></span>  
  
|<span data-ttu-id="a5534-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a5534-106">Parameter</span></span>|<span data-ttu-id="a5534-107">설명</span><span class="sxs-lookup"><span data-stu-id="a5534-107">Description</span></span>|  
|---------------|-----------------|  
|`kickoffMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="a5534-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="a5534-108">Return Value</span></span>  
 <span data-ttu-id="a5534-109">`HRESULT`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="a5534-109">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a5534-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a5534-110">Requirements</span></span>  
 <span data-ttu-id="a5534-111">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="a5534-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5534-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a5534-112">See Also</span></span>  
 [<span data-ttu-id="a5534-113">ISymUnmanagedAsyncMethodPropertiesWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a5534-113">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)
