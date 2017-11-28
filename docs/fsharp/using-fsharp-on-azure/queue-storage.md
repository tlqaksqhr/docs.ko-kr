---
title: "F #을 사용 하 여 Azure 큐 저장소 시작"
description: "Azure 큐는 안정적이 고 비동기 응용 프로그램 구성 요소 간의 메시징을 제공 합니다. 메시징 사용 독립적으로 확장할 응용 프로그램 구성 요소를 클라우드입니다."
keywords: "visual f #, f #, 기능 프로그래밍,.NET,.NET Core를 Azure"
author: sylvanc
ms.author: phcart
ms.date: 09/20/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 70dc554c-8f4d-42a7-8e2a-6438657d012a
ms.openlocfilehash: f5ebdb3f3b50996a397c8420b773178493744d70
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="get-started-with-azure-queue-storage-using-f"></a><span data-ttu-id="32269-105">F #을 사용 하 여 Azure 큐 저장소 시작</span><span class="sxs-lookup"><span data-stu-id="32269-105">Get started with Azure Queue storage using F#</span></span> #

<span data-ttu-id="32269-106">Azure 큐 저장소는 클라우드 응용 프로그램 구성 요소 간에 메시징을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="32269-106">Azure Queue storage provides cloud messaging between application components.</span></span> <span data-ttu-id="32269-107">눈금에 대 한 응용 프로그램을 디자인, 응용 프로그램 구성 요소는 종종 분리, 있습니다 수를 독립적으로 확장할 수 있도록.</span><span class="sxs-lookup"><span data-stu-id="32269-107">In designing applications for scale, application components are often decoupled, so that they can scale independently.</span></span> <span data-ttu-id="32269-108">큐 저장소 바탕 화면, 온-프레미스 서버 또는 모바일 장치는 클라우드에서 실행 중인 여부 비동기 메시징 응용 프로그램 구성 요소 간의 통신을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="32269-108">Queue storage delivers asynchronous messaging for communication between application components, whether they are running in the cloud, on the desktop, on an on-premises server, or on a mobile device.</span></span> <span data-ttu-id="32269-109">큐 저장소는 비동기 작업을 관리 하 고 프로세스 작업 흐름을 작성도 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="32269-109">Queue storage also supports managing asynchronous tasks and building process work flows.</span></span>

### <a name="about-this-tutorial"></a><span data-ttu-id="32269-110">이 자습서 정보</span><span class="sxs-lookup"><span data-stu-id="32269-110">About this tutorial</span></span>

<span data-ttu-id="32269-111">이 자습서에서는 Azure 큐 저장소를 사용 하 여 몇 가지 일반적인 작업에 대 한 F # 코드를 작성 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="32269-111">This tutorial shows how to write F# code for some common tasks using Azure Queue storage.</span></span> <span data-ttu-id="32269-112">다루는 작업 만들기 및 큐를 삭제 하 고 추가, 읽기 및 큐 메시지 삭제를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="32269-112">Tasks covered include creating and deleting queues and adding, reading, and deleting queue messages.</span></span>

<span data-ttu-id="32269-113">큐 저장소의 개념적인 개요를 참조 하십시오 [큐 저장소에 대 한.NET 가이드](/azure/storage/storage-dotnet-how-to-use-queues)합니다.</span><span class="sxs-lookup"><span data-stu-id="32269-113">For a conceptual overview of queue storage, please see [the .NET guide for queue storage](/azure/storage/storage-dotnet-how-to-use-queues).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="32269-114">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="32269-114">Prerequisites</span></span>

<span data-ttu-id="32269-115">이 가이드를 사용 하려면 먼저 [Azure 저장소 계정 만들기](/azure/storage/storage-create-storage-account)합니다.</span><span class="sxs-lookup"><span data-stu-id="32269-115">To use this guide, you must first [create an Azure storage account](/azure/storage/storage-create-storage-account).</span></span>
<span data-ttu-id="32269-116">또한이 계정에 대 한 저장소 액세스 키를 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="32269-116">You'll also need your storage access key for this account.</span></span>

