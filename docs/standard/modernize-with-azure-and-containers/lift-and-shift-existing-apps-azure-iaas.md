---
title: "기존 응용 프로그램이 Azure IaaS 이동할"
description: "기존.NET 응용 프로그램을 Azure 클라우드 및 Windows 컨테이너를 현대화 합니다."
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/26/2017
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: eed17ad06c138c3a4eb85f5e023427b681488784
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/23/2017
---
# <a name="lift-and-shift-existing-apps-azure-iaas"></a><span data-ttu-id="90e2a-103">기존 응용 프로그램이 Azure IaaS 이동할</span><span class="sxs-lookup"><span data-stu-id="90e2a-103">Lift and shift existing apps Azure IaaS</span></span>

> <span data-ttu-id="90e2a-104">비전:으로 하드웨어의 온-프레미스 투자와 총 비용을 줄이고 유지 관리, 네트워킹 단순히를 다시 호스트 하는 클라우드에서 기존 응용 프로그램의 첫 번째 단계입니다.</span><span class="sxs-lookup"><span data-stu-id="90e2a-104">Vision: As a first step, to reduce your on-premises investment and total cost of hardware and networking maintenance, simply rehost your existing applications in the cloud.</span></span>

<span data-ttu-id="90e2a-105">들어가기 전에 *어떻게* 서비스 (IaaS) 플랫폼으로 Azure 인프라를 기존 응용 프로그램을 마이그레이션하려면 중요 한 이유를 분석 하는 *이유* IaaS에 직접 마이그레이션할 원하는 azure입니다.</span><span class="sxs-lookup"><span data-stu-id="90e2a-105">Before getting into *how* to migrate your existing applications to the Azure infrastructure as a service (IaaS) platform, it's important to analyze the reasons *why* you'd want to migrate directly to IaaS in Azure.</span></span> <span data-ttu-id="90e2a-106">기본적으로이 현대화 완성도 수준 시나리오, 현재 온-프레미스 인프라를 사용 하 여 계속 진행 하지 않고 클라우드 Vm을 사용 하 여 시작 것입니다.</span><span class="sxs-lookup"><span data-stu-id="90e2a-106">The scenario at this modernization maturity level essentially is to start using VMs in the cloud, instead of continuing to use your current, on-premises infrastructure.</span></span>

<span data-ttu-id="90e2a-107">다른 분석 점은 *이유* 방금 더 많은 고급 Azure에서 관리 되는 서비스를 추가 하는 대신 순수 IaaS 클라우드로 마이그레이션하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="90e2a-107">Another point to analyze is *why* you might want to migrate to pure IaaS cloud instead of just adding more advanced managed services in Azure.</span></span> <span data-ttu-id="90e2a-108">경우의 수를 결정 해야 IaaS를 처음에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="90e2a-108">You need to determine what cases might require IaaS in the first place.</span></span>

<span data-ttu-id="90e2a-109">그림 2-1 현대화 완성도 수준의 클라우드 인프라를 갖춘 응용 프로그램을 배치 합니다.</span><span class="sxs-lookup"><span data-stu-id="90e2a-109">Figure 2-1 positions Cloud Infrastructure-Ready applications in the modernization maturity levels:</span></span>

![클라우드 인프라를 갖춘 응용 프로그램을 위치 지정](./media/image2-1.png)

> <span data-ttu-id="90e2a-111">**그림 2-1입니다.**</span><span class="sxs-lookup"><span data-stu-id="90e2a-111">**Figure 2-1.**</span></span> <span data-ttu-id="90e2a-112">클라우드 인프라를 갖춘 응용 프로그램을 위치 지정</span><span class="sxs-lookup"><span data-stu-id="90e2a-112">Positioning Cloud Infrastructure-Ready applications</span></span>

## <a name="why-migrate-existing-net-web-applications-to-azure-iaas"></a><span data-ttu-id="90e2a-113">기존.NET 웹 응용 프로그램에서는 Azure IaaS 마이그레이션하는 이유</span><span class="sxs-lookup"><span data-stu-id="90e2a-113">Why migrate existing .NET web applications to Azure IaaS</span></span> 

