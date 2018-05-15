---
title: 컨테이너 기반 응용 프로그램에 대 한 Azure 계산 플랫폼 선택
description: Azure 클라우드 및 Windows 컨테이너와 기존.NET 응용 프로그램을 최신식 | 컨테이너 기반 응용 프로그램에 대 한 Azure 계산 플랫폼 선택
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/04/2018
ms.openlocfilehash: ebf022a52aaaf95ae335976f5e097921b0ac8006
ms.sourcegitcommit: 88f251b08bf0718ce119f3d7302f514b74895038
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/10/2018
---
# <a name="choosing-azure-compute-platforms-for-container-based-applications"></a><span data-ttu-id="f5841-103">컨테이너 기반 응용 프로그램에 대 한 Azure 계산 플랫폼 선택</span><span class="sxs-lookup"><span data-stu-id="f5841-103">Choosing Azure compute platforms for container-based applications</span></span>

<span data-ttu-id="f5841-104">이전 섹션을 읽은 후 이미 알고 있는 대로 Azure는 여러 선택 항목을 제공 하는 개방형 클라우드입니다.</span><span class="sxs-lookup"><span data-stu-id="f5841-104">As you have noticed after reading the previous sections, Azure is an open cloud that offers multiple choices.</span></span> <span data-ttu-id="f5841-105">하지만 요구 사항에 가장 적합 한 것을 사용할 수 있습니다, 어떤 제품/기술의 컨테이너 화 된 응용 프로그램에 사용 해야 하는 방법에 대 한 질문에서는 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="f5841-105">You can use the best fit for your needs, however, it also surfaces questions about what product/technology you should use for your containerized applications.</span></span>

<span data-ttu-id="f5841-106">로 *기본적으로* 권장 사항, 다음은이 설명서에서 권장 하는 주요 조건:</span><span class="sxs-lookup"><span data-stu-id="f5841-106">As a *by-default* recommendation, the following is the main criteria recommended in this guidance:</span></span>

  - <span data-ttu-id="f5841-107">**단일 구식 응용 프로그램:** Azure 앱 서비스 선택</span><span class="sxs-lookup"><span data-stu-id="f5841-107">**Single monolithic app:** Choose Azure App Service</span></span>
  - <span data-ttu-id="f5841-108">**N 계층 응용 프로그램:** 한 개 또는 몇 백 엔드 서비스에 있는 경우 Azure Kubernetes 서비스 (AKS), 서비스 패브릭 (SF) 또는 응용 프로그램 서비스와 같은 orchestrators 선택</span><span class="sxs-lookup"><span data-stu-id="f5841-108">**N-Tier app:** Choose orchestrators such as Azure Kubernetes Service (AKS), Service Fabric (SF) or App Service if you have a single or few back-end services</span></span>
  - <span data-ttu-id="f5841-109">**Linux microservices:** AKS/Kubernetes 선택</span><span class="sxs-lookup"><span data-stu-id="f5841-109">**Linux microservices:** Choose AKS/Kubernetes</span></span>
  - <span data-ttu-id="f5841-110">**Windows microservices:** 서비스 패브릭 선택</span><span class="sxs-lookup"><span data-stu-id="f5841-110">**Windows microservices:** Choose Service Fabric</span></span>
  - <span data-ttu-id="f5841-111">**서버가 없는 함수 & 이벤트 처리기:** Azure 함수 선택</span><span class="sxs-lookup"><span data-stu-id="f5841-111">**Serverless functions & event handlers:** Choose Azure Functions</span></span>
  - <span data-ttu-id="f5841-112">**대량 일괄:** Azure 배치를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f5841-112">**Large-scale Batch:** Choose Azure Batch</span></span>

<span data-ttu-id="f5841-113">그러나이 권장 사항은 해야 수 수행 솔트, 축소와 제품의 선택은 특정 응용 프로그램의 요구 사항 및 특징에 따라 달라 집니다입니다.</span><span class="sxs-lookup"><span data-stu-id="f5841-113">However, this recommendation should be taken with a pinch of salt, as the product’s selection will depend on your specific application’s needs and characteristics.</span></span> <span data-ttu-id="f5841-114">일부 응용 프로그램 처음에 비슷한 형식이 계실 하는 경우에 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="f5841-114">Not all applications are the same even when initially they might look similar types.</span></span>

<span data-ttu-id="f5841-115">응용 프로그램의 요구에 대 한 심층 분석 한 후 선택한 제품에 다 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5841-115">After a deeper analysis of the application’s needs, the product selected could be different.</span></span> <span data-ttu-id="f5841-116">하지만, 시작 지점으로 지침 초기 평가 시작 하는 데 수 있게 되며 특정 우선 순위에 따라 테스트.</span><span class="sxs-lookup"><span data-stu-id="f5841-116">But, as a starting point, it is good to have initial guidance from where you can start evaluating and testing based on certain priority.</span></span>

<span data-ttu-id="f5841-117">다음 그림에 자세한 의사 결정 테이블 하는 동안 더 포괄적을 분석할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5841-117">In the next figure, you can analyze a more global while detailed decision table.</span></span>

![](./media/image8.5.png)

<span data-ttu-id="f5841-118">알림 방법을 기본 운영 체제 (Windows vs. 일부 orchestrators는 더 Linux 컨테이너에 완성도 높은 Windows 컨테이너에서 다른 Linux)는 의사 결정 요소를 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5841-118">Notice how the underlying OS (Windows vs. Linux) can also be a decision factor as some orchestrators are more mature on Linux containers and other on Windows containers.</span></span> <span data-ttu-id="f5841-119">예를 들어 Linux 컨테이너는 서비스 패브릭에서 덜 성숙한 하지만 Kubernetes (Azure에서 AKS)에서 매우 성숙한입니다.</span><span class="sxs-lookup"><span data-stu-id="f5841-119">For instance, Linux containers are very mature in Kubernetes (AKS in Azure) but less mature on Service Fabric.</span></span> <span data-ttu-id="f5841-120">반면에 Windows 컨테이너는 더 (2017 년 5 월에에서 릴리스됨) 서비스 패브릭에서 완벽 하 고 덜 AKS에 완성도 높은입니다.</span><span class="sxs-lookup"><span data-stu-id="f5841-120">On the other hand, Windows Containers are more mature in Service Fabric (released in May 2017) and less mature in AKS.</span></span>

<span data-ttu-id="f5841-121">그러나 OS 완성에서 이러한 차이점은 나중에 페이드 여러 플랫폼 됩니다 비교 가능한 OS 완성 및 결정은 응용 프로그램 해야 할 수 또는 각 플랫폼의 에코 시스템에 따라 특정 기능을 기반으로 기본 설정에 더 많은 배치 이유입니다.</span><span class="sxs-lookup"><span data-stu-id="f5841-121">However, those differences in OS maturity will fade in the future and multiple platforms will have comparable OS maturity and the decision will lay more on preferences based on specific features your application might need or based on each platform's ecosystem reasons.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="f5841-122">[이전](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
[다음](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)</span><span class="sxs-lookup"><span data-stu-id="f5841-122">[Previous](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
[Next](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)</span></span>
