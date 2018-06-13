---
title: ICLRDomainManager 인터페이스
ms.date: 03/30/2017
api_name:
- ICLRDomainManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDomainManager
helpviewer_keywords:
- ICLRDomainManager interface [.NET Framework hosting]
ms.assetid: f08b2390-d872-4521-a815-e9c237c4c45d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c3b8dd67cb7dff4bec5bab192a08461ef13fcbd9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33436360"
---
# <a name="iclrdomainmanager-interface"></a><span data-ttu-id="a3b3f-102">ICLRDomainManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a3b3f-102">ICLRDomainManager Interface</span></span>
<span data-ttu-id="a3b3f-103">호스트를에서 기본 응용 프로그램 도메인을 초기화 하 고 초기화 속성을 지정 하는 데 사용 될 응용 프로그램 도메인 관리자를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3b3f-103">Enables the host to specify the application domain manager that will be used to initialize the default application domain, and to specify initialization properties.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a3b3f-104">메서드</span><span class="sxs-lookup"><span data-stu-id="a3b3f-104">Methods</span></span>  
  
|<span data-ttu-id="a3b3f-105">메서드</span><span class="sxs-lookup"><span data-stu-id="a3b3f-105">Method</span></span>|<span data-ttu-id="a3b3f-106">설명</span><span class="sxs-lookup"><span data-stu-id="a3b3f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a3b3f-107">SetAppDomainManagerType 메서드</span><span class="sxs-lookup"><span data-stu-id="a3b3f-107">SetAppDomainManagerType Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-setappdomainmanagertype-method.md)|<span data-ttu-id="a3b3f-108">파생 된 형식을 지정 된 <xref:System.AppDomainManager?displayProperty=nameWithType> 기본 응용 프로그램 도메인을 초기화 하는 데 사용할 응용 프로그램 도메인 관리자의 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="a3b3f-108">Specifies the type, derived from the <xref:System.AppDomainManager?displayProperty=nameWithType> class, of the application domain manager that will be used to initialize the default application domain.</span></span>|  
|[<span data-ttu-id="a3b3f-109">SetPropertiesForDefaultAppDomain 메서드</span><span class="sxs-lookup"><span data-stu-id="a3b3f-109">SetPropertiesForDefaultAppDomain Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-setpropertiesfordefaultappdomain-method.md)|<span data-ttu-id="a3b3f-110">기본 응용 프로그램 도메인 초기화를 사용할 수 있는 속성을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3b3f-110">Sets properties that will be used to initialize the default application domain.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a3b3f-111">설명</span><span class="sxs-lookup"><span data-stu-id="a3b3f-111">Remarks</span></span>  
 <span data-ttu-id="a3b3f-112">이 인터페이스의 인스턴스를 호출 하는 [iclrcontrol:: Getclrmanager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) IID 관리자 유형 사용 하 여 메서드 `IID_ICLRDomainManager`합니다.</span><span class="sxs-lookup"><span data-stu-id="a3b3f-112">To get an instance of this interface, call the [ICLRControl::GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) method with the manager type IID `IID_ICLRDomainManager`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a3b3f-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a3b3f-113">Requirements</span></span>  
 <span data-ttu-id="a3b3f-114">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a3b3f-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a3b3f-115">**헤더:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="a3b3f-115">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="a3b3f-116">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="a3b3f-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a3b3f-117">**.NET framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a3b3f-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3b3f-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a3b3f-118">See Also</span></span>  
 [<span data-ttu-id="a3b3f-119">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a3b3f-119">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="a3b3f-120">호스팅</span><span class="sxs-lookup"><span data-stu-id="a3b3f-120">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