<span data-ttu-id="90e2a-114">비용 절감을 달성 하기 위해 초기 IaaS 수준에서도 클라우드로 마이그레이션하는 주요 이유는 합니다.</span><span class="sxs-lookup"><span data-stu-id="90e2a-114">The main reason to migrate to the cloud, even at an initial IaaS level, is to achieve cost reductions.</span></span> <span data-ttu-id="90e2a-115">더 많은 관리 되는 인프라 서비스를 사용 하 여 조직의 하드웨어 유지 관리, 서버 또는 VM 프로 비전 및 배포 및 관리 인프라에 투자를 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="90e2a-115">By using more managed infrastructure services, your organization can lower its investment in hardware maintenance, server or VM provisioning and deployment, and infrastructure management.</span></span>

<span data-ttu-id="90e2a-116">앱에서 클라우드로 이동 하도록 결정을 내린 후 선택 하는 이유에 IaaS PaaS는 단순히는 같은 더 많은 고급 옵션 대신 IaaS 환경의 주요 이유는 더 익숙할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="90e2a-116">After you make the decision to move your apps to the cloud, the main reason why you might choose IaaS instead of more advanced options like PaaS is simply that the IaaS environment will be more familiar.</span></span> <span data-ttu-id="90e2a-117">온-프레미스 환경에서는 현재와 비슷한 환경으로 이동, 가장 빠른 경로 클라우드를 만들어 더 낮은 학습 곡선을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="90e2a-117">Moving to an environment that's similar to your current, on-premises environment offers a lower learning curve, which makes it the quickest path to the cloud.</span></span>

<span data-ttu-id="90e2a-118">그러나 클라우드로 가장 빠른 경로 라인 것은 아닙니다는 클라우드에서 실행 중인 응용 프로그램에서 가장 효과적 권한을 얻게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="90e2a-118">However, taking the quickest path to the cloud doesn't mean that you will gain the most benefit from having your applications running in the cloud.</span></span> <span data-ttu-id="90e2a-119">어떤 조직에서 이미 도입 된 클라우드 DevOps 지원 및 PaaS (클라우드 최적화) 완성도 수준에서 클라우드 마이그레이션 가장 큰 이점을 얻게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="90e2a-119">Any organization will gain the most significant benefits from a cloud migration at the already introduced Cloud DevOps-Ready and PaaS (Cloud-Optimized) maturity levels.</span></span>

<span data-ttu-id="90e2a-120">또한 되었기 때문에 응용 프로그램을 더 쉽게 최신식 다시 이미에 IaaS 클라우드에서 실행 될 때 나중에 설계 하 분명 하 게 합니다.</span><span class="sxs-lookup"><span data-stu-id="90e2a-120">It also has become evident that applications are easier to modernize and re-architect in the future when they are already running in the cloud, even on IaaS.</span></span> <span data-ttu-id="90e2a-121">부분적 때문에 응용 프로그램 데이터 마이그레이션을 이미 달성 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="90e2a-121">This is true in part because application data migration has already been achieved.</span></span> <span data-ttu-id="90e2a-122">또한 조직 됩니다가 클라우드에서 작업에 필요한 기술 얻은 하려고 하 교대조에서 "클라우드 문화권"입니다.</span><span class="sxs-lookup"><span data-stu-id="90e2a-122">Also, your organization will have gained skills required for working in the cloud, and made the shift to operating in a "cloud culture."</span></span>

## <a name="when-to-migrate-to-iaas-instead-of-to-paas"></a><span data-ttu-id="90e2a-123">PaaS로 대신 IaaS를 마이그레이션 시기</span><span class="sxs-lookup"><span data-stu-id="90e2a-123">When to migrate to IaaS instead of to PaaS</span></span>

