---
title: Docker 컨테이너, 이미지 및 레지스트리
description: Microsoft 플랫폼 및 도구를 사용하여 컨테이너화된 Docker 응용 프로그램 수명 주기
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: ff5a1f3e4b09ac9f7ea600d3f127523b96fcce55
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/29/2018
ms.locfileid: "37106365"
---
# <a name="docker-containers-images-and-registries"></a><span data-ttu-id="1a002-103">Docker 컨테이너, 이미지 및 레지스트리</span><span class="sxs-lookup"><span data-stu-id="1a002-103">Docker containers, images, and registries</span></span>

<span data-ttu-id="1a002-104">Docker를 사용 하는 경우는 응용 프로그램 또는 만들고 서비스 패키지 하 고 여기에 종속 컨테이너 이미지에 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a002-104">When using Docker, you create an app or service and package it and its dependencies into a container image.</span></span> <span data-ttu-id="1a002-105">이미지는 앱 또는 서비스와 그 구성 및 종속성을 정적으로 표현합니다.</span><span class="sxs-lookup"><span data-stu-id="1a002-105">An image is a static representation of the app or service and its configuration and dependencies.</span></span>

<span data-ttu-id="1a002-106">응용 프로그램 또는 서비스를 실행 하려면 응용 프로그램의 이미지가 Docker 호스트에서 실행 중인 컨테이너를 만들려면 인스턴스화됩니다.</span><span class="sxs-lookup"><span data-stu-id="1a002-106">To run the app or service, the app's image is instantiated to create a container, which will be running on the Docker host.</span></span> <span data-ttu-id="1a002-107">컨테이너는 개발 환경 또는 PC에서 초기에 테스트됩니다.</span><span class="sxs-lookup"><span data-stu-id="1a002-107">Containers are initially tested in a development environment or PC.</span></span>

<span data-ttu-id="1a002-108">이미지의 라이브러리 역할을 레지스트리에 이미지를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a002-108">You store images in a registry, which acts as a library of images.</span></span> <span data-ttu-id="1a002-109">프로덕션 orchestrators에 배포할 때 레지스트리를 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a002-109">You need a registry when deploying to production orchestrators.</span></span> <span data-ttu-id="1a002-110">Docker는 [Docker 허브](https://hub.docker.com/)를 통해 공용 레지스트리를 관리합니다. 다른 공급업체는 다른 이미지 컬렉션을 위한 레지스트리를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1a002-110">Docker maintains a public registry via [Docker Hub](https://hub.docker.com/); other vendors provide registries for different collections of images.</span></span> <span data-ttu-id="1a002-111">또는 기업에서는 자체 Docker 이미지를 위해 개인 레지스트리 온-프레미스를 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a002-111">Alternatively, enterprises can have a private registry on-premises for their own Docker images.</span></span>

<span data-ttu-id="1a002-112">그림 1-4 이미지와 레지스트리의 Docker에서 관계를 다른 구성 요소를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1a002-112">Figure 1-4 shows how images and registries in Docker relate to other components.</span></span> <span data-ttu-id="1a002-113">그것은 또한 공급업체로부터 제공되는 여러 레지스트리를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="1a002-113">It also shows the multiple registry offerings from vendors.</span></span>

![](./media/image4.png)

<span data-ttu-id="1a002-114">Docker 용어 및 개념의 그림 1-4: 분류</span><span class="sxs-lookup"><span data-stu-id="1a002-114">Figure 1-4: Taxonomy of Docker terms and concepts</span></span>

<span data-ttu-id="1a002-115">레지스트리 ()에 이미지를 배치 하 여 모든 프레임 워크 수준 종속성을 포함 하 여 정적 및 변경할 수 없는 응용 프로그램 비트를 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a002-115">By putting images in a registry, you can store static and immutable application bits, including all of their dependencies, at a framework level.</span></span> <span data-ttu-id="1a002-116">하면 버전을 관리할 수 및 여러 환경에서 이미지를 배포 하 고 따라서 일관 된 배포 단위를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a002-116">You then can version and deploy images in multiple environments and thus provide a consistent deployment unit.</span></span>

<span data-ttu-id="1a002-117">개인 이미지 레지스트리, 온-프레미스 호스트 또는 클라우드에 다음과 같은 상황에서 권장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1a002-117">Private image registries, either hosted on-premises or in the cloud, are recommended for the following situations:</span></span>

-   <span data-ttu-id="1a002-118">기밀로 인해 이미지를 공개적으로 공유해서는 안됩니다.</span><span class="sxs-lookup"><span data-stu-id="1a002-118">Your images must not be shared publicly due to confidentiality.</span></span>

-   <span data-ttu-id="1a002-119">이미지와 선택한 배포 환경 사이에는 최소 네트워크 대기 시간이 요구됩니다.</span><span class="sxs-lookup"><span data-stu-id="1a002-119">You want to have minimum network latency between your images and your chosen deployment environment.</span></span> <span data-ttu-id="1a002-120">예를 들어 프로덕션 환경의 Azure 이면를 싶을 네트워크 대기 시간이 최소화 됩니다 되도록 이미지를 Azure 컨테이너 레지스트리에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a002-120">For example, if your production environment is Azure, you probably want to store your images in Azure Container Registry so that network latency will be minimal.</span></span> <span data-ttu-id="1a002-121">프로덕션 환경이 동일한 로컬 네트워크 내에서 사용 가능한 온-프레미스 Docker Trusted Registry인 경우에도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="1a002-121">In a similar way, if your production environment is on-premises, you might want to have an on-premises Docker Trusted Registry available within the same local network.</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="1a002-122">[이전](docker-terminology.md)
[다음](Docker-application-lifecycle/index.md)</span><span class="sxs-lookup"><span data-stu-id="1a002-122">[Previous](docker-terminology.md)
[Next](Docker-application-lifecycle/index.md)</span></span>