## <a name="create-an-f-script-and-start-f-interactive"></a><span data-ttu-id="32269-117">만들기는 F # 스크립트와 시작 F # 대화형</span><span class="sxs-lookup"><span data-stu-id="32269-117">Create an F# Script and Start F# Interactive</span></span>

<span data-ttu-id="32269-118">이 문서에 있는 예제에서 F # 응용 프로그램 또는 F # 스크립트에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32269-118">The samples in this article can be used in either an F# application or an F# script.</span></span> <span data-ttu-id="32269-119">F # 스크립트를 만들려면으로 파일 만들기는 `.fsx` 예를 들어 확장 `queues.fsx`, F # 개발 환경에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="32269-119">To create an F# script, create a file with the `.fsx` extension, for example `queues.fsx`, in your F# development environment.</span></span>

<span data-ttu-id="32269-120">를 사용 하 여 한 [패키지 관리자](package-management.md) 와 같은 [Paket](https://fsprojects.github.io/Paket/) 또는 [NuGet](https://www.nuget.org/) 를 설치 하는 `WindowsAzure.Storage` 패키지와 참조 `WindowsAzure.Storage.dll` 는 를사용하여스크립트에서`#r`지시문입니다.</span><span class="sxs-lookup"><span data-stu-id="32269-120">Next, use a [package manager](package-management.md) such as [Paket](https://fsprojects.github.io/Paket/) or [NuGet](https://www.nuget.org/) to install the `WindowsAzure.Storage` package and reference `WindowsAzure.Storage.dll` in your script using a `#r` directive.</span></span>

### <a name="add-namespace-declarations"></a><span data-ttu-id="32269-121">네임 스페이스 선언을 추가합니다</span><span class="sxs-lookup"><span data-stu-id="32269-121">Add namespace declarations</span></span>

<span data-ttu-id="32269-122">다음 추가 `open` 문을의 맨 위에 `queues.fsx` 파일:</span><span class="sxs-lookup"><span data-stu-id="32269-122">Add the following `open` statements to the top of the `queues.fsx` file:</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L1-L3)]

### <a name="get-your-connection-string"></a><span data-ttu-id="32269-123">연결 문자열 가져오기</span><span class="sxs-lookup"><span data-stu-id="32269-123">Get your connection string</span></span>

<span data-ttu-id="32269-124">이 자습서에 대 한 Azure 저장소 연결 문자열이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="32269-124">You'll need an Azure Storage connection string for this tutorial.</span></span> <span data-ttu-id="32269-125">연결 문자열에 대 한 자세한 내용은 참조 [저장소 연결 문자열 구성](/azure/storage/storage-configure-connection-string)합니다.</span><span class="sxs-lookup"><span data-stu-id="32269-125">For more information about connection strings, see [Configure Storage Connection Strings](/azure/storage/storage-configure-connection-string).</span></span>

<span data-ttu-id="32269-126">자습서에서는 다음과 같이 스크립트에 연결 문자열을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="32269-126">For the tutorial, you'll enter your connection string in your script, like this:</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L9-L9)]

<span data-ttu-id="32269-127">그러나이 방법은 **좋지** 를 실제 프로젝트.</span><span class="sxs-lookup"><span data-stu-id="32269-127">However, this is **not recommended** for real projects.</span></span> <span data-ttu-id="32269-128">저장소 계정 키 저장소 계정에 대 한 루트 암호와 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="32269-128">Your storage account key is similar to the root password for your storage account.</span></span> <span data-ttu-id="32269-129">항상 저장소 계정 키를 보호 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="32269-129">Always be careful to protect your storage account key.</span></span> <span data-ttu-id="32269-130">하드 코딩을 다른 사용자에 게 액세스가 허용 되는 일반 텍스트 파일에 저장 하거나 다른 사용자에 게 배포 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="32269-130">Avoid distributing it to other users, hard-coding it, or saving it in a plain-text file that is accessible to others.</span></span> <span data-ttu-id="32269-131">노출 되었다고 판단 되 면 Azure 포털을 사용 하 여 키를 다시 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32269-131">You can regenerate your key using the Azure Portal if you believe it may have been compromised.</span></span>

