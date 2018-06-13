---
title: Azure 컨테이너 인스턴스 (ACI)에 Windows 컨테이너를 배포 하는 경우
description: Azure 클라우드 및 Windows 컨테이너와 기존.NET 응용 프로그램을 최신식 | Azure 컨테이너 인스턴스 (ACI)에 Windows 컨테이너를 배포 하는 경우
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/29/2018
ms.openlocfilehash: 3dc23c96543d9611763b571105f52b150dfec06f
ms.sourcegitcommit: 88f251b08bf0718ce119f3d7302f514b74895038
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/10/2018
ms.locfileid: "33957953"
---
# <a name="when-to-deploy-windows-containers-to-azure-container-instances-aci"></a><span data-ttu-id="be364-103">Azure 컨테이너 인스턴스 (ACI)에 Windows 컨테이너를 배포 하는 경우</span><span class="sxs-lookup"><span data-stu-id="be364-103">When to deploy Windows Containers to Azure Container Instances (ACI)</span></span>

<span data-ttu-id="be364-104">방금 배포 및 업그레이드/패치 해도 내부에 있는 운영 체제 또는 투명 하는 모든 Vm 하지 않아도 azure 컨테이너 인스턴스와 주 가치 제안을 컨테이너에 즉시 배포할 수 있습니다 및 해당 환경을 유지 관리할 필요가 없습니다. 즉시 사용할 환경으로 다시 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="be364-104">Azure Container Instances main value proposition is that you can right away deploy containers to it and you don’t need to maintain that environment, you don’t need to upgrade/patch the underlaying operating system or VMs, all that is transparent and you just deploy containers into a ready-to-use environment.</span></span>

<span data-ttu-id="be364-105">이유 및 ACI를 사용 하도록 하려는 경우 시나리오 주 시나리오와 유사 기본적으로 컨테이너를 Azure Vm을 사용 하는 경우, Azure 컨테이너 인스턴스를 사용 하 여에 대 한 주요 시나리오는:</span><span class="sxs-lookup"><span data-stu-id="be364-105">The reasons and scenarios when you would want to use ACI are similar to the main scenarios when you use Azure VMs with containers, so basically, the main scenarios for using Azure Container Instances are:</span></span>

-   <span data-ttu-id="be364-106">**개발/테스트 시나리오**</span><span class="sxs-lookup"><span data-stu-id="be364-106">**Dev/Test scenarios**</span></span>
-   <span data-ttu-id="be364-107">**작업 자동화**</span><span class="sxs-lookup"><span data-stu-id="be364-107">**Task automation**</span></span>
-   <span data-ttu-id="be364-108">**CI/CD 에이전트**</span><span class="sxs-lookup"><span data-stu-id="be364-108">**CI/CD agents**</span></span>
-   <span data-ttu-id="be364-109">**작은/소수 자릿수가 일괄 처리**</span><span class="sxs-lookup"><span data-stu-id="be364-109">**Small/scale batch processing**</span></span>
-   <span data-ttu-id="be364-110">**단순한 웹 앱**</span><span class="sxs-lookup"><span data-stu-id="be364-110">**Simple web apps**</span></span>

<span data-ttu-id="be364-111">간단한 웹 응용 프로그램 시나리오 ACI에 대 한 상당한 시나리오 이지만 ACI에서 컨테이너 이미지 당 단일 컨테이너 인스턴스를 하나만 지정할 수 있습니다, 때문 고가용성 않아도 해 서만 제한적으로 조정할 수를 고려 합니다.</span><span class="sxs-lookup"><span data-stu-id="be364-111">The simple web apps scenario is a fair scenario for ACI but take into account that since in ACI you can only have a single container instance per container image, you won’t have high availability and only have limited scalability.</span></span>

<span data-ttu-id="be364-112">그러나 ACI 방금 단일 컨테이너 인스턴스를 제공 하기 때문에 인프라 것으로 간주 됩니다, 경우에 Windows Server와 함께 일반 Azure Vm에 비해 큰 이점이.</span><span class="sxs-lookup"><span data-stu-id="be364-112">However, even when ACI is considered infrastructure because it just provides single container instances, there is a huge benefit compared to regular Azure VMs with Windows Server.</span></span> <span data-ttu-id="be364-113">ACI, 셀프 유지 관리 되는 환경에는 컨테이너를 방금 배포와 해당 컨테이너에 대 한 비용 지불 됩니다.</span><span class="sxs-lookup"><span data-stu-id="be364-113">With ACI, you just deploy the containers into a self-maintained environment and you just pay for those containers.</span></span> <span data-ttu-id="be364-114">위치를 사용 하 고 Vm 컨테이너와 대부분의 시나리오는 훨씬 더 나은 플랫폼 이므로 유지 관리/업데이트/패치 Vm 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="be364-114">You don’t need to maintain/update/patch VMs, so it is a much better platform for most scenarios where you might be using VMs with containers.</span></span> <span data-ttu-id="be364-115">ACI를 사용 하 여 매우 간단 하 고, 방금는 컨테이너를 배포 하 고, 컨테이너를 방금 배포 VM 환경을 만들 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="be364-115">Using ACI is straight forward, you just deploy a container, there’s no need to create a VM environment you just deploy containers.</span></span>

<span data-ttu-id="be364-116">Azure 컨테이너 인스턴스 (ACI)의 주요 이점은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="be364-116">The main benefits of Azure Container Instances (ACI) are:</span></span>

-   <span data-ttu-id="be364-117">서버를 관리 하지 않고 컨테이너를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="be364-117">Run containers without managing servers</span></span>
-   <span data-ttu-id="be364-118">필요에 따라 컨테이너와 유연성 증가</span><span class="sxs-lookup"><span data-stu-id="be364-118">Increase agility with containers on demand</span></span>
-   <span data-ttu-id="be364-119">클라우드 최고의 간단 하 고 속도로 컨테이너를 배포-단일 명령으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="be364-119">Deploy containers to the cloud with unprecedented simplicity and speed—with a single command.</span></span> 
-   <span data-ttu-id="be364-120">하이퍼바이저 격리 된 응용 프로그램 보안</span><span class="sxs-lookup"><span data-stu-id="be364-120">Secure applications with hypervisor isolation</span></span>

<span data-ttu-id="be364-121">즉, ACI와 가상 컴퓨터를 관리 하거나를 새로운 도구를 배울 필요 하지 않고 빠른 응용 프로그램을 개발할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be364-121">In short, with ACI you can develop apps fast without managing virtual machines or having to learn new tools.</span></span> <span data-ttu-id="be364-122">바로 응용 프로그램은 클라우드에서 실행 되는 컨테이너의 경우</span><span class="sxs-lookup"><span data-stu-id="be364-122">It's just your application, in a container, running in the cloud.</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="be364-123">[이전](when-to-deploy-windows-containers-to-azure-vms-iaas-cloud.md)
[다음](when-to-deploy-windows-containers-to-service-fabric.md)</span><span class="sxs-lookup"><span data-stu-id="be364-123">[Previous](when-to-deploy-windows-containers-to-azure-vms-iaas-cloud.md)
[Next](when-to-deploy-windows-containers-to-service-fabric.md)</span></span>
