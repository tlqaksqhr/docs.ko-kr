---
title: "추가 기능 및 확장성"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- extensibility [.NET Framework], add-ins
- add-ins [.NET Framework]
- add-ins [.NET Framework], about
- hosts [.NET Framework], compared to add-ins
- .NET Framework, add-ins
- add-in pipeline [.NET Framework], about
- add-ins [.NET Framework], compared to hosts
- .NET Framework, extensibility
- versioning [.NET Framework], add-ins
ms.assetid: 8dd45b02-7218-40f9-857d-40d7b98b850b
caps.latest.revision: "42"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7e4d336992be216178b1237c9f43bffb3de61fba
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="add-ins-and-extensibility"></a><span data-ttu-id="267dc-102">추가 기능 및 확장성</span><span class="sxs-lookup"><span data-stu-id="267dc-102">Add-ins and Extensibility</span></span>
<a name="top"></a> <span data-ttu-id="267dc-103">추가 기능은 호스트 응용 프로그램에 대한 확장명 기능이나 서비스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="267dc-103">Add-ins provide extended features or services for a host application.</span></span> <span data-ttu-id="267dc-104">[!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] 에서는 개발자가 추가 기능을 개발하고 호스트 응용 프로그램에서 활성화하는 데 사용할 수 있는 프로그래밍 모델을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="267dc-104">The [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] provides a programming model that developers can use to develop add-ins and activate them in their host application.</span></span> <span data-ttu-id="267dc-105">모델은 이 작업을 위해 호스트와 추가 기능 간에 통신 파이프라인을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="267dc-105">The model achieves this by constructing a communication pipeline between the host and the add-in.</span></span> <span data-ttu-id="267dc-106">모델은 <xref:System.AddIn>, <xref:System.AddIn.Hosting>, <xref:System.AddIn.Pipeline>및 <xref:System.AddIn.Contract> 네임스페이스의 형식을 사용하여 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="267dc-106">The model is implemented by using the types in the <xref:System.AddIn>, <xref:System.AddIn.Hosting>, <xref:System.AddIn.Pipeline>, and <xref:System.AddIn.Contract> namespaces.</span></span>  
  
 <span data-ttu-id="267dc-107">이 개요는 다음과 같은 단원으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="267dc-107">This overview contains the following sections:</span></span>  
  