<span data-ttu-id="32269-132">실제 응용 프로그램 저장소 연결 문자열을 유지 관리 하는 가장 좋은 방법은 구성 파일에는 합니다.</span><span class="sxs-lookup"><span data-stu-id="32269-132">For real applications, the best way to maintain your storage connection string is in a configuration file.</span></span> <span data-ttu-id="32269-133">구성 파일에서 연결 문자열을 페치 하려면이 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32269-133">To fetch the connection string from a configuration file, you can do this:</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L11-L13)]

<span data-ttu-id="32269-134">Azure 구성 관리자를 사용 하는 것은 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="32269-134">Using Azure Configuration Manager is optional.</span></span> <span data-ttu-id="32269-135">.NET Framework 등의 API를 사용할 수도 있습니다 `ConfigurationManager` 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="32269-135">You can also use an API such as the .NET Framework's `ConfigurationManager` type.</span></span>

### <a name="parse-the-connection-string"></a><span data-ttu-id="32269-136">연결 문자열을 구문 분석</span><span class="sxs-lookup"><span data-stu-id="32269-136">Parse the connection string</span></span>

<span data-ttu-id="32269-137">연결 문자열을 구문 분석 하려면 다음을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="32269-137">To parse the connection string, use:</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L19-L20)]

<span data-ttu-id="32269-138">이 반환 됩니다는 `CloudStorageAccount`합니다.</span><span class="sxs-lookup"><span data-stu-id="32269-138">This will return a `CloudStorageAccount`.</span></span>

### <a name="create-the-queue-service-client"></a><span data-ttu-id="32269-139">큐 서비스 클라이언트 만들기</span><span class="sxs-lookup"><span data-stu-id="32269-139">Create the Queue service client</span></span>

<span data-ttu-id="32269-140">`CloudQueueClient` 클래스를 사용 하면 큐 저장소에 저장 된 큐를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32269-140">The `CloudQueueClient` class enables you to retrieve queues stored in Queue storage.</span></span> <span data-ttu-id="32269-141">서비스 클라이언트를 만드는 한 가지 방법은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="32269-141">Here's one way to create the service client:</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L26-L26)]

<span data-ttu-id="32269-142">이제 데이터를 읽고 큐 저장소에 데이터를 기록 하는 코드를 작성할 준비가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="32269-142">Now you are ready to write code that reads data from and writes data to Queue storage.</span></span>

## <a name="create-a-queue"></a><span data-ttu-id="32269-143">큐 만들기</span><span class="sxs-lookup"><span data-stu-id="32269-143">Create a queue</span></span>

<span data-ttu-id="32269-144">이 예제에는 존재 하지 않는 경우 큐를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="32269-144">This example shows how to create a queue if it doesn't already exist:</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L32-L36)]

## <a name="insert-a-message-into-a-queue"></a><span data-ttu-id="32269-145">큐에 메시지를 삽입 합니다.</span><span class="sxs-lookup"><span data-stu-id="32269-145">Insert a message into a queue</span></span>

<span data-ttu-id="32269-146">기존 큐에 메시지를 삽입 하려면 먼저 새 만들려면 `CloudQueueMessage`합니다.</span><span class="sxs-lookup"><span data-stu-id="32269-146">To insert a message into an existing queue, first create a new `CloudQueueMessage`.</span></span> <span data-ttu-id="32269-147">그런 다음 호출 하 여 `AddMessage` 메서드.</span><span class="sxs-lookup"><span data-stu-id="32269-147">Next, call the `AddMessage` method.</span></span> <span data-ttu-id="32269-148">A `CloudQueueMessage` 를 u t F-8 형식 문자열 중 하나에서 생성 또는 `byte` 배열은 다음과 같이 합니다.</span><span class="sxs-lookup"><span data-stu-id="32269-148">A `CloudQueueMessage` can be created from either a string (in UTF-8 format) or a `byte` array, like this:</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L42-L44)]

