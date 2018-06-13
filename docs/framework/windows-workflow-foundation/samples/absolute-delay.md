---
title: 절대 지연
ms.date: 03/30/2017
ms.assetid: b483139a-39bb-4560-8003-8969a8fc2cd1
ms.openlocfilehash: 3a104f6b879e9cdc899bad2201ad1ed320a38a2d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33518387"
---
# <a name="absolute-delay"></a><span data-ttu-id="3d2f9-102">절대 지연</span><span class="sxs-lookup"><span data-stu-id="3d2f9-102">Absolute Delay</span></span>
<span data-ttu-id="3d2f9-103">이 샘플의 주요 시나리오는 워크플로 응용 프로그램에서 지속형 타이머를 사용하여 지정된 <xref:System.DateTime>까지 지연하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3d2f9-103">The main scenario for this sample is to delay until a specified <xref:System.DateTime> using durable timers in a workflow application.</span></span> <span data-ttu-id="3d2f9-104">지정된 <xref:System.Activities.Statements.Delay>(또는 분/초 수) 동안만 지연할 수 있다는 점에서 이 샘플은 기본 제공 <xref:System.TimeSpan> 작업을 사용하는 것과는 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="3d2f9-104">This is different from using the built-in <xref:System.Activities.Statements.Delay> activity as this will only allow you to delay for a given <xref:System.TimeSpan> (or number of minutes/seconds).</span></span>  
  
 <span data-ttu-id="3d2f9-105">다음과 같은 일부 실제 시나리오에서는 이러한 차이를 구분해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d2f9-105">Some real-life scenarios in which you may want to make this distinction include the following:</span></span>  
  
1.  <span data-ttu-id="3d2f9-106">오류가 없음을 확인하기 위해 메일 전송을 30초 동안 지연하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d2f9-106">You want to delay sending a mail for 30 seconds to make sure you didn’t make any errors.</span></span>  
  
2.  <span data-ttu-id="3d2f9-107">야근을 하고 있으며 정상 업무 시간(예: 오전 8시)까지 모든 메일을 지연하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d2f9-107">You are working overtime and want to delay all of your mails until normal business hours (such as 8 am).</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="3d2f9-108">세부 항목</span><span class="sxs-lookup"><span data-stu-id="3d2f9-108">Demonstrates</span></span>  
  
1.  <span data-ttu-id="3d2f9-109"><xref:System.Activities.Statements.DurableTimerExtension>을 사용하여 절대 지연 구현</span><span class="sxs-lookup"><span data-stu-id="3d2f9-109"><xref:System.Activities.Statements.DurableTimerExtension> for implementing Absolute Delay</span></span>  
  
2.  <span data-ttu-id="3d2f9-110"><xref:System.Activities.WorkflowApplication>을 사용하여 지속성 타이머에 대해 지속성 설정</span><span class="sxs-lookup"><span data-stu-id="3d2f9-110">Setting up persistence using <xref:System.Activities.WorkflowApplication> for Durable Timers</span></span>  
  
3.  <span data-ttu-id="3d2f9-111"><xref:System.Activities.NativeActivity%601>를 통해 확장성 지점 사용</span><span class="sxs-lookup"><span data-stu-id="3d2f9-111">Use of <xref:System.Activities.NativeActivity%601> for using Extensibility points</span></span>  
  
4.  <span data-ttu-id="3d2f9-112">SendEmail 작업에서 <xref:System.Activities.CodeActivity%601> 사용</span><span class="sxs-lookup"><span data-stu-id="3d2f9-112">Use of <xref:System.Activities.CodeActivity%601> in the SendEmail activity</span></span>  
  
5.  <xref:System.Activities.Statements.Delay>  
  