<span data-ttu-id="90e2a-124">다음 섹션에서는에서는 주로 PaaS 플랫폼 및 서비스에 기반 하는 클라우드 DevOps 지원 응용 프로그램에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="90e2a-124">In the next sections, we discuss Cloud DevOps-Ready applications that are mostly based on PaaS platforms and services.</span></span> <span data-ttu-id="90e2a-125">이러한 응용 프로그램을 클라우드로 마이그레이션하면 대부분 이점을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="90e2a-125">These apps give you the most benefits from migrating to the cloud.</span></span>

<span data-ttu-id="90e2a-126">목표는 클라우드에서 기존 응용 프로그램을 이동 하는 단순히, 하는 경우 먼저, Azure 앱 서비스에서 실행 되도록를 대폭 수정 해야 하는 기존 응용 프로그램을 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="90e2a-126">If your goal is simply to move existing applications to the cloud, first, identify existing applications that will require substantial modification to run in Azure App Service.</span></span> <span data-ttu-id="90e2a-127">이러한 앱에는 첫 번째 후보 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="90e2a-127">These apps should be the first candidates.</span></span>

<span data-ttu-id="90e2a-128">그런 다음 원하지 않거나 Windows 컨테이너 및 또는 Azure 서비스 패브릭 또는 Kubernetes 같은 orchestrators로 이동할 수 없습니다, 아직 다음 있으면 일반 Vm (IaaS)를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="90e2a-128">Then, if you don't want or still cannot move to Windows Containers and or orchestrators like Azure Service Fabric or Kubernetes, yet, then is when you would use plain VMs (IaaS).</span></span>

<span data-ttu-id="90e2a-129">하지만 올바르게 구성, 안전 하 게 유지 하 고, Vm을 유지 해야 한다는 훨씬 더 많은 시간 및 Azure에서 PaaS 서비스를 사용 하는 IT 전문 염두에서에 둬야 합니다.</span><span class="sxs-lookup"><span data-stu-id="90e2a-129">But, keep in mind that correctly configuring, securing, and maintaining VMs requires much more time and IT expertise compared to using PaaS services in Azure.</span></span> <span data-ttu-id="90e2a-130">Azure 가상 컴퓨터를 고려 하는 경우 수행 하는 계정으로 패치, 업데이트 및 VM 환경을 관리 하는 데 필요한 지속적인 유지 관리 작업이 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="90e2a-130">If you are considering Azure Virtual Machines, make sure that you take into account the ongoing maintenance effort required to patch, update, and manage your VM environment.</span></span> <span data-ttu-id="90e2a-131">Azure 가상 컴퓨터 IaaS를입니다.</span><span class="sxs-lookup"><span data-stu-id="90e2a-131">Azure Virtual Machines is IaaS.</span></span>

## <a name="use-azure-migrate-to-analyze-and-migrate-your-existing-applications-to-azure"></a><span data-ttu-id="90e2a-132">Azure 마이그레이션을 사용 하 여 분석 하 고 기존 응용 프로그램을 Azure 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="90e2a-132">Use Azure Migrate to analyze and migrate your existing applications to Azure</span></span>

<span data-ttu-id="90e2a-133">클라우드로 마이그레이션의 필요가 어려울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="90e2a-133">Migrating to the cloud doesn't have to be difficult.</span></span> <span data-ttu-id="90e2a-134">하지만 대부분의 조직에는 환경 및 응용 프로그램, 작업, 및 데이터 간의 긴밀 하 게 상호 종속 관계에 대 한 심층 파악-시작 하는 데 어려움 합니다.</span><span class="sxs-lookup"><span data-stu-id="90e2a-134">But many organizations struggle to get started - to get deep visibility into the environment and the tight interdependencies between applications, workloads, and data.</span></span> <span data-ttu-id="90e2a-135">해당 표시 하지 않고 앞으로 경로 계획 하기 어려울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="90e2a-135">Without that visibility, it can be difficult to plan the path forward.</span></span> <span data-ttu-id="90e2a-136">성공적인 마이그레이션에는 데 필요한 작업에 세부 정보 없이 조직 내에서 오른쪽의 대화를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="90e2a-136">Without detailed information on what's required for a successful migration, you can't have the right conversations within your organization.</span></span> <span data-ttu-id="90e2a-137">비용 이점에 대해 충분히 알 수 없는 또는 여부 작업 방금 리프트 및-시프트 하거나 수를 성공적으로 마이그레이션하려면 상당한 재작업 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="90e2a-137">You don't know enough about the potential cost benefits, or whether workloads could just lift-and-shift or would require significant rework to migrate successfully.</span></span> <span data-ttu-id="90e2a-138">대부분의 조직에서는 원하는 대로 당연 합니다.</span><span class="sxs-lookup"><span data-stu-id="90e2a-138">No wonder many organizations hesitate.</span></span>