## <a name="peek-at-the-next-message"></a><span data-ttu-id="32269-149">다음 메시지 엿보기</span><span class="sxs-lookup"><span data-stu-id="32269-149">Peek at the next message</span></span>

<span data-ttu-id="32269-150">호출 하 여 큐에서 제거 하지 않고 큐 앞의 메시지를 피킹할 수 있습니다는 `PeekMessage` 메서드.</span><span class="sxs-lookup"><span data-stu-id="32269-150">You can peek at the message in the front of a queue, without removing it from the queue, by calling the `PeekMessage` method.</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L50-L52)]

## <a name="get-the-next-message-for-processing"></a><span data-ttu-id="32269-151">다음 메시지 처리에 대 한 가져오기</span><span class="sxs-lookup"><span data-stu-id="32269-151">Get the next message for processing</span></span>

<span data-ttu-id="32269-152">호출 하 여 처리를 위해 큐의 앞에 메시지를 검색할 수 있습니다는 `GetMessage` 메서드.</span><span class="sxs-lookup"><span data-stu-id="32269-152">You can retrieve the message at the front of a queue for processing by calling the `GetMessage` method.</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L58-L59)]

<span data-ttu-id="32269-153">나중에 사용 하 여 메시지를 성공적으로 처리를 나타낼 `DeleteMessage`합니다.</span><span class="sxs-lookup"><span data-stu-id="32269-153">You later indicate successful processing of the message by using `DeleteMessage`.</span></span>

## <a name="change-the-contents-of-a-queued-message"></a><span data-ttu-id="32269-154">대기 중인된 메시지의 내용을 변경합니다</span><span class="sxs-lookup"><span data-stu-id="32269-154">Change the contents of a queued message</span></span>

<span data-ttu-id="32269-155">검색된 메시지 내부에서 큐의 내용을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32269-155">You can change the contents of a retrieved message in-place in the queue.</span></span> <span data-ttu-id="32269-156">메시지 작업 작업을 나타내는 경우에 작업 작업의 상태를 업데이트 하려면이 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32269-156">If the message represents a work task, you could use this feature to update the status of the work task.</span></span> <span data-ttu-id="32269-157">다음 코드는 새 내용으로 큐 메시지를 업데이트 하 고 다른 60 초를 확장 하 여 표시 제한 시간을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="32269-157">The following code updates the queue message with new contents, and sets the visibility timeout to extend another 60 seconds.</span></span> <span data-ttu-id="32269-158">이 메시지와 관련 된 작업의 상태를 저장 하 고 클라이언트 메시지에 대해 작업을 계속 하려면 다른 분을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="32269-158">This saves the state of work associated with the message, and gives the client another minute to continue working on the message.</span></span> <span data-ttu-id="32269-159">큐 메시지의 처리 단계 하드웨어 또는 소프트웨어 오류로 인해 실패 한 경우 처음부터 다시 시작 하지 않고도 여러 단계의 워크플로 추적 하기 위해이 방법을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32269-159">You could use this technique to track multi-step workflows on queue messages, without having to start over from the beginning if a processing step fails due to hardware or software failure.</span></span> <span data-ttu-id="32269-160">일반적으로는 다시 시도 횟수를 보관할 때 하 고 메시지를 몇 번 이상 다시 시도 하는 경우 파일을 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="32269-160">Typically, you would keep a retry count as well, and if the message is retried more than some number of times, you would delete it.</span></span> <span data-ttu-id="32269-161">이 처리 될 때마다 응용 프로그램 오류를 트리거하는 메시지 로부터 보호 됩니다.</span><span class="sxs-lookup"><span data-stu-id="32269-161">This protects against a message that triggers an application error each time it is processed.</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L65-L69)]

