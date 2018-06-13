---
title: CreateIDispatchSTAForwarder 함수 (WPF 관리 되지 않는 API 참조)
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- CreateIDispatchSTAForwarder
api_location:
- PresentationHost_v0400.dll
ms.assetid: 57a02dfa-f091-4ace-9c06-1f4ab52b3527
ms.openlocfilehash: f7e45d5cafa40ba147fe39888e74a67ac9f95c5b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33536653"
---
# <a name="createidispatchstaforwarder-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="a65b0-102">CreateIDispatchSTAForwarder 함수 (WPF 관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="a65b0-102">CreateIDispatchSTAForwarder Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="a65b0-103">이 API는 Windows Presentation Foundation (WPF) 인프라를 지원 하며 사용자 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a65b0-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="a65b0-104">스레드 및 창 관리를 위한 Windows Presentation Foundation (WPF) 인프라에서 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a65b0-104">Used by the Windows Presentation Foundation (WPF) infrastructure for thread and windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a65b0-105">구문</span><span class="sxs-lookup"><span data-stu-id="a65b0-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateIDispatchSTAForwarder(  
   __in IDispatch *pDispatchDelegate,   
   __deref_out IDispatch **ppForwarder  
)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a65b0-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a65b0-106">Parameters</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="a65b0-107">속성 값/반환 값</span><span class="sxs-lookup"><span data-stu-id="a65b0-107">Property Value/Return Value</span></span>  
 <span data-ttu-id="a65b0-108">pDispatchDelegate</span><span class="sxs-lookup"><span data-stu-id="a65b0-108">pDispatchDelegate</span></span>  
 <span data-ttu-id="a65b0-109">에 대 한 포인터는 `IDispatch` 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="a65b0-109">A pointer to an `IDispatch` interface.</span></span>  
  
 <span data-ttu-id="a65b0-110">ppForwarder</span><span class="sxs-lookup"><span data-stu-id="a65b0-110">ppForwarder</span></span>  
 <span data-ttu-id="a65b0-111">주소에 대 한 포인터는 `IDispatch` 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="a65b0-111">A pointer to the address of an `IDispatch` interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a65b0-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a65b0-112">Requirements</span></span>  
 <span data-ttu-id="a65b0-113">**플랫폼:** 참조 [.NET Framework 시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a65b0-113">**Platforms:** See [.NET Framework System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a65b0-114">**DLL:**</span><span class="sxs-lookup"><span data-stu-id="a65b0-114">**DLL:**</span></span>  
  
 <span data-ttu-id="a65b0-115">.NET framework 3.0 및 3.5: PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="a65b0-115">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="a65b0-116">.NET Framework 4 이상: PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="a65b0-116">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="a65b0-117">**.NET framework 버전:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a65b0-117">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a65b0-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a65b0-118">See Also</span></span>  
 [<span data-ttu-id="a65b0-119">F 관리되지 않는 API 참조</span><span class="sxs-lookup"><span data-stu-id="a65b0-119">WPF Unmanaged API Reference</span></span>](../../../../docs/framework/wpf/advanced/wpf-unmanaged-api-reference.md)