<span data-ttu-id="90e2a-139">[Azure 마이그레이션](https://aka.ms/azuremigrate) 지침, 통찰력, 및 Azure로 마이그레이션에 도움을 주는 데 필요한 메커니즘을 제공 하는 새로운 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="90e2a-139">[Azure Migrate](https://aka.ms/azuremigrate) is a new service that provides the guidance, insights, and mechanisms needed to assist you in migrating to Azure.</span></span> <span data-ttu-id="90e2a-140">Azure 마이그레이션 작업을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="90e2a-140">Azure Migrate provides:</span></span>

-   <span data-ttu-id="90e2a-141">검색 및 온-프레미스 가상 컴퓨터에 대 한 평가</span><span class="sxs-lookup"><span data-stu-id="90e2a-141">Discovery and assessment for on-premises virtual machines</span></span>

-   <span data-ttu-id="90e2a-142">다중 계층 응용 프로그램의 높은 정확도 검색에 기본 제공 된 종속성 매핑</span><span class="sxs-lookup"><span data-stu-id="90e2a-142">Inbuilt dependency mapping for high-confidence discovery of multi-tier applications</span></span>

-   <span data-ttu-id="90e2a-143">Azure 가상 컴퓨터에 지능형 적정</span><span class="sxs-lookup"><span data-stu-id="90e2a-143">Intelligent rightsizing to Azure virtual machines</span></span>

-   <span data-ttu-id="90e2a-144">보고를 사용 하며 잠재적인 문제에 대 한 지침이 호환성</span><span class="sxs-lookup"><span data-stu-id="90e2a-144">Compatibility reporting with guidelines for remediating potential issues</span></span>

-   <span data-ttu-id="90e2a-145">데이터베이스 검색 및 마이그레이션에 대 한 Azure 데이터베이스 관리 서비스와 통합</span><span class="sxs-lookup"><span data-stu-id="90e2a-145">Integration with Azure Database Management Service for database discovery and migration</span></span>

<span data-ttu-id="90e2a-146">Azure 마이그레이션 작업 마이그레이션할 비즈니스에 미치는 영향을 최소화 하면서 Azure에서 예상 대로 실행할 수 있는 확신을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="90e2a-146">Azure Migrate gives you confidence that your workloads can migrate with minimal impact to the business and run as expected in Azure.</span></span> <span data-ttu-id="90e2a-147">적절 한 도구와 지침 최대 해당 중요 한 성능 보장 하는 동안 투자 수익률을 얻을 수 있습니다 및 안정성 요구 사항을 충족 합니다.</span><span class="sxs-lookup"><span data-stu-id="90e2a-147">With the right tools and guidance, you can achieve maximum return on investment while assuring that critical performance and reliability needs are met.</span></span>

<span data-ttu-id="90e2a-148">그림 2-2 Azure 마이그레이션에서 수행 하는 모든 서버 및 응용 프로그램 연결에 대 한 기본 제공 종속성 매핑을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="90e2a-148">Figure 2-2 shows you the built-in dependency mapping for all server and application connections performed by Azure Migrate.</span></span>

![클라우드 인프라를 갖춘 응용 프로그램을 위치 지정](./media/image2-2.png)

> <span data-ttu-id="90e2a-150">**그림 2-2입니다.**</span><span class="sxs-lookup"><span data-stu-id="90e2a-150">**Figure 2-2.**</span></span> <span data-ttu-id="90e2a-151">클라우드 인프라를 갖춘 응용 프로그램을 위치 지정</span><span class="sxs-lookup"><span data-stu-id="90e2a-151">Positioning Cloud Infrastructure-Ready applications</span></span>

## <a name="use-azure-site-recovery-to-migrate-your-existing-vms-to-azure-vms"></a><span data-ttu-id="90e2a-152">Azure Site Recovery를 사용 하 여 기존 Vm을 Azure Vm에 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="90e2a-152">Use Azure Site Recovery to migrate your existing VMs to Azure VMs</span></span>

<span data-ttu-id="90e2a-153">끝에 끝의 일환으로 [Azure 마이그레이션](https://aka.ms/azuremigrate), [Azure Site Recovery](https://docs.microsoft.com/azure/site-recovery/site-recovery-overview) Azure의 Vm에 웹 앱을 쉽게 마이그레이션할 수는 데 사용할 수 있는 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="90e2a-153">As part of the end-to-end [Azure Migrate](https://aka.ms/azuremigrate), [Azure Site Recovery](https://docs.microsoft.com/azure/site-recovery/site-recovery-overview) is a tool that you can use to easily migrate your web apps to VMs in Azure.</span></span> <span data-ttu-id="90e2a-154">보조 온-프레미스 위치에 복제 또는 온-프레미스 Vm 및 물리적 서버를 Azure에 복제 사이트 복구를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="90e2a-154">You can use Site Recovery to replicate on-premises VMs and physical servers to Azure, or to replicate them to a secondary on-premises location.</span></span> <span data-ttu-id="90e2a-155">온-프레미스에서 지원 되는 Azure VM에서 실행 되는 작업에도 복제할 수 있습니다 *Hyper-v* VM의는 *VMware* VM을 Windows 또는 Linux 물리적 서버입니다.</span><span class="sxs-lookup"><span data-stu-id="90e2a-155">You can even replicate a workload that's running on a supported Azure VM, on an on-premises *Hyper-V* VM, on a *VMware* VM, or on a Windows or Linux physical server.</span></span> <span data-ttu-id="90e2a-156">Azure로의 복제를 보조 데이터 센터를 유지 관리 하 고 비용을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="90e2a-156">Replication to Azure eliminates the cost and complexity of maintaining a secondary datacenter.</span></span>

<span data-ttu-id="90e2a-157">사이트 복구에도 부분적으로 하이브리드 환경에 맞게 이루어집니다 온-프레미스와 Azure에 의해서도 영향을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="90e2a-157">Site Recovery is also made specifically for hybrid environments that are partly on-premises and partly on Azure.</span></span> <span data-ttu-id="90e2a-158">사이트 복구 Vm에서 실행 되는 앱을 유지 하 여 비즈니스 연속성을 보장 하는 데 도움이 됩니다 및 온-프레미스 물리적 서버를 사용할 수 있는 사이트 작동이 중지 된 경우.</span><span class="sxs-lookup"><span data-stu-id="90e2a-158">Site Recovery helps ensure business continuity by keeping your apps that are running on VMs and on-premises physical servers available if a site goes down.</span></span> <span data-ttu-id="90e2a-159">복제를 지속적으로 사용할 수 있는 보조 위치에서 기본 사이트를 사용할 수 없는 경우 Vm 및 물리적 서버에서 실행 되는 작업.</span><span class="sxs-lookup"><span data-stu-id="90e2a-159">It replicates workloads that are running on VMs and physical servers so that they remain available in a secondary location if the primary site isn't available.</span></span> <span data-ttu-id="90e2a-160">작업을 다시 실행 하 고 위쪽 인 경우 기본 사이트를 복구 합니다.</span><span class="sxs-lookup"><span data-stu-id="90e2a-160">It recovers workloads to the primary site when it's up and running again.</span></span>

<span data-ttu-id="90e2a-161">그림 2-3 Azure Site Recovery를 사용 하 여 여러 VM 마이그레이션의 실행을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="90e2a-161">Figure 2-3 shows the execution of multiple VM migrations by using Azure Site Recovery.</span></span>

![클라우드 인프라를 갖춘 응용 프로그램을 위치 지정](./media/image2-3.png)

> <span data-ttu-id="90e2a-163">**그림 2-3입니다.**</span><span class="sxs-lookup"><span data-stu-id="90e2a-163">**Figure 2-3.**</span></span> <span data-ttu-id="90e2a-164">클라우드 인프라를 갖춘 응용 프로그램을 위치 지정</span><span class="sxs-lookup"><span data-stu-id="90e2a-164">Positioning Cloud Infrastructure-Ready applications</span></span>

### <a name="additional-resources"></a><span data-ttu-id="90e2a-165">추가 리소스</span><span class="sxs-lookup"><span data-stu-id="90e2a-165">Additional resources</span></span>

-   <span data-ttu-id="90e2a-166">**Azure 마이그레이션 데이터 시트**</span><span class="sxs-lookup"><span data-stu-id="90e2a-166">**Azure Migrate Datasheet**</span></span>

    [<span data-ttu-id="90e2a-167">https://aka.ms/azuremigration\_datasheet</span><span class="sxs-lookup"><span data-stu-id="90e2a-167">https://aka.ms/azuremigration\_datasheet</span></span>](https://aka.ms/azuremigration\_datasheet)

-   <span data-ttu-id="90e2a-168">**Azure Migrate**</span><span class="sxs-lookup"><span data-stu-id="90e2a-168">**Azure Migrate**</span></span>

    [<span data-ttu-id="90e2a-169">http://azuremigrationcenter.com/</span><span class="sxs-lookup"><span data-stu-id="90e2a-169">http://azuremigrationcenter.com/</span></span>](http://azuremigrationcenter.com/)

-   <span data-ttu-id="90e2a-170">**사이트 복구를 사용 하 여 Azure로 마이그레이션**</span><span class="sxs-lookup"><span data-stu-id="90e2a-170">**Migrate to Azure with Site Recovery**</span></span>

    [<span data-ttu-id="90e2a-171">https://docs.microsoft.com/azure/site-recovery/site-recovery-migrate-to-azure</span><span class="sxs-lookup"><span data-stu-id="90e2a-171">https://docs.microsoft.com/azure/site-recovery/site-recovery-migrate-to-azure</span></span>](https://docs.microsoft.com/azure/site-recovery/site-recovery-migrate-to-azure)

-   <span data-ttu-id="90e2a-172">**Azure Site Recovery 서비스 개요**</span><span class="sxs-lookup"><span data-stu-id="90e2a-172">**Azure Site Recovery service overview**</span></span>

    [<span data-ttu-id="90e2a-173">https://docs.microsoft.com/azure/site-recovery/site-recovery-overview</span><span class="sxs-lookup"><span data-stu-id="90e2a-173">https://docs.microsoft.com/azure/site-recovery/site-recovery-overview</span></span>](https://docs.microsoft.com/azure/site-recovery/site-recovery-overview)

-   <span data-ttu-id="90e2a-174">**Azure Vm에는 AWS의 마이그레이션 Vm**</span><span class="sxs-lookup"><span data-stu-id="90e2a-174">**Migrating VMs in AWS to Azure VMs**</span></span>

    [<span data-ttu-id="90e2a-175">https://docs.microsoft.com/azure/site-recovery/site-recovery-migrate-aws-to-azure</span><span class="sxs-lookup"><span data-stu-id="90e2a-175">https://docs.microsoft.com/azure/site-recovery/site-recovery-migrate-aws-to-azure</span></span>](https://docs.microsoft.com/azure/site-recovery/site-recovery-migrate-aws-to-azure)

>[!div class="step-by-step"]
<span data-ttu-id="90e2a-176">[이전](index.md)
[다음](migrate-your-relational-databases-to-azure.md)</span><span class="sxs-lookup"><span data-stu-id="90e2a-176">[Previous](index.md)
[Next](migrate-your-relational-databases-to-azure.md)</span></span>