6.  <span data-ttu-id="3d2f9-113">XAML 전용 워크플로</span><span class="sxs-lookup"><span data-stu-id="3d2f9-113">XAML-only workflow</span></span>  
  
 <span data-ttu-id="3d2f9-114">이 샘플에서는 <xref:System.DateTime>을 받아들이고 지속형 타이머를 사용하여 지연 기간을 등록하는 사용자 지정 작업을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3d2f9-114">This sample demonstrates how to create a custom activity which takes in a <xref:System.DateTime> and uses durable timers to register the delay duration.</span></span> <span data-ttu-id="3d2f9-115">지속형 타이머를 사용하는 경우 책갈피를 타이머 확장에 등록해야 하므로 <xref:System.Activities.NativeActivity>를 사용하여 해당 책갈피를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d2f9-115">When using durable timers, you must use a <xref:System.Activities.NativeActivity> to create a bookmark, as you will need to register this bookmark with the timer extension.</span></span> <span data-ttu-id="3d2f9-116">이 샘플에서는 지속형 타이머가 만료될 경우 `OnTimerExpired` 메서드가 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d2f9-116">In this sample, when the durable timer expires, the `OnTimerExpired` method will be called.</span></span> <span data-ttu-id="3d2f9-117">런타임에 이 정보를 제공하려면 <xref:System.Activities.NativeActivity%601.CacheMetadata%2A> 이벤트에 타이머 확장을 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d2f9-117">Make sure that you are adding the timer extension in the <xref:System.Activities.NativeActivity%601.CacheMetadata%2A> event to ensure you are providing the runtime with this information.</span></span> <span data-ttu-id="3d2f9-118">기타 구현 세부 정보는 <xref:System.DateTime>에서 <xref:System.TimeSpan>으로 변환할 논리를 구현해야 한다는 것뿐입니다. 지속형 타이머는 <xref:System.DateTime>만 받아들이기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="3d2f9-118">The only other implementation detail is that you will need to implement logic to convert from <xref:System.DateTime> to <xref:System.TimeSpan>, as durable timers only take in a <xref:System.DateTime>.</span></span> <span data-ttu-id="3d2f9-119">이 경우 정확도가 약간 저하됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d2f9-119">Do note that there is a small lapse in accuracy by doing</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3d2f9-120"><xref:System.DateTime>에서 <xref:System.TimeSpan>으로 변환하면 정확도가 약간 손실됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d2f9-120">There is a small loss of accuracy by converting from <xref:System.DateTime> to <xref:System.TimeSpan>.</span></span>  
  
 <span data-ttu-id="3d2f9-121">이 샘플에서는 <xref:System.Activities.WorkflowApplication>에 대해 지속성을 설정하는 방법도 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3d2f9-121">This sample also demonstrates how to turn on persistence for a <xref:System.Activities.WorkflowApplication>.</span></span> <span data-ttu-id="3d2f9-122">이 특정 샘플에서는 타이머가 만료될 때까지 기다리는 유휴 시간 동안 워크플로 데이터가 지속성 데이터베이스에 언로드되는 지속형 타이머를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3d2f9-122">For this particular sample, we will be using durable timers in which the workflow data will be unloaded into the persistence database during the idle time while waiting for timer to expire.</span></span> <span data-ttu-id="3d2f9-123">다른 지속성 동작에 이 구현을 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d2f9-123">This implementation can also be used for other persistence actions.</span></span> <span data-ttu-id="3d2f9-124">이 샘플에서는 SQL Server로 지속성 연결 문자열을 설정하는 방법 및 워크플로 인스턴스에 대한 데이터를 저장하기 위해 인스턴스 저장소를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3d2f9-124">This sample shows how to set up the persistence connection string with SQL Server, and how to create the instance store in order to persist the data for workflow instances.</span></span> <span data-ttu-id="3d2f9-125">워크플로 인스턴스를 실행 가능하게 만드는 이벤트가 발생한 후 워크플로를 다시 시작하는 방법에 대한 논리가 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d2f9-125">Logic is provided on how to resume the workflow once an event is raised which makes the workflow instance runnable.</span></span>  
  
 <span data-ttu-id="3d2f9-126">이 샘플을 실행 하는 대로 기본 제공 지연이 시작 되 고 완료 되 면를 차례로 시간 전자 메일 메시지를 보내도록 하면 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d2f9-126">As you step through this sample, you will see the time in which the built-in delay begins and completes, which in turn will cause an email message to be sent.</span></span> <span data-ttu-id="3d2f9-127">여기서 AbsoluteDelay 작업은 지정한 <xref:System.DateTime>(또는 <xref:System.DateTime>이 만료된 경우 0초) 전까지 중지되며, 만료 시 전자 메일이 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d2f9-127">From there, the AbsoluteDelay activity will halt until a specified <xref:System.DateTime> (or 0 seconds if the <xref:System.DateTime> has expired) which in turn will send out an email upon expiration.</span></span> <span data-ttu-id="3d2f9-128">이 샘플에서는 기본 제공 <xref:System.Activities.Statements.Delay> 기능의 두 가지 사용 사례를 AbsoluteDelay 작업 사용과 비교하여 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3d2f9-128">This will show the two different use cases of the built-in <xref:System.Activities.Statements.Delay> functionality versus using an AbsoluteDelay activity.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="3d2f9-129">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="3d2f9-129">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="3d2f9-130">SQL Server Express 이상이 컴퓨터에 설치되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="3d2f9-130">Ensure you have SQL Server Express (or higher) installed on your machine</span></span>  
  