-   [<span data-ttu-id="267dc-108">추가 기능 모델</span><span class="sxs-lookup"><span data-stu-id="267dc-108">Add-in Model</span></span>](#addin_model)  
  
-   [<span data-ttu-id="267dc-109">추가 기능 및 호스트 구별</span><span class="sxs-lookup"><span data-stu-id="267dc-109">Distinguishing Between Add-ins and Hosts</span></span>](#distinguishing_between_addins_and_hosts)  
  
-   [<span data-ttu-id="267dc-110">관련 항목</span><span class="sxs-lookup"><span data-stu-id="267dc-110">Related Topics</span></span>](#related_topics)  
  
-   [<span data-ttu-id="267dc-111">참조</span><span class="sxs-lookup"><span data-stu-id="267dc-111">Reference</span></span>](#reference)  
  
> [!NOTE]
>  <span data-ttu-id="267dc-112">추가 기능 파이프라인 빌드를 위한 도구의 고객 기술 미리 보기 및 추가 샘플 코드는 [CodePlex의 관리되는 확장성 및 추가 기능 프레임워크 사이트](http://go.microsoft.com/fwlink/?LinkId=121190)(영문)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="267dc-112">You can find additional sample code, and customer technology previews of tools for building add-in pipelines, at the [Managed Extensibility and Add-In Framework site on CodePlex](http://go.microsoft.com/fwlink/?LinkId=121190).</span></span>  
  
<a name="addin_model"></a>   
## <a name="add-in-model"></a><span data-ttu-id="267dc-113">추가 기능 모델</span><span class="sxs-lookup"><span data-stu-id="267dc-113">Add-in Model</span></span>  
 <span data-ttu-id="267dc-114">추가 기능 모델은 추가 기능과 호스트 간의 모든 통신을 담당하는, 추가 기능 파이프라인(통신 파이프라인이라고도 함)을 구성하는 일련의 세그먼트로 이루어져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="267dc-114">The add-in model consists of a series of segments that make up the add-in pipeline (also known as the communication pipeline), that is responsible for all communication between the add-in and the host.</span></span> <span data-ttu-id="267dc-115">파이프라인은 추가 기능과 해당 호스트 간에 데이터를 교환하는 세그먼트의 대칭 통신 모델입니다.</span><span class="sxs-lookup"><span data-stu-id="267dc-115">The pipeline is a symmetrical communication model of segments that exchange data between an add-in and its host.</span></span> <span data-ttu-id="267dc-116">호스트와 추가 기능 간에 이러한 세그먼트를 개발하면 추가 기능의 버전 관리 및 격리를 지원하는 필수 추상화 계층이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="267dc-116">Developing these segments between the host and the add-in provides the required layers of abstraction that support versioning and isolation of the add-in.</span></span>  
  
 <span data-ttu-id="267dc-117">다음 그림에서는 파이프라인을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="267dc-117">The following illustration shows the pipeline.</span></span>  
  
 <span data-ttu-id="267dc-118">![추가 &#45; 파이프라인 모델입니다. ] (../../../docs/framework/add-ins/media/addin1.png "AddIn1")</span><span class="sxs-lookup"><span data-stu-id="267dc-118">![Add&#45;in pipeline model.](../../../docs/framework/add-ins/media/addin1.png "AddIn1")</span></span>  
<span data-ttu-id="267dc-119">추가 기능 파이프라인</span><span class="sxs-lookup"><span data-stu-id="267dc-119">Add-in pipeline</span></span>  
  
 <span data-ttu-id="267dc-120">이러한 세그먼트에 대한 어셈블리가 동일한 응용 프로그램 도메인에 있을 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="267dc-120">The assemblies for these segments are not required to be in the same application domain.</span></span> <span data-ttu-id="267dc-121">고유한 새 응용 프로그램 도메인, 기존 응용 프로그램 도메인 또는 호스트의 응용 프로그램 도메인에 추가 기능을 로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="267dc-121">You can load an add-in into its own new application domain, into an existing application domain, or even into the host's application domain.</span></span> <span data-ttu-id="267dc-122">동일한 응용 프로그램 도메인에 여러 추가 기능을 로드할 수 있으며, 이 경우 추가 기능이 리소스와 보안 컨텍스트를 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="267dc-122">You can load multiple add-ins into the same application domain, which enables the add-ins to share resources and security contexts.</span></span>  
  
 <span data-ttu-id="267dc-123">추가 기능 모델은 호스트와 추가 기능 간에 격리 경계(원격 경계라고도 함)라는 선택적 경계를 지원하고 권장합니다.</span><span class="sxs-lookup"><span data-stu-id="267dc-123">The add-in model supports, and recommends, an optional boundary between the host and the add-in, which is called the isolation boundary (also known as a remoting boundary).</span></span> <span data-ttu-id="267dc-124">이 경계는 응용 프로그램 도메인 또는 프로세스 경계일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="267dc-124">This boundary can be an application domain or process boundary.</span></span>  
  
 <span data-ttu-id="267dc-125">파이프라인 중간에 있는 계약 세그먼트는 호스트의 응용 프로그램 도메인과 추가 기능의 응용 프로그램 도메인 둘 다에 로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="267dc-125">The contract segment in the middle of the pipeline is loaded into both the host's application domain and the add-in's application domain.</span></span> <span data-ttu-id="267dc-126">계약은 호스트와 추가 기능이 서로 형식을 교환하는 데 사용하는 가상 메서드를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="267dc-126">The contract defines the virtual methods that the host and the add-in use to exchange types with each other.</span></span>  
  
 <span data-ttu-id="267dc-127">격리 경계를 통과하려면 형식이 계약 또는 직렬화 가능 형식이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="267dc-127">To pass through the isolation boundary, types must be either contracts or serializable types.</span></span> <span data-ttu-id="267dc-128">계약 또는 직렬화 가능 형식이 아닌 형식은 파이프라인의 어댑터 세그먼트에 의해 계약으로 변환되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="267dc-128">Types that are not contracts or serializable types must be converted to contracts by the adapter segments in the pipeline.</span></span>  
  
 <span data-ttu-id="267dc-129">파이프라인의 보기 세그먼트는 계약에 정의된 대로 호스트와 추가 기능에 공유하는 메서드 뷰를 제공하는 추상 기본 클래스 또는 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="267dc-129">The view segments of the pipeline are abstract base classes or interfaces that provide the host and the add-in with a view of the methods that they share, as defined by the contract.</span></span>  
  
 <span data-ttu-id="267dc-130">파이프라인 세그먼트 개발에 대한 자세한 내용은 [Pipeline Development](../../../docs/framework/add-ins/pipeline-development.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="267dc-130">For more information about developing pipeline segments, see [Pipeline Development](../../../docs/framework/add-ins/pipeline-development.md).</span></span>  
  
 <span data-ttu-id="267dc-131">이후 섹션에서는 추가 기능 모델의 기능을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="267dc-131">The sections that follow describe the features of the add-in model.</span></span>  
  
### <a name="independent-versioning"></a><span data-ttu-id="267dc-132">독립된 버전 관리</span><span class="sxs-lookup"><span data-stu-id="267dc-132">Independent Versioning</span></span>  
 <span data-ttu-id="267dc-133">추가 기능 모델을 사용하면 호스트와 추가 기능 버전을 독립적으로 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="267dc-133">The add-in model allows hosts and add-ins to version independently.</span></span> <span data-ttu-id="267dc-134">따라서 추가 기능 모델은 다음 시나리오를 가능하게 합니다.</span><span class="sxs-lookup"><span data-stu-id="267dc-134">As a result, the add-in model enables the following scenarios:</span></span>  
  
-   <span data-ttu-id="267dc-135">호스트가 이전 버전의 호스트용으로 빌드된 추가 기능을 사용할 수 있게 해주는 어댑터 만들기</span><span class="sxs-lookup"><span data-stu-id="267dc-135">Creating an adapter that enables a host to use an add-in built for a previous version of the host.</span></span>  
  
-   <span data-ttu-id="267dc-136">호스트가 이후 버전의 호스트용으로 빌드된 추가 기능을 사용할 수 있게 해주는 어댑터 만들기</span><span class="sxs-lookup"><span data-stu-id="267dc-136">Creating an adapter that enables a host to use an add-in built for a later version of the host.</span></span>  
  
-   <span data-ttu-id="267dc-137">호스트가 다른 호스트용으로 빌드된 추가 기능을 사용할 수 있게 해주는 어댑터 만들기</span><span class="sxs-lookup"><span data-stu-id="267dc-137">Creating an adapter that enables a host to use add-ins built for a different host.</span></span>  
  
### <a name="discovery-and-activation"></a><span data-ttu-id="267dc-138">검색 및 활성화</span><span class="sxs-lookup"><span data-stu-id="267dc-138">Discovery and Activation</span></span>  
 <span data-ttu-id="267dc-139">정보 저장소에서 발견된 추가 기능을 나타내는 컬렉션의 토큰을 사용하여 추가 기능을 활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="267dc-139">You can activate an add-in by using a token from a collection that represents the add-ins found from an information store.</span></span> <span data-ttu-id="267dc-140">추가 기능은 추가 기능의 호스트 뷰를 정의하는 형식을 검색하여 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="267dc-140">Add-ins are found by searching for the type that defines the host's view of the add-in.</span></span> <span data-ttu-id="267dc-141">추가 기능을 정의하는 형식을 기준으로 특정 추가 기능을 찾을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="267dc-141">You can also find a specific add-in by the type that defines the add-in.</span></span> <span data-ttu-id="267dc-142">정보 저장소는 파이프라인 저장소와 추가 기능 저장소라는 두 개의 캐시 파일로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="267dc-142">The information store consists of two cache files: the pipeline store and the add-in store.</span></span>  
  
 <span data-ttu-id="267dc-143">정보 저장소를 업데이트 및 다시 빌드하는 방법에 대한 자세한 내용은 [추가 기능 검색](http://msdn.microsoft.com/en-us/5d268dde-11df-4c4d-a022-f58d88bbc421)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="267dc-143">For information about updating and rebuilding the information store, see [Add-in Discovery](http://msdn.microsoft.com/en-us/5d268dde-11df-4c4d-a022-f58d88bbc421).</span></span> <span data-ttu-id="267dc-144">추가 기능을 활성화하는 방법에 대한 자세한 내용은 [추가 기능 활성화](http://msdn.microsoft.com/en-us/bedcbcdf-5964-4215-b5f3-3299798b2b3f) 및 [방법: 다양한 격리 및 보안으로 추가 기능 활성화](http://msdn.microsoft.com/en-us/7afe7ec8-5158-4350-9119-5df0ecab8aa5)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="267dc-144">For information about activating add-ins, see [Add-in Activation](http://msdn.microsoft.com/en-us/bedcbcdf-5964-4215-b5f3-3299798b2b3f) and [How to: Activate Add-ins with Different Isolation and Security](http://msdn.microsoft.com/en-us/7afe7ec8-5158-4350-9119-5df0ecab8aa5).</span></span>  
  
### <a name="isolation-levels-and-external-processes"></a><span data-ttu-id="267dc-145">격리 수준 및 외부 프로세스</span><span class="sxs-lookup"><span data-stu-id="267dc-145">Isolation Levels and External Processes</span></span>  
 <span data-ttu-id="267dc-146">추가 기능 모델은 추가 기능과 해당 호스트 간에 또는 추가 기능 간에 여러 수준의 격리를 지원합니다. 최소 격리부터 시작하여 이러한 수준은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="267dc-146">The add-in model supports several levels of isolation between an add-in and its host or between add-ins. Starting from the least isolated, these levels are as follows:</span></span>  
  
-   <span data-ttu-id="267dc-147">추가 기능이 호스트와 동일한 응용 프로그램 도메인에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="267dc-147">The add-in runs in the same application domain as the host.</span></span> <span data-ttu-id="267dc-148">이 경우 다른 응용 프로그램 도메인을 사용할 때 얻을 수 있는 격리 및 언로드 기능이 손실되므로 권장되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="267dc-148">This is not recommended because you lose the isolation and unloading capabilities that you get when you use different application domains.</span></span>  
  
-   <span data-ttu-id="267dc-149">여러 추가 기능이 호스트에서 사용하는 응용 프로그램 도메인과 다른 동일한 응용 프로그램 도메인에 로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="267dc-149">Multiple add-ins are loaded into the same application domain that is different from the application domain used by the host.</span></span>  
  
-   <span data-ttu-id="267dc-150">각 추가 기능이 배타적으로 고유한 응용 프로그램 도메인에 로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="267dc-150">Each add-in is loaded exclusively into its own application domain.</span></span> <span data-ttu-id="267dc-151">이는 가장 일반적인 격리 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="267dc-151">This is the most common level of isolation.</span></span>  
  
-   <span data-ttu-id="267dc-152">여러 추가 기능이 외부 프로세스에서 동일한 응용 프로그램 도메인에 로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="267dc-152">Multiple add-ins are loaded into the same application domain in an external process.</span></span>  
  
-   <span data-ttu-id="267dc-153">각 추가 기능이 외부 프로세스에서 배타적으로 고유한 응용 프로그램 도메인에 로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="267dc-153">Each add-in is loaded exclusively into its own application domain in an external process.</span></span> <span data-ttu-id="267dc-154">이는 가장 격리된 시나리오입니다.</span><span class="sxs-lookup"><span data-stu-id="267dc-154">This is the most isolated scenario.</span></span>  
  
 <span data-ttu-id="267dc-155">외부 프로세스를 사용하는 방법에 대한 자세한 내용은 [방법: 다양한 격리 및 보안으로 추가 기능 활성화](http://msdn.microsoft.com/en-us/7afe7ec8-5158-4350-9119-5df0ecab8aa5)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="267dc-155">For more information about using external processes, see [How to: Activate Add-ins with Different Isolation and Security](http://msdn.microsoft.com/en-us/7afe7ec8-5158-4350-9119-5df0ecab8aa5).</span></span>  
  
### <a name="lifetime-management"></a><span data-ttu-id="267dc-156">수명 관리</span><span class="sxs-lookup"><span data-stu-id="267dc-156">Lifetime Management</span></span>  
 <span data-ttu-id="267dc-157">추가 기능 모델은 응용 프로그램 도메인 및 프로세스 경계에 걸쳐 있으므로 가비지 수집만으로는 개체를 해제하고 확보하기에 충분하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="267dc-157">Because the add-in model spans application domain and process boundaries, garbage collection by itself is not sufficient to release and reclaim objects.</span></span> <span data-ttu-id="267dc-158">추가 기능 모델은 토큰 및 참조 횟수를 사용하며 일반적으로 추가 프로그래밍이 필요하지 않은 수명 관리 메커니즘을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="267dc-158">The add-in model provides a lifetime management mechanism that uses tokens and reference counting, and usually does not require additional programming.</span></span> <span data-ttu-id="267dc-159">자세한 내용은 [수명 관리](http://msdn.microsoft.com/en-us/57a9c87e-394c-4fef-89f2-aa4223a2aeb5)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="267dc-159">For more information, see [Lifetime Management](http://msdn.microsoft.com/en-us/57a9c87e-394c-4fef-89f2-aa4223a2aeb5).</span></span>  
  
 [<span data-ttu-id="267dc-160">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="267dc-160">Back to top</span></span>](#top)  
  
<a name="distinguishing_between_addins_and_hosts"></a>   
## <a name="distinguishing-between-add-ins-and-hosts"></a><span data-ttu-id="267dc-161">추가 기능 및 호스트 구별</span><span class="sxs-lookup"><span data-stu-id="267dc-161">Distinguishing Between Add-ins and Hosts</span></span>  
 <span data-ttu-id="267dc-162">추가 기능과 호스트의 차이점은 단지 호스트가 추가 기능을 활성화한다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="267dc-162">The difference between an add-in and a host is merely that the host is the one that activates the add-in.</span></span> <span data-ttu-id="267dc-163">호스트는 워드프로세싱 응용 프로그램과 해당 맞춤법 검사기와 같이 둘 중에서 더 큰 것이거나, 미디어 플레이어를 포함하는 인스턴트 메시징 클라이언트와 같이 둘 중에서 더 작은 것일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="267dc-163">The host can be the larger of the two, such as a word processing application and its spell checkers; or the host can be the smaller of the two, such as an instant messaging client that embeds a media player.</span></span> <span data-ttu-id="267dc-164">추가 기능 모델은 클라이언트 및 서버 시나리오 둘 다에서 추가 기능을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="267dc-164">The add-in model supports add-ins in both client and server scenarios.</span></span> <span data-ttu-id="267dc-165">서버 추가 기능의 예로는 메일 서버에 바이러스 검사, 스팸 필터 및 IP 보호를 제공하는 추가 기능이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="267dc-165">Examples of server add-ins include add-ins that provide mail servers with virus scanning, spam filters, and IP protection.</span></span> <span data-ttu-id="267dc-166">클라이언트 추가 기능의 예로는 워드프로세서용 참조 추가 기능, 그래픽 프로그램 및 게임용 특수 기능 및 로컬 전자 메일 클라이언트용 바이러스 검색이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="267dc-166">Client add-in examples include reference add-ins for word processors, specialized features for graphics programs and games, and virus scanning for local e-mail clients.</span></span>  
  
 [<span data-ttu-id="267dc-167">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="267dc-167">Back to top</span></span>](#top)  
  
<a name="related_topics"></a>   
## <a name="related-topics"></a><span data-ttu-id="267dc-168">관련 항목</span><span class="sxs-lookup"><span data-stu-id="267dc-168">Related Topics</span></span>  
  
|<span data-ttu-id="267dc-169">제목</span><span class="sxs-lookup"><span data-stu-id="267dc-169">Title</span></span>|<span data-ttu-id="267dc-170">설명</span><span class="sxs-lookup"><span data-stu-id="267dc-170">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="267dc-171">Pipeline Development</span><span class="sxs-lookup"><span data-stu-id="267dc-171">Pipeline Development</span></span>](../../../docs/framework/add-ins/pipeline-development.md)|<span data-ttu-id="267dc-172">호스트 응용 프로그램과 추가 기능 간의 세그먼트 통신 파이프라인을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="267dc-172">Describes the communication pipeline of segments from the host application to the add-in.</span></span> <span data-ttu-id="267dc-173">파이프라인을 생성하는 방법 및 [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]에서 세그먼트를 파이프라인에 배포하는 방법을 설명하는 코드 예제를 연습 항목에서 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="267dc-173">Provides code examples in walkthrough topics that describe how to construct the pipeline and how to deploy segments to the pipeline in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].</span></span>|  
|[<span data-ttu-id="267dc-174">응용 프로그램 도메인 및 어셈블리</span><span class="sxs-lookup"><span data-stu-id="267dc-174">Application Domains and Assemblies</span></span>](http://msdn.microsoft.com/en-us/433b04ae-4ba8-4849-9dbd-79194f240346)|<span data-ttu-id="267dc-175">보안, 안정성 및 버전 관리를 위한 격리 경계를 제공하는 응용 프로그램 도메인과 어셈블리 간의 관계를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="267dc-175">Describes the relationship between application domains, which provide an isolation boundary for security, reliability, and versioning, and assemblies.</span></span>|  
  
 [<span data-ttu-id="267dc-176">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="267dc-176">Back to top</span></span>](#top)  
  
<a name="reference"></a>   
## <a name="reference"></a><span data-ttu-id="267dc-177">참조</span><span class="sxs-lookup"><span data-stu-id="267dc-177">Reference</span></span>  
 <xref:System.AddIn?displayProperty=nameWithType>  
  
 <xref:System.AddIn.Contract?displayProperty=nameWithType>  
  
 <xref:System.AddIn.Hosting?displayProperty=nameWithType>  
  
 <xref:System.AddIn.Pipeline?displayProperty=nameWithType>  
  
 [<span data-ttu-id="267dc-178">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="267dc-178">Back to top</span></span>](#top)