---
title: 비동기 개요
description: 비동기 프로그래밍이 다중 코어에서 차단 I/O 및 동시 작업을 간단하게 처리할 수 있게 해주는 주요 기술이 되는 방법을 알아봅니다.
author: cartermp
ms.author: wiwagn
ms.date: 06/20/2016
ms.technology: dotnet-standard
ms.assetid: 1e38e9d9-8284-46ee-a15f-199adc4f26f4
ms.openlocfilehash: b9d612186e1051644e8d4ae9476b8fafd811deb0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="async-overview"></a><span data-ttu-id="1c3ec-103">비동기 개요</span><span class="sxs-lookup"><span data-stu-id="1c3ec-103">Async Overview</span></span>

<span data-ttu-id="1c3ec-104">얼마 전만 해도 최신 PC 또는 서버를 구입하기만 해도 앱 속도가 빨라졌지만 이러한 추세는 중단되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1c3ec-104">Not so long ago, apps got faster simply by buying a newer PC or server and then that trend stopped.</span></span> <span data-ttu-id="1c3ec-105">사실 반대가 되었다고 해야 맞습니다.</span><span class="sxs-lookup"><span data-stu-id="1c3ec-105">In fact, it reversed.</span></span> <span data-ttu-id="1c3ec-106">1ghz 싱글 코어 ARM 칩이 탑재되고 서버 작업이 VM으로 전환된 휴대폰이 출시되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1c3ec-106">Mobile phones appeared with 1ghz single core ARM chips and server workloads transitioned to VMs.</span></span> <span data-ttu-id="1c3ec-107">그래도 사용자는 여전히 응답성이 뛰어난 UI를 원하고 비즈니스 소유자는 비즈니스에 맞게 확장되는 서버를 원합니다.</span><span class="sxs-lookup"><span data-stu-id="1c3ec-107">Users still want responsive UI and business owners want servers that scale with their business.</span></span> <span data-ttu-id="1c3ec-108">모바일 및 클라우드로의 전환과 인터넷 연결 사용자 수가 30억 명을 넘어서면서 일련의 새로운 소프트웨어 패턴이 생겼습니다.</span><span class="sxs-lookup"><span data-stu-id="1c3ec-108">The transition to mobile and cloud and an internet-connected population of >3B users has resulted in a new set of software patterns.</span></span> 

* <span data-ttu-id="1c3ec-109">클라이언트 응용 프로그램은 항상 켜져 있고, 항상 연결되어 있으며, 지속적으로 사용자 조작(예: 터치)에 빠르게 응답해야 하고, 앱 스토어 등급이 높아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c3ec-109">Client applications are expected to be always-on, always-connected and constantly responsive to user interaction (for example, touch) with high app store ratings!</span></span>
* <span data-ttu-id="1c3ec-110">서비스는 적절하게 확장 및 축소하여 트래픽 급증을 처리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c3ec-110">Services are expected to handle spikes in traffic by gracefully scaling up and down.</span></span> 

<span data-ttu-id="1c3ec-111">비동기 프로그래밍은 다중 코어에서 차단 I/O 및 동시 작업을 간단하게 처리할 수 있게 해주는 주요 기술입니다.</span><span class="sxs-lookup"><span data-stu-id="1c3ec-111">Async programming is a key technique that makes it straightforward to handle blocking I/O and concurrent operations on multiple cores.</span></span> <span data-ttu-id="1c3ec-112">.NET에서는 앱과 서비스가 C#, VB 및 F#으로 작성된 사용하기 쉬운 언어 수준의 비동기 프로그래밍 모델을 사용하여 응답성 및 탄력성을 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c3ec-112">.NET provides the capability for apps and services to be responsive and elastic with easy-to-use, language-level asynchronous programming models in C#, VB, and F#.</span></span>

## <a name="why-write-async-code"></a><span data-ttu-id="1c3ec-113">비동기 코드를 작성하는 이유</span><span class="sxs-lookup"><span data-stu-id="1c3ec-113">Why Write Async Code?</span></span>