2.  <span data-ttu-id="3d2f9-131">[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 명령 프롬프트의 WF/Basic/Services/AbsoluteDelay/CS에서 setup.cmd를 실행하여 AbsoluteDelaySampleDB 데이터베이스, 지속성 스키마 및 지속성 논리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3d2f9-131">Run setup.cmd (from WF/Basic/Services/AbsoluteDelay/CS) in a [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] command prompt to create the AbsoluteDelaySampleDB database, create the persistence schema and create the persistence logic.</span></span>  
  
3.  <span data-ttu-id="3d2f9-132">[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]에서 솔루션을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="3d2f9-132">Open the solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
4.  <span data-ttu-id="3d2f9-133">지연 작업의 기간을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3d2f9-133">Specify the Duration in the Delay activity.</span></span>  
  
5.  <span data-ttu-id="3d2f9-134">AbsoluteDelay 작업의 ExpirationTime을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3d2f9-134">Specify the ExpirationTime in the AbsoluteDelay activity.</span></span>  
  
6.  <span data-ttu-id="3d2f9-135">SendMail 작업의 SendMailTo, SendMailFrom, SendMailSubject, SendMailBody 및 SmtpHost 필드를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="3d2f9-135">Update the SendMailTo, SendMailFrom, SendMailSubject, SendMailBody, and SmtpHost fields in the SendMail activity.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3d2f9-136">올바른 SMTP 호스트를 입력하지 않으면 응용 프로그램에서 SMTP 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="3d2f9-136">If you do not enter a valid SMTP host, the application will throw a SMTP exception.</span></span>  
  
7.  <span data-ttu-id="3d2f9-137">선택 하 여 솔루션을 빌드합니다 **빌드**, **솔루션 빌드**합니다.</span><span class="sxs-lookup"><span data-stu-id="3d2f9-137">Build the solution by selecting **Build**, **Build Solution**.</span></span>  
  
8.  <span data-ttu-id="3d2f9-138">키를 눌러 솔루션을 실행 **F5**합니다.</span><span class="sxs-lookup"><span data-stu-id="3d2f9-138">Run the solution by pressing **F5**.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="3d2f9-139">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d2f9-139">The samples may already be installed on your machine.</span></span> <span data-ttu-id="3d2f9-140">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="3d2f9-140">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="3d2f9-141">이 디렉터리가로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4에 대 한 Windows WF (Workflow Foundation) 샘플](http://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플.</span><span class="sxs-lookup"><span data-stu-id="3d2f9-141">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="3d2f9-142">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d2f9-142">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\AbsoluteDelay`
