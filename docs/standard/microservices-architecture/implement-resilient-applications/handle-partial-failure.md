---
title: "부분 오류 처리"
description: "컨테이너 화 된.NET 응용 프로그램에 대 한.NET Microservices 아키텍처 | 부분 오류 처리"
keywords: "Docker, 마이크로 서비스, ASP.NET, 컨테이너"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: b7d16acf3de2d395da70e8f46e59c129dec24f71
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="handling-partial-failure"></a><span data-ttu-id="58ae9-104">부분 오류 처리</span><span class="sxs-lookup"><span data-stu-id="58ae9-104">Handling partial failure</span></span>

<span data-ttu-id="58ae9-105">Microservices 기반 응용 프로그램과 같은 분산된 시스템에서 부분 실패는 끊임없이 위험이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58ae9-105">In distributed systems like microservices-based applications, there is an ever-present risk of partial failure.</span></span> <span data-ttu-id="58ae9-106">예를 들어, 단일 마이크로 서비스/컨테이너 실패할 수 있습니다 또는 짧은 시간에 대 한 응답을 사용할 수 없습니다 또는 단일 VM 또는 서버가 충돌할 수 있는 합니다.</span><span class="sxs-lookup"><span data-stu-id="58ae9-106">For instance, a single microservice/container can fail or might not be available to respond for a short time, or a single VM or server can crash.</span></span> <span data-ttu-id="58ae9-107">클라이언트와 서비스는 별도 프로세스, 이기 때문 서비스는 클라이언트의 요청에 시기 적절 하 게에서 응답 하도록 못할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58ae9-107">Since clients and services are separate processes, a service might not be able to respond in a timely way to a client’s request.</span></span> <span data-ttu-id="58ae9-108">서비스에 매우 느리게 응답 하 고 오버 로드 된 요청이 있을 수 있습니다 또는 단순히 액세스할 수 없는 짧은 시간에 대 한 네트워크 문제 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="58ae9-108">The service might be overloaded and responding extremely slowly to requests, or might simply not be accessible for a short time because of network issues.</span></span>

<span data-ttu-id="58ae9-109">예를 들어 주문 세부 정보 페이지는 eShopOnContainers에서 샘플 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="58ae9-109">For example, consider the Order details page from the eShopOnContainers sample application.</span></span> <span data-ttu-id="58ae9-110">정렬 마이크로 서비스 응답 하지 않으면 사용자가 클라이언트 프로세스 (MVC 웹 응용 프로그램)를 구현 하는 잘못 된 주문을 제출 하-예를 들어, 클라이언트 코드 된 시간 제한 없이 동기 Rpc를 사용 하는 경우-스레드를 무기한으로 차단 응답을 기다리는 중입니다.</span><span class="sxs-lookup"><span data-stu-id="58ae9-110">If the ordering microservice is unresponsive when the user tries to submit an order, a bad implementation of the client process (the MVC web application)—for example, if the client code were to use synchronous RPCs with no timeout—would block threads indefinitely waiting for a response.</span></span> <span data-ttu-id="58ae9-111">안 좋은 사용자 경험을 만드는 것 이외에 응답 하지 않는 모든 대기를 사용 하거나 한 스레드를 차단 및 스레드는 확장성이 높은 응용 프로그램에서 매우 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="58ae9-111">In addition to creating a bad user experience, every unresponsive wait consumes or blocks a thread, and threads are extremely valuable in highly scalable applications.</span></span> <span data-ttu-id="58ae9-112">많은 차단 된 스레드가 결국 응용 프로그램의 런타임 스레드 부족이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58ae9-112">If there are many blocked threads, eventually the application’s runtime can run out of threads.</span></span> <span data-ttu-id="58ae9-113">응용 프로그램 대신 전체적으로 응답 하지 않을 수 있습니다이 경우 그림 10-1에 표시 된 대로 방금 부분적으로 응답 합니다.</span><span class="sxs-lookup"><span data-stu-id="58ae9-113">In that case, the application can become globally unresponsive instead of just partially unresponsive, as show in Figure 10-1.</span></span>

![](./media/image1.png)

<span data-ttu-id="58ae9-114">**그림 10-1**합니다.</span><span class="sxs-lookup"><span data-stu-id="58ae9-114">**Figure 10-1**.</span></span> <span data-ttu-id="58ae9-115">스레드 서비스 가용성에 영향을 주는 종속성으로 인해 일부 실패</span><span class="sxs-lookup"><span data-stu-id="58ae9-115">Partial failures because of dependencies that impact service thread availability</span></span>

