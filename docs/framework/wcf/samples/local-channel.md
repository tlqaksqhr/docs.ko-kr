---
title: "로컬 채널"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fa1917a4-f701-4e82-a439-14a16282c7cc
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: dee09b8f7b1e48a84fa79381d44fe48a4da16129
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="local-channel"></a><span data-ttu-id="8b515-102">로컬 채널</span><span class="sxs-lookup"><span data-stu-id="8b515-102">Local Channel</span></span>
<span data-ttu-id="8b515-103">로컬 채널은 동일한 응용 프로그램 도메인 내에서 통신하는 데 사용되는 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 전송 채널입니다.</span><span class="sxs-lookup"><span data-stu-id="8b515-103">Local Channel is a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] transport channel that is used for communication within the same application domain.</span></span> <span data-ttu-id="8b515-104">로컬 채널은 클라이언트와 서비스가 동일한 응용 프로그램 도메인에서 실행 중이고 일반적인 WCF 채널 스택(메시지의 serialization 및 deserialization)의 오버헤드를 방지해야 하는 경우에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="8b515-104">This is useful for scenarios where the client and the service are running in the same application domain and the overhead of the typical WCF channel stack (serialization and deserialization of messages) must be avoided.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="8b515-105">세부 항목</span><span class="sxs-lookup"><span data-stu-id="8b515-105">Demonstrates</span></span>  
 <span data-ttu-id="8b515-106">로컬 채널</span><span class="sxs-lookup"><span data-stu-id="8b515-106">Local Channel</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="8b515-107">토론</span><span class="sxs-lookup"><span data-stu-id="8b515-107">Discussion</span></span>  
 <span data-ttu-id="8b515-108">이 샘플은 다음의 두 프로젝트 파일로 구성되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b515-108">The sample consists of two project files:</span></span>  
  
-   <span data-ttu-id="8b515-109">**LocalChannel**: 현재 응용 프로그램 도메인 내의 로컬 채널의 프로그래밍 방식으로 표현 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b515-109">**LocalChannel**: The programmatic representation of the local channel within the current application domain.</span></span> <span data-ttu-id="8b515-110">이 프로젝트에서 보내기 구성 요소는 메시지를 메모리 내 큐에 넣고 받기 구성 요소는 메시지를 큐에서 꺼내 해당 메시지를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="8b515-110">In this project, the sending component places the message in an in-memory queue and the receiving component de-queues the message to receive it.</span></span>  
  
-   <span data-ttu-id="8b515-111">**ClientAndService**:이 프로젝트는 콘솔 응용 프로그램에 서비스를 호스트 한 다음 같은 응용 프로그램 도메인 내에서 서비스를 호출 하는 클라이언트를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b515-111">**ClientAndService**: This project hosts a service in a console application and then runs a client to call the service from within the same application domain.</span></span>  
  
 <span data-ttu-id="8b515-112">로컬 채널 디자인은 채널 스택과 serialization 프로세스를 모두 건너뛰므로 속도가 빨라집니다.</span><span class="sxs-lookup"><span data-stu-id="8b515-112">The local channel design skips both the channel stack and the serialization process to increase speed.</span></span> <span data-ttu-id="8b515-113">로컬 전송 채널은 클라이언트의 서비스 호출을 서비스로 전송하고 값을 클라이언트에 다시 반환하는 큐를 사용하여 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b515-113">The local transport channel is implemented using a queue to transport service calls from the client to the service and to return back the value to the client.</span></span> <span data-ttu-id="8b515-114">매개 변수 및 반환 값을 serialize하는 대신 이 샘플에서는 해당 개체를 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="8b515-114">Rather than serializing parameters and return values, the sample copies the objects.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="8b515-115">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="8b515-115">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="8b515-116">LocalChannel 솔루션을 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="8b515-116">Build and run the LocalChannel solution.</span></span>  
  
2.  <span data-ttu-id="8b515-117">서비스 호스트가 시작되고 클라이언트가 로컬 채널을 사용하여 서비스를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="8b515-117">The service host is started and the client calls the service using the local channel.</span></span> <span data-ttu-id="8b515-118">콘솔 창에 서비스 호출 결과가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b515-118">A console window appears to display the results of the service call.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="8b515-119">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b515-119">The samples may already be installed on your machine.</span></span> <span data-ttu-id="8b515-120">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="8b515-120">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="8b515-121">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="8b515-121">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="8b515-122">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b515-122">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Channels\LocalChannel`
