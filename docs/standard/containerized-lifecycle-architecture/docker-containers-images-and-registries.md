---
title: "Docker 컨테이너, 이미지 및 레지스트리"
description: "Microsoft 플랫폼 및 도구와 Docker 컨테이너 화 된 응용 프로그램 수명 주기"
keywords: "Docker, 마이크로 서비스, ASP.NET, 컨테이너"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: b115b25d8ae335aafbe41bac0d694170be7e3c49
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="docker-containers-images-and-registries"></a><span data-ttu-id="99b35-104">Docker 컨테이너, 이미지 및 레지스트리</span><span class="sxs-lookup"><span data-stu-id="99b35-104">Docker containers, images, and registries</span></span>

<span data-ttu-id="99b35-105">Docker를 사용 하는 경우는 응용 프로그램 또는 만들고 서비스 패키지 하 고 여기에 종속 컨테이너 이미지에 합니다.</span><span class="sxs-lookup"><span data-stu-id="99b35-105">When using Docker, you create an app or service and package it and its dependencies into a container image.</span></span> <span data-ttu-id="99b35-106">이미지는 응용 프로그램 또는 서비스와 해당 구성 및 종속성의 정적 표현 합니다.</span><span class="sxs-lookup"><span data-stu-id="99b35-106">An image is a static representation of the app or service and its configuration and dependencies.</span></span>

<span data-ttu-id="99b35-107">응용 프로그램 또는 서비스를 실행 하려면 응용 프로그램의 이미지가 Docker 호스트에서 실행 중인 컨테이너를 만들려면 인스턴스화됩니다.</span><span class="sxs-lookup"><span data-stu-id="99b35-107">To run the app or service, the app's image is instantiated to create a container, which will be running on the Docker host.</span></span> <span data-ttu-id="99b35-108">컨테이너는 개발 환경 또는 PC에서 처음 테스트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="99b35-108">Containers are initially tested in a development environment or PC.</span></span>

<span data-ttu-id="99b35-109">이미지의 라이브러리 역할을 레지스트리에 이미지를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="99b35-109">You store images in a registry, which acts as a library of images.</span></span> <span data-ttu-id="99b35-110">프로덕션 orchestrators에 배포할 때 레지스트리를 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="99b35-110">You need a registry when deploying to production orchestrators.</span></span> <span data-ttu-id="99b35-111">Docker가 관리를 통해 공개 레지스트리 [Docker 허브](https://hub.docker.com/); 다른 공급 업체 이미지의 다양 한 컬렉션에 대 한 레지스트리를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="99b35-111">Docker maintains a public registry via [Docker Hub](https://hub.docker.com/); other vendors provide registries for different collections of images.</span></span> <span data-ttu-id="99b35-112">기업에서는 사설 레지스트리를 가질 수 있습니다 또는 온-프레미스 자신의 Docker 이미지에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="99b35-112">Alternatively, enterprises can have a private registry on-premises for their own Docker images.</span></span>

<span data-ttu-id="99b35-113">그림 1-4 이미지와 레지스트리의 Docker에서 관계를 다른 구성 요소를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="99b35-113">Figure 1-4 shows how images and registries in Docker relate to other components.</span></span> <span data-ttu-id="99b35-114">또한 공급 업체의 여러 레지스트리 제공 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="99b35-114">It also shows the multiple registry offerings from vendors.</span></span>

![](./media/image4.png)

<span data-ttu-id="99b35-115">Docker 용어 및 개념의 그림 1-4: 분류</span><span class="sxs-lookup"><span data-stu-id="99b35-115">Figure 1-4: Taxonomy of Docker terms and concepts</span></span>

<span data-ttu-id="99b35-116">레지스트리 ()에 이미지를 배치 하 여 모든 프레임 워크 수준 종속성을 포함 하 여 정적 및 변경할 수 없는 응용 프로그램 비트를 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99b35-116">By putting images in a registry, you can store static and immutable application bits, including all of their dependencies, at a framework level.</span></span> <span data-ttu-id="99b35-117">하면 버전을 관리할 수 및 여러 환경에서 이미지를 배포 하 고 따라서 일관 된 배포 단위를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="99b35-117">You then can version and deploy images in multiple environments and thus provide a consistent deployment unit.</span></span>

<span data-ttu-id="99b35-118">개인 이미지 레지스트리, 온-프레미스 호스트 또는 클라우드에 다음과 같은 상황에서 권장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="99b35-118">Private image registries, either hosted on-premises or in the cloud, are recommended for the following situations:</span></span>

-   <span data-ttu-id="99b35-119">기밀성 인해 공개적으로 이미지를 공유 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="99b35-119">Your images must not be shared publicly due to confidentiality.</span></span>

-   <span data-ttu-id="99b35-120">사용자 이미지와 선택한 배포 환경 간의 최소 네트워크 대기 시간이 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="99b35-120">You want to have minimum network latency between your images and your chosen deployment environment.</span></span> <span data-ttu-id="99b35-121">예를 들어 프로덕션 환경의 Azure 이면를 싶을 네트워크 대기 시간이 최소화 됩니다 되도록 이미지를 Azure 컨테이너 레지스트리에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="99b35-121">For example, if your production environment is Azure, you probably want to store your images in Azure Container Registry so that network latency will be minimal.</span></span> <span data-ttu-id="99b35-122">유사한 방식 프로덕션 환경에는 온-프레미스에는 경우는 온-프레미스 Docker Trusted Registry 동일한 로컬 네트워크 내에서 사용할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="99b35-122">In a similar way, if your production environment is on-premises, you might want to have an on-premises Docker Trusted Registry available within the same local network.</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="99b35-123">[이전] (docker-terminology.md) [다음] (Docker-응용 프로그램-수명 주기/index.md)</span><span class="sxs-lookup"><span data-stu-id="99b35-123">[Previous] (docker-terminology.md) [Next] (Docker-application-lifecycle/index.md)</span></span>