## <a name="de-queue-the-next-message"></a><span data-ttu-id="32269-162">다음 메시지 큐에서 제거</span><span class="sxs-lookup"><span data-stu-id="32269-162">De-queue the next message</span></span>

<span data-ttu-id="32269-163">코드에는 두 단계로 큐에서 메시지를 큐 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="32269-163">Your code de-queues a message from a queue in two steps.</span></span> <span data-ttu-id="32269-164">호출 하는 경우 `GetMessage`를 큐에 있는 다음 메시지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="32269-164">When you call `GetMessage`, you get the next message in a queue.</span></span> <span data-ttu-id="32269-165">반환 된 메시지 `GetMessage` 이 큐에서 메시지를 읽을 다른 모든 코드 보이지 않게 합니다.</span><span class="sxs-lookup"><span data-stu-id="32269-165">A message returned from `GetMessage` becomes invisible to any other code reading messages from this queue.</span></span> <span data-ttu-id="32269-166">이 메시지 기본적으로 30 초 동안 보이지 않는 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="32269-166">By default, this message stays invisible for 30 seconds.</span></span> <span data-ttu-id="32269-167">메시지 큐에서 제거를 마치려면 호출 또한 해야 `DeleteMessage`합니다.</span><span class="sxs-lookup"><span data-stu-id="32269-167">To finish removing the message from the queue, you must also call `DeleteMessage`.</span></span> <span data-ttu-id="32269-168">메시지를 제거 하는이 두 단계 과정 통해 있는 코드에 하드웨어 또는 소프트웨어 오류로 인해 메시지를 처리 하지 못하는 경우 코드의 다른 인스턴스 수 동일한 메시지가 다시 시도 하십시오 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32269-168">This two-step process of removing a message assures that if your code fails to process a message due to hardware or software failure, another instance of your code can get the same message and try again.</span></span> <span data-ttu-id="32269-169">코드 호출 `DeleteMessage` 메시지 처리 된 후 마우스 오른쪽 단추로 합니다.</span><span class="sxs-lookup"><span data-stu-id="32269-169">Your code calls `DeleteMessage` right after the message has been processed.</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L75-L76)]

## <a name="use-async-workflows-with-common-queue-storage-apis"></a><span data-ttu-id="32269-170">비동기 워크플로 사용 하 여 일반적인 큐 저장소 Api</span><span class="sxs-lookup"><span data-stu-id="32269-170">Use Async workflows with common Queue storage APIs</span></span>

<span data-ttu-id="32269-171">이 예제에서는 일반적인 큐 저장소 Api는 비동기 워크플로 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="32269-171">This example shows how to use an async workflow with common Queue storage APIs.</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L82-L91)]

## <a name="additional-options-for-de-queuing-messages"></a><span data-ttu-id="32269-172">메시지를 역직렬화 큐에 대 한 추가 옵션</span><span class="sxs-lookup"><span data-stu-id="32269-172">Additional options for de-queuing messages</span></span>

<span data-ttu-id="32269-173">두 가지 방법으로 큐에서 메시지 검색을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32269-173">There are two ways you can customize message retrieval from a queue.</span></span>
<span data-ttu-id="32269-174">첫째, 32) (최대 메시지 일괄 처리를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32269-174">First, you can get a batch of messages (up to 32).</span></span> <span data-ttu-id="32269-175">둘째, 많거나 완벽 하 게 각 메시지를 처리 하는 시간이 적은 코드를 허용 더 길거나 더 짧은 표시 안 함 시간 초과 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32269-175">Second, you can set a longer or shorter invisibility timeout, allowing your code more or less time to fully process each message.</span></span> <span data-ttu-id="32269-176">다음 코드 예제에서는 `GetMessages` 보려면 20 하나로 메시지를 호출 하 고 다음 각 메시지를 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="32269-176">The following code example uses `GetMessages` to get 20 messages in one call and then processes each message.</span></span> <span data-ttu-id="32269-177">또한 각 메시지에 대해 5 분에 표시 안 함 시간 제한을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="32269-177">It also sets the invisibility timeout to five minutes for each message.</span></span> <span data-ttu-id="32269-178">이와 동시에 모든 메시지에 대해 5 분을 시작 하는 참고 후 일 분에 대 한 호출 이후 경과한 `GetMessages`, 모든 메시지는 삭제 되지 않았으므로 다시 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="32269-178">Note that the 5 minutes starts for all messages at the same time, so after 5 minutes have passed since the call to `GetMessages`, any messages which have not been deleted will become visible again.</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L97-L99)]

