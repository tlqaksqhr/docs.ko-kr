---
title: "컨테이너 및 Docker 소개"
description: "컨테이너화된 .NET 응용 프로그램을 위한 .NET 마이크로 서비스 아키텍처 | 컨테이너 및 Docker 소개"
keywords: "Docker, 마이크로 서비스, ASP.NET, 컨테이너"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: bb9466129287b0f10ace3c6d1129fb94b7a443e2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="introduction-to-containers-and-docker"></a><span data-ttu-id="2fb11-104">컨테이너 및 Docker 소개</span><span class="sxs-lookup"><span data-stu-id="2fb11-104">Introduction to Containers and Docker</span></span>

<span data-ttu-id="2fb11-105">컨테이너화는 응용 프로그램 또는 서비스, 이에 해당하는 종속성 및 (배포 매니페스트 파일로 일반화된) 구성이 컨테이너 이미지로 패키지되는 소프트웨어 개발 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="2fb11-105">Containerization is an approach to software development in which an application or service, its dependencies, and its configuration (abstracted as deployment manifest files) are packaged together as a container image.</span></span> <span data-ttu-id="2fb11-106">컨테이너화된 응용 프로그램은 하나의 단위로 테스트하고 컨테이너 이미지 인스턴스로 호스트 OS(운영 체제)에 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2fb11-106">The containerized application can be tested as a unit and deployed as a container image instance to the host operating system (OS).</span></span>

<span data-ttu-id="2fb11-107">배송 컨테이너를 사용하여 컨테이너 안에 들어있는 화물에 상관없이 상품을 배, 기차 또는 트럭으로 운반하듯이 소프트웨어 컨테이너도 다양한 코드 및 종속성을 포함할 수 있는 소프트웨어의 표준 단위 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fb11-107">Just as shipping containers allow goods to be transported by ship, train, or truck regardless of the cargo inside, software containers act as a standard unit of software that can contain different code and dependencies.</span></span> <span data-ttu-id="2fb11-108">이러한 방식의 소프트웨어 컨테이너화를 통해 개발자와 IT 전문가는 수정 과정을 거의 거치지 않고 모든 환경에서 응용 프로그램을 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2fb11-108">Containerizing software this way enables developers and IT professionals to deploy them across environments with little or no modification.</span></span>

<span data-ttu-id="2fb11-109">또한 컨테이너는 공유 OS에서 응용 프로그램을 서로 격리합니다.</span><span class="sxs-lookup"><span data-stu-id="2fb11-109">Containers also isolate applications from each other on a shared OS.</span></span> <span data-ttu-id="2fb11-110">컨테이너화된 응용 프로그램은 OS(Linux 또는 Windows)에서 차례대로 실행되는 컨테이너 호스트의 맨 위에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="2fb11-110">Containerized applications run on top of a container host that in turn runs on the OS (Linux or Windows).</span></span> <span data-ttu-id="2fb11-111">따라서 컨테이너의 공간은 VM(가상 컴퓨터) 이미지보다 훨씬 작습니다.</span><span class="sxs-lookup"><span data-stu-id="2fb11-111">Containers therefore have a significantly smaller footprint than virtual machine (VM) images.</span></span>

<span data-ttu-id="2fb11-112">그림 2-1에 표시된 것처럼 각 컨테이너는 전체 웹 응용 프로그램 또는 서비스를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2fb11-112">Each container can run a whole web application or a service, as shown in Figure 2-1.</span></span> <span data-ttu-id="2fb11-113">이 예제에서는 Docker 호스트가 컨테이너 호스트이며 앱 1, 앱 2, Svc 1, Svc 2가 컨테이너화된 응용 프로그램 또는 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="2fb11-113">In this example, Docker host is a container host, and App1, App2, Svc 1, and Svc 2 are containerized applications or services.</span></span>

![](./media/image1.png)

<span data-ttu-id="2fb11-114">**그림 2-1**.</span><span class="sxs-lookup"><span data-stu-id="2fb11-114">**Figure 2-1**.</span></span> <span data-ttu-id="2fb11-115">컨테이너 호스트에서 실행되는 여러 컨테이너</span><span class="sxs-lookup"><span data-stu-id="2fb11-115">Multiple containers running on a container host</span></span>

<span data-ttu-id="2fb11-116">컨테이너화의 또 다른 이점은 확장성입니다.</span><span class="sxs-lookup"><span data-stu-id="2fb11-116">Another benefit of containerization is scalability.</span></span> <span data-ttu-id="2fb11-117">단기 작업에 대한 새 컨테이너를 만들어 신속하게 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2fb11-117">You can scale out quickly by creating new containers for short-term tasks.</span></span> <span data-ttu-id="2fb11-118">응용 프로그램의 관점에서 볼 때 이미지 인스턴스화(컨테이너 생성)는 서비스 또는 웹앱과 같은 프로세스 인스턴스화와 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="2fb11-118">From an application point of view, instantiating an image (creating a container) is similar to instantiating a process like a service or web app.</span></span> <span data-ttu-id="2fb11-119">그러나 안정성을 생각한다면, 동일한 이미지의 여러 인스턴스를 여러 호스트 서버에서 실행할 경우 일반적으로 기본 도메인이 다른 다양한 호스트 서버 또는 VM에서 각 컨테이너(이미지 인스턴스)를 실행하려 할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2fb11-119">For reliability, however, when you run multiple instances of the same image across multiple host servers, you typically want each container (image instance) to run in a different host server or VM in different fault domains.</span></span>

<span data-ttu-id="2fb11-120">즉, 컨테이너는 전체 응용 프로그램 수명 주기 워크플로에서 격리, 이식성, 민첩성, 확장성, 제어에 대한 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2fb11-120">In short, containers offer the benefits of isolation, portability, agility, scalability, and control across the whole application lifecycle workflow.</span></span> <span data-ttu-id="2fb11-121">가장 중요한 이점은 개발 및 작업 사이에서 격리를 제공한다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2fb11-121">The most important benefit is the isolation provided between Dev and Ops.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="2fb11-122">[이전] (../index.md) [다음] (docker-defined.md)</span><span class="sxs-lookup"><span data-stu-id="2fb11-122">[Previous] (../index.md) [Next] (docker-defined.md)</span></span>