<span data-ttu-id="58ae9-116">큰 microservices 기반 응용 프로그램에서 모든 부분 오류 수 증폭, 대부분의 내부 microservices 상호 작용 (한 안티패턴 하다 고 간주)이 표시 되는 동기 HTTP 호출 기반 하는 경우에 특히 합니다.</span><span class="sxs-lookup"><span data-stu-id="58ae9-116">In a large microservices-based application, any partial failure can be amplified, especially if most of the internal microservices interaction is based on synchronous HTTP calls (which is considered an anti-pattern).</span></span> <span data-ttu-id="58ae9-117">수백만 번 하루 들어오는 호출을 수신 하는 시스템에 대해 생각 합니다.</span><span class="sxs-lookup"><span data-stu-id="58ae9-117">Think about a system that receives millions of incoming calls per day.</span></span> <span data-ttu-id="58ae9-118">시스템에는 동기 HTTP 호출의 긴 체인을 기반으로 하는 잘못 된 디자인을 이러한 들어오는 호출 동기 종속성으로 여러 개의 내부 microservices 자세한 수백만 (1: 4의 비율을 가정 하겠습니다) 보내는 호출에에서 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58ae9-118">If your system has a bad design that is based on long chains of synchronous HTTP calls, these incoming calls might result in many more millions of outgoing calls (let’s suppose a ratio of 1:4) to dozens of internal microservices as synchronous dependencies.</span></span> <span data-ttu-id="58ae9-119">이러한 상황에서 그림 10-2, 특히 종속성 나와 \#3입니다.</span><span class="sxs-lookup"><span data-stu-id="58ae9-119">This situation is shown in Figure 10-2, especially dependency \#3.</span></span>

![](./media/image2.png)

<span data-ttu-id="58ae9-120">**그림 10-2**합니다.</span><span class="sxs-lookup"><span data-stu-id="58ae9-120">**Figure 10-2**.</span></span> <span data-ttu-id="58ae9-121">긴 체인의 HTTP 요청에 대 한 잘못 된 디자인을 갖게 될 결과</span><span class="sxs-lookup"><span data-stu-id="58ae9-121">The impact of having an incorrect design featuring long chains of HTTP requests</span></span>

<span data-ttu-id="58ae9-122">일시적인 오류는 사실상 분산 보장 및 자체 모든 종속성에 우수한 가용성 하는 경우에 기반된 시스템을 클라우드입니다.</span><span class="sxs-lookup"><span data-stu-id="58ae9-122">Intermittent failure is virtually guaranteed in a distributed and cloud based system, even if every dependency itself has excellent availability.</span></span> <span data-ttu-id="58ae9-123">이 팩트 고려해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="58ae9-123">This should be a fact you need to consider.</span></span>

<span data-ttu-id="58ae9-124">디자인 하지 않으며 내결함성을 보장할 수 있는 기술을 구현 하는 경우에 작은 가동 중시 시간 증폭 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58ae9-124">If you do not design and implement techniques to ensure fault tolerance, even small downtimes can be amplified.</span></span> <span data-ttu-id="58ae9-125">예를 들어 99.99% 가용성의 50 종속성이 ripple 효과 인해 각 월의 가동 중지 시간이 몇 시간으로 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="58ae9-125">As an example, 50 dependencies each with 99.99% of availability would result in several hours of downtime each month because of this ripple effect.</span></span> <span data-ttu-id="58ae9-126">마이크로 서비스 종속성 대용량의 요청을 처리 하는 동안 오류가 발생 하면 해당 오류 각 서비스의 모든 사용 가능한 요청 스레드를 포화 시키고 전체 응용 프로그램 크래시 신속 하 게 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58ae9-126">When a microservice dependency fails while handling a high volume of requests, that failure can quickly saturate all available request threads in each service and crash the whole application.</span></span>

![](./media/image3.png)

<span data-ttu-id="58ae9-127">**그림 10-3**합니다.</span><span class="sxs-lookup"><span data-stu-id="58ae9-127">**Figure 10-3**.</span></span> <span data-ttu-id="58ae9-128">Microservices 긴 체인 동기 HTTP 호출을 사용 하 여 증폭 부분 실패</span><span class="sxs-lookup"><span data-stu-id="58ae9-128">Partial failure amplified by microservices with long chains of synchronous HTTP calls</span></span>

<span data-ttu-id="58ae9-129">섹션에서이 문제를 최소화 하기 위해 "*비동기 마이크로 서비스 통합 적용 마이크로 서비스의 자치 성을*" (장에서 아키텍처)에서는 권장 비동기 통신을 내부에서 사용할 수 있습니다 microservices 합니다.</span><span class="sxs-lookup"><span data-stu-id="58ae9-129">To minimize this problem, in the section "*Asynchronous microservice integration enforce microservice’s autonomy*” (in the architecture chapter), we encouraged you to use asynchronous communication across the internal microservices.</span></span> <span data-ttu-id="58ae9-130">간단 하 게 설명할 더 다음 섹션에서입니다.</span><span class="sxs-lookup"><span data-stu-id="58ae9-130">We briefly explain more in the next section.</span></span>

<span data-ttu-id="58ae9-131">또한 반드시 부분 장애를 처리 하도록 microservices 및 클라이언트 응용 프로그램을 디자인 하는-즉, 탄력적인 microservices 및 클라이언트 응용 프로그램을 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="58ae9-131">In addition, it is essential that you design your microservices and client applications to handle partial failures—that is, to build resilient microservices and client applications.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="58ae9-132">[이전] [다음] (부분 실패 strategies.md) (index.md)</span><span class="sxs-lookup"><span data-stu-id="58ae9-132">[Previous] (index.md) [Next] (partial-failure-strategies.md)</span></span>
