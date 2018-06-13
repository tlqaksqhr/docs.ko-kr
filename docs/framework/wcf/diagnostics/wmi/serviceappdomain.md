---
title: ServiceAppDomain
ms.date: 03/30/2017
ms.assetid: f28e5186-a66d-46c1-abe9-b50e07f8cb4f
ms.openlocfilehash: aef0a0da9d107b92d9d3017968d5554205a6fd71
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33485670"
---
# <a name="serviceappdomain"></a><span data-ttu-id="fe87a-102">ServiceAppDomain</span><span class="sxs-lookup"><span data-stu-id="fe87a-102">ServiceAppDomain</span></span>
<span data-ttu-id="fe87a-103">서비스를 응용 프로그램 도메인에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="fe87a-103">Maps a service to an application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe87a-104">구문</span><span class="sxs-lookup"><span data-stu-id="fe87a-104">Syntax</span></span>  
  
```  
class ServiceAppDomain  
{  
  Service ref;  
  AppDomainInfo ref;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="fe87a-105">메서드</span><span class="sxs-lookup"><span data-stu-id="fe87a-105">Methods</span></span>  
 <span data-ttu-id="fe87a-106">ServiceAppDomain 클래스는 메서드를 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fe87a-106">The ServiceAppDomain class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="fe87a-107">속성</span><span class="sxs-lookup"><span data-stu-id="fe87a-107">Properties</span></span>  
 <span data-ttu-id="fe87a-108">ServiceAppDomain 클래스에는 다음 속성이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe87a-108">The ServiceAppDomain class has the following properties:</span></span>  
  
### <a name="ref"></a><span data-ttu-id="fe87a-109">ref</span><span class="sxs-lookup"><span data-stu-id="fe87a-109">ref</span></span>  
 <span data-ttu-id="fe87a-110">데이터 형식: Service</span><span class="sxs-lookup"><span data-stu-id="fe87a-110">Data type: Service</span></span>  
<span data-ttu-id="fe87a-111">한정자: Key</span><span class="sxs-lookup"><span data-stu-id="fe87a-111">Qualifiers: Key</span></span>  
  
 <span data-ttu-id="fe87a-112">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="fe87a-112">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fe87a-113">이 응용 프로그램 도메인의 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="fe87a-113">The service of this application domain.</span></span>  
  
### <a name="ref"></a><span data-ttu-id="fe87a-114">ref</span><span class="sxs-lookup"><span data-stu-id="fe87a-114">ref</span></span>  
 <span data-ttu-id="fe87a-115">데이터 형식: AppDomainInfo</span><span class="sxs-lookup"><span data-stu-id="fe87a-115">Data type: AppDomainInfo</span></span>  
<span data-ttu-id="fe87a-116">한정자: Key</span><span class="sxs-lookup"><span data-stu-id="fe87a-116">Qualifiers: Key</span></span>  
  
 <span data-ttu-id="fe87a-117">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="fe87a-117">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fe87a-118">응용 프로그램 도메인의 속성을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="fe87a-118">Contains properties of the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fe87a-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fe87a-119">Requirements</span></span>  
  
|<span data-ttu-id="fe87a-120">MOF</span><span class="sxs-lookup"><span data-stu-id="fe87a-120">MOF</span></span>|<span data-ttu-id="fe87a-121">Servicemodel.mof에 선언되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe87a-121">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="fe87a-122">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="fe87a-122">Namespace</span></span>|<span data-ttu-id="fe87a-123">root\ServiceModel에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe87a-123">Defined in root\ServiceModel</span></span>|
