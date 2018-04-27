---
title: 온-프레미스에서 Windows 컨테이너를 배포 하는 경우 IaaS VM 인프라
description: 컨테이너 화 된.NET 응용 프로그램에 대 한.NET Microservices 아키텍처 | 온-프레미스에서 Windows 컨테이너를 배포 하는 경우 IaaS VM 인프라
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/26/2017
ms.prod: .net
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 1d3ad9cf3a17518ee4732b3799de2d3b103b81b7
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2018
---
# <a name="when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure"></a><span data-ttu-id="cdd7b-103">온-프레미스에서 Windows 컨테이너를 배포 하는 경우 IaaS VM 인프라</span><span class="sxs-lookup"><span data-stu-id="cdd7b-103">When to deploy Windows Containers in your on-premises IaaS VM infrastructure</span></span>

-   <span data-ttu-id="cdd7b-104">조직에서 클라우드로 전환할 준비가 되셨습니까 되지 않을 수 있습니다 있거나 것 단순히 수 없는 한 비즈니스 적 사유가 클라우드로 이동할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cdd7b-104">Your organization might not be ready to move to the cloud, or it might simply not be able to move to the cloud for a business reason.</span></span> <span data-ttu-id="cdd7b-105">그러나 사용자 고유의 데이터 센터에 Windows 컨테이너를 사용 하는 이점을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cdd7b-105">But, you can still get the benefits of using Windows Containers in your own datacenters.</span></span>

-   <span data-ttu-id="cdd7b-106">사용 하는 온-프레미스, 않으며는 있는 속도가 느려질 수 있습니다는 클라우드로 이동 하려고 하면 다른 아티팩트를 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cdd7b-106">You might have other artifacts that are being used on-premises, and which might slow you down when you try to move to the cloud.</span></span> <span data-ttu-id="cdd7b-107">예를 들어, 보안 또는 인증 종속성 온-프레미스 Windows Server Active Directory, 또는 다른 온-프레미스 자산입니다.</span><span class="sxs-lookup"><span data-stu-id="cdd7b-107">For example, security or authentication dependencies with on-premises Windows Server Active Directory, or any other on-premises asset.</span></span>

-   <span data-ttu-id="cdd7b-108">현재 Windows 컨테이너를 사용 하 여 시작 하는 경우 더 나은 위치에서 클라우드로 단계적된으로 마이그레이션하면 내일 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cdd7b-108">If you start using Windows Containers today, you can make a phased migration to the cloud tomorrow from a much better position.</span></span> <span data-ttu-id="cdd7b-109">Windows 컨테이너에 없는 잠금 기능으로 모든 클라우드에 대 한 배포 단위 해지고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cdd7b-109">Windows Containers is becoming a unit of deployment for any cloud, with no lock-in.</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="cdd7b-110">[이전](when-not-to-deploy-to-windows-containers.md)
[다음](when-to-deploy-windows-containers-to-azure-vms-iaas-cloud.md)</span><span class="sxs-lookup"><span data-stu-id="cdd7b-110">[Previous](when-not-to-deploy-to-windows-containers.md)
[Next](when-to-deploy-windows-containers-to-azure-vms-iaas-cloud.md)</span></span>
