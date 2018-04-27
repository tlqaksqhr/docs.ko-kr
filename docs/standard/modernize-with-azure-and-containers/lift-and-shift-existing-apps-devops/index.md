---
title: 기존 앱 DevOps 리프트 앤 시프트
description: Azure 클라우드 및 Windows 컨테이너를 사용하여 기존 .NET 응용 프로그램 현대화
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/26/2017
ms.prod: .net
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 5229e6c9a63e5adf76c7a893a49a8a55633fa621
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2018
---
# <a name="lift-and-shift-existing-apps-devops"></a><span data-ttu-id="91bdf-103">기존 앱 DevOps 리프트 앤 시프트</span><span class="sxs-lookup"><span data-stu-id="91bdf-103">Lift and shift existing apps DevOps</span></span>

> <span data-ttu-id="91bdf-104">비전: 기존 .NET Framework 응용 프로그램을 클라우드 DevOps 지원 응용 프로그램에 리프트 앤 시프트하여 배포 민첩성을 대폭 개선함으로써 더 빠르게 배송하고 앱 배송 비용을 낮출 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91bdf-104">Vision: Lift and shift your existing .NET Framework applications to Cloud DevOps-Ready applications to drastically improve your deployment agility, so you can ship faster and lower app delivery costs.</span></span>

<span data-ttu-id="91bdf-105">컨테이너와 같은 새로운 기술과 클라우드의 이점을 활용하려면 기존.NET 응용 프로그램을 부분적으로나마 현대화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="91bdf-105">To take advantage of the benefits of the cloud and new technologies like containers, you should at least partially modernize your existing .NET applications.</span></span> <span data-ttu-id="91bdf-106">궁극적으로, 엔터프라이즈 응용 프로그램을 현대화하면 총 소유 비용이 감소합니다.</span><span class="sxs-lookup"><span data-stu-id="91bdf-106">Ultimately, modernizing your enterprise applications will lower your total cost of ownership.</span></span>

<span data-ttu-id="91bdf-107">응용 프로그램을 부분적으로 현대화하는 경우 전체 마이그레이션 및 재설계가 꼭 필요한 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="91bdf-107">Partially modernizing an app doesn't necessarily mean a full migration and re-architecture.</span></span> <span data-ttu-id="91bdf-108">쉽고 빠른 리프트 앤 시프트 프로세스를 사용하여 기존 응용 프로그램을 처음으로 현대화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91bdf-108">You can initially modernize your existing applications by using a lift and shift process that's easy and fast.</span></span> <span data-ttu-id="91bdf-109">모든 Windows 및 IIS 종속성을 사용하여 기존 .NET Framework 버전으로 작성된 현재 코드베이스를 유지 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91bdf-109">You can maintain your current code base, written in existing .NET Framework versions, with any Windows and IIS dependencies.</span></span> <span data-ttu-id="91bdf-110">그림 4-1에서는 Azure 응용 프로그램 현대화 완성 모델에서 클라우드 DevOps 지원 앱의 위치가 지정되는 방법을 중점적으로 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="91bdf-110">Figure 4-1 highlights how Cloud DevOps-Ready apps are positioned in Azure application modernization maturity models.</span></span>

![클라우드 DevOps 지원 응용 프로그램 위치 지정](./media/image1.png)

> <span data-ttu-id="91bdf-112">**그림 4-1.**</span><span class="sxs-lookup"><span data-stu-id="91bdf-112">**Figure 4-1.**</span></span> <span data-ttu-id="91bdf-113">클라우드 DevOps 지원 응용 프로그램 위치 지정</span><span class="sxs-lookup"><span data-stu-id="91bdf-113">Positioning Cloud DevOps-Ready applications</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="91bdf-114">[이전](../migrate-your-relational-databases-to-azure.md)
[다음](reasons-to-lift-and-shift-existing-net-apps-to-cloud-devops-ready-applications.md)</span><span class="sxs-lookup"><span data-stu-id="91bdf-114">[Previous](../migrate-your-relational-databases-to-azure.md)
[Next](reasons-to-lift-and-shift-existing-net-apps-to-cloud-devops-ready-applications.md)</span></span>