<span data-ttu-id="1c3ec-114">최신 앱은 파일 및 네트워킹 I/O를 광범위하게 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1c3ec-114">Modern apps make extensive use of file and networking I/O.</span></span> <span data-ttu-id="1c3ec-115">이전에는 I/O API가 기본적으로 차단되어, 어려운 패턴을 배우고 사용하지 않을 경우 사용자 환경 및 하드웨어 사용률이 좋지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="1c3ec-115">I/O APIs traditionally block by default, resulting in poor user experiences and hardware utilization unless you want to learn and use challenging patterns.</span></span> <span data-ttu-id="1c3ec-116">작업 기반 비동기 API 및 언어 수준의 비동기 프로그래밍 모델은 이 모델을 뒤집어 새로운 개념을 배우지 않고도 기본적으로 비동기 실행을 사용할 수 있게 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c3ec-116">Task-based async APIs and the language-level asynchronous programming model invert this model, making async execution the default with few new concepts to learn.</span></span>

<span data-ttu-id="1c3ec-117">비동기 코드에는 다음과 같은 특성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c3ec-117">Async code has the following characteristics:</span></span>

* <span data-ttu-id="1c3ec-118">I/O 요청이 반환되기를 기다리는 동안 추가 요청을 처리할 수 있도록 스레드를 양도하여 더 많은 서버 요청을 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="1c3ec-118">Handles more server requests by yielding threads to handle more requests while waiting for I/O requests to return.</span></span>
* <span data-ttu-id="1c3ec-119">I/O 요청을 기다리는 동안 UI 조작에 스레드를 양도하고 장기 실행 작업을 다른 CPU 코어로 전환하여 UI 응답성을 개선합니다.</span><span class="sxs-lookup"><span data-stu-id="1c3ec-119">Enables UIs to be more responsive by yielding threads to UI interaction while waiting for I/O requests and by transitioning long-running work to other CPU cores.</span></span>
* <span data-ttu-id="1c3ec-120">대부분의 최신 .NET API는 비동기입니다.</span><span class="sxs-lookup"><span data-stu-id="1c3ec-120">Many of the newer .NET APIs are asynchronous.</span></span>
* <span data-ttu-id="1c3ec-121">.NET에서 비동기 코드를 작성하는 것은 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="1c3ec-121">It's easy to write async code in .NET!</span></span>

## <a name="whats-next"></a><span data-ttu-id="1c3ec-122">새로운 기능</span><span class="sxs-lookup"><span data-stu-id="1c3ec-122">What's next?</span></span>

<span data-ttu-id="1c3ec-123">자세한 내용은 [비동기에 대한 자세한 설명](async-in-depth.md) 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1c3ec-123">For more information, see the [Async in depth](async-in-depth.md) topic.</span></span>

<span data-ttu-id="1c3ec-124">[비동기 프로그래밍 패턴](/asynchronous-programming-patterns/index.md) 항목은 .NET에서 지원되는 세 가지 비동기 프로그래밍 패턴에 대한 개요를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1c3ec-124">The [Asynchronous Programming Patterns](/asynchronous-programming-patterns/index.md) topic provides an overview of the three asynchronous programming patterns supported in .NET:</span></span>  
  
-   <span data-ttu-id="1c3ec-125">[APM(비동기 프로그래밍 모델)](asynchronous-programming-patterns/asynchronous-programming-model-apm.md)(레거시)</span><span class="sxs-lookup"><span data-stu-id="1c3ec-125">[Asynchronous Programming Model (APM)](asynchronous-programming-patterns/asynchronous-programming-model-apm.md) (legacy)</span></span>  
  
-   <span data-ttu-id="1c3ec-126">[EAP(이벤트 기반 비동기 패턴)](asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)(레거시)</span><span class="sxs-lookup"><span data-stu-id="1c3ec-126">[Event-based Asynchronous Pattern (EAP)](asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md) (legacy)</span></span>  
  
-   <span data-ttu-id="1c3ec-127">[TAP(작업 기반 비동기 패턴)](asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md)(새로운 개발에 권장)</span><span class="sxs-lookup"><span data-stu-id="1c3ec-127">[Task-based Asynchronous Pattern (TAP)](asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md) (recommended for new development)</span></span>  

<span data-ttu-id="1c3ec-128">권장 작업 기반 프로그래밍 모델에 대한 자세한 내용은 [작업 기반 비동기 프로그래밍](parallel-programming/task-based-asynchronous-programming.md) 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1c3ec-128">For more information about recommended task-based programming model, see the [Task-based asynchronous programming](parallel-programming/task-based-asynchronous-programming.md) topic.</span></span>