## <a name="get-the-queue-length"></a><span data-ttu-id="32269-179">큐 길이 가져오기</span><span class="sxs-lookup"><span data-stu-id="32269-179">Get the queue length</span></span>

<span data-ttu-id="32269-180">큐에 있는 메시지 수의 예측을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32269-180">You can get an estimate of the number of messages in a queue.</span></span> <span data-ttu-id="32269-181">`FetchAttributes` 메서드 요청 큐 서비스의 메시지 수를 포함 하 여 큐 특성을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32269-181">The `FetchAttributes` method asks the Queue service to retrieve the queue attributes, including the message count.</span></span> <span data-ttu-id="32269-182">`ApproximateMessageCount` 하 여 검색할 마지막 값을 반환 하는 속성은 `FetchAttributes` 큐 서비스를 호출 하지 않고 메서드.</span><span class="sxs-lookup"><span data-stu-id="32269-182">The `ApproximateMessageCount` property returns the last value retrieved by the `FetchAttributes` method, without calling the Queue service.</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L105-L106)]

## <a name="delete-a-queue"></a><span data-ttu-id="32269-183">큐 삭제</span><span class="sxs-lookup"><span data-stu-id="32269-183">Delete a queue</span></span>

<span data-ttu-id="32269-184">호출 하는 큐와 그 안에 포함 된 모든 메시지를 삭제 하려면는 `Delete` 큐 개체에서 메서드.</span><span class="sxs-lookup"><span data-stu-id="32269-184">To delete a queue and all the messages contained in it, call the `Delete` method on the queue object.</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L112-L113)]

## <a name="next-steps"></a><span data-ttu-id="32269-185">다음 단계</span><span class="sxs-lookup"><span data-stu-id="32269-185">Next steps</span></span>

<span data-ttu-id="32269-186">큐 저장소의 기본 사항 학습 한, 했으므로 더 복잡 한 저장소 작업에 대 한 자세한 내용은 다음이 링크를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="32269-186">Now that you've learned the basics of Queue storage, follow these links to learn about more complex storage tasks.</span></span>

- [<span data-ttu-id="32269-187">.NET 참조 용 저장소 클라이언트 라이브러리</span><span class="sxs-lookup"><span data-stu-id="32269-187">Storage Client Library for .NET reference</span></span>](http://go.microsoft.com/fwlink/?LinkID=390731&clcid=0x409)
- [<span data-ttu-id="32269-188">Azure 저장소 형식 공급자</span><span class="sxs-lookup"><span data-stu-id="32269-188">Azure Storage Type Provider</span></span>](https://github.com/fsprojects/AzureStorageTypeProvider)
- [<span data-ttu-id="32269-189">Azure 저장소 팀 블로그</span><span class="sxs-lookup"><span data-stu-id="32269-189">Azure Storage Team Blog</span></span>](http://blogs.msdn.com/b/windowsazurestorage/)
- [<span data-ttu-id="32269-190">연결 문자열 구성</span><span class="sxs-lookup"><span data-stu-id="32269-190">Configuring Connection Strings</span></span>](http://msdn.microsoft.com/library/azure/ee758697.aspx)
- [<span data-ttu-id="32269-191">REST API 참조</span><span class="sxs-lookup"><span data-stu-id="32269-191">REST API reference</span></span>](http://msdn.microsoft.com/library/azure/dd179355)
