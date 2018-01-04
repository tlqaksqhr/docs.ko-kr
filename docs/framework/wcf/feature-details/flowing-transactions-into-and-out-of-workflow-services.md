---
title: "트랜잭션을 워크플로 서비스 내부 및 외부로 이동"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 03ced70e-b540-4dd9-86c8-87f7bd61f609
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a38c0c224c93941efa767d142aa7738296a62f15
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="flowing-transactions-into-and-out-of-workflow-services"></a><span data-ttu-id="e20ea-102">트랜잭션을 워크플로 서비스 내부 및 외부로 이동</span><span class="sxs-lookup"><span data-stu-id="e20ea-102">Flowing Transactions into and out of Workflow Services</span></span>
<span data-ttu-id="e20ea-103">워크플로 서비스 및 클라이언트는 트랜잭션에 참여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e20ea-103">Workflow services and clients can participate in transactions.</span></span>  <span data-ttu-id="e20ea-104">서비스 작업이 앰비언트 트랜잭션의 일부가 되도록 하려면 <xref:System.ServiceModel.Activities.Receive> 활동 내에 <xref:System.ServiceModel.Activities.TransactedReceiveScope> 활동을 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="e20ea-104">For a service operation to become part of an ambient transaction, place a <xref:System.ServiceModel.Activities.Receive> activity within a <xref:System.ServiceModel.Activities.TransactedReceiveScope> activity.</span></span> <span data-ttu-id="e20ea-105"><xref:System.ServiceModel.Activities.Send> 내의 <xref:System.ServiceModel.Activities.SendReply> 또는 <xref:System.ServiceModel.Activities.TransactedReceiveScope> 활동에서 실행하는 모든 호출은 앰비언트 트랜잭션 내에서도 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="e20ea-105">Any calls made by a <xref:System.ServiceModel.Activities.Send> or a <xref:System.ServiceModel.Activities.SendReply> activity within the <xref:System.ServiceModel.Activities.TransactedReceiveScope> will also be made within the ambient transaction.</span></span> <span data-ttu-id="e20ea-106">워크플로 클라이언트 응용 프로그램에서는 <xref:System.Activities.Statements.TransactionScope> 활동을 사용하여 앰비언트 트랜잭션을 만들고 앰비언트 트랜잭션을 사용하여 서비스 작업을 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e20ea-106">A workflow client application can create an ambient transaction by using the <xref:System.Activities.Statements.TransactionScope> activity and call service operations using the ambient transaction.</span></span> <span data-ttu-id="e20ea-107">이 항목에서는 트랜잭션에 참여하는 워크플로 서비스와 워크플로 클라이언트를 만드는 과정을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e20ea-107">This topic walks you through creating a workflow service and workflow client that participate in transactions.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="e20ea-108">워크플로 서비스 인스턴스가 트랜잭션 내에서 로드되고 워크플로에 <xref:System.Activities.Statements.Persist> 활동이 포함된 경우 트랜잭션 제한 시간이 초과될 때까지 워크플로 인스턴스가 중단됩니다.</span><span class="sxs-lookup"><span data-stu-id="e20ea-108">If a workflow service instance is loaded within a transaction and the workflow contains a <xref:System.Activities.Statements.Persist> activity, the workflow instance will hang until the transaction times out.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e20ea-109"><xref:System.ServiceModel.Activities.TransactedReceiveScope>를 사용할 때마다 <xref:System.ServiceModel.Activities.TransactedReceiveScope> 활동 내에 워크플로의 모든 Receive를 두는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e20ea-109">Whenever you use a <xref:System.ServiceModel.Activities.TransactedReceiveScope> it is recommended to place all Receives in the workflow within <xref:System.ServiceModel.Activities.TransactedReceiveScope> activities.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e20ea-110"><xref:System.ServiceModel.Activities.TransactedReceiveScope>를 사용할 때 메시지가 잘못된 순서로 도착하는 경우 워크플로가 순서가 잘못된 첫 번째 메시지를 전달하려고 할 때 중단됩니다.</span><span class="sxs-lookup"><span data-stu-id="e20ea-110">When using <xref:System.ServiceModel.Activities.TransactedReceiveScope> and messages arrive in the incorrect order, the workflow will be aborted when trying to deliver the first out of order message.</span></span> <span data-ttu-id="e20ea-111">워크플로가 유휴 상태일 때 항상 일관된 중지 지점에 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e20ea-111">You must make sure your workflow is always at a consistent stopping point when the workflow idles.</span></span> <span data-ttu-id="e20ea-112">이렇게 하면 워크플로가 중단된 경우 이전 유지 지점에서 워크플로를 다시 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e20ea-112">This will allow you to restart the workflow from a previous persistence point should the workflow be aborted.</span></span>  
  
### <a name="create-a-shared-library"></a><span data-ttu-id="e20ea-113">공유 라이브러리 만들기</span><span class="sxs-lookup"><span data-stu-id="e20ea-113">Create a shared library</span></span>  
  
1.  <span data-ttu-id="e20ea-114">비어 있는 새 Visual Studio 솔루션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e20ea-114">Create a new empty Visual Studio Solution.</span></span>  
  
2.  <span data-ttu-id="e20ea-115">`Common`이라는 새 클래스 라이브러리 프로젝트를 추가하고,</span><span class="sxs-lookup"><span data-stu-id="e20ea-115">Add a new class library project called `Common`.</span></span> <span data-ttu-id="e20ea-116">다음 어셈블리에 대한 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="e20ea-116">Add references to the following assemblies:</span></span>  
  
    -   <span data-ttu-id="e20ea-117">System.Activities.dll</span><span class="sxs-lookup"><span data-stu-id="e20ea-117">System.Activities.dll</span></span>  
  
    -   <span data-ttu-id="e20ea-118">System.ServiceModel.dll</span><span class="sxs-lookup"><span data-stu-id="e20ea-118">System.ServiceModel.dll</span></span>  
  
    -   <span data-ttu-id="e20ea-119">System.ServiceModel.Activities.dll</span><span class="sxs-lookup"><span data-stu-id="e20ea-119">System.ServiceModel.Activities.dll</span></span>  
  
    -   <span data-ttu-id="e20ea-120">System.Transactions.dll</span><span class="sxs-lookup"><span data-stu-id="e20ea-120">System.Transactions.dll</span></span>  
  
3.  <span data-ttu-id="e20ea-121">`PrintTransactionInfo` 프로젝트에 `Common`라는 새 클래스를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="e20ea-121">Add a new class called `PrintTransactionInfo` to the `Common` project.</span></span> <span data-ttu-id="e20ea-122">이 클래스는 <xref:System.Activities.NativeActivity>에서 파생되며 <xref:System.Activities.NativeActivity.Execute%2A> 메서드를 오버로드합니다.</span><span class="sxs-lookup"><span data-stu-id="e20ea-122">This class is derived from <xref:System.Activities.NativeActivity> and overloads the <xref:System.Activities.NativeActivity.Execute%2A> method.</span></span>  
  
    ```  
    using System;  
    using System;  
    using System.Activities;  
    using System.Transactions;  
  
    namespace Common  
    {  
        public class PrintTransactionInfo : NativeActivity  
        {  
            protected override void Execute(NativeActivityContext context)  
            {  
                RuntimeTransactionHandle rth = context.Properties.Find(typeof(RuntimeTransactionHandle).FullName) as RuntimeTransactionHandle;  
  
                if (rth == null)  
                {  
                    Console.WriteLine("There is no ambient RuntimeTransactionHandle");  
                }  
  
                Transaction t = rth.GetCurrentTransaction(context);  
  
                if (t == null)  
                {  
                    Console.WriteLine("There is no ambient transaction");  
                }  
                else  
                {  
                    Console.WriteLine("Transaction: {0} is {1}", t.TransactionInformation.DistributedIdentifier, t.TransactionInformation.Status);  
                }  
            }  
        }  
  
    }  
    ```  
  
     <span data-ttu-id="e20ea-123">이는 앰비언트 트랜잭션에 대한 정보를 표시하는 기본 활동으로서, 이 항목에 사용되는 서비스 및 클라이언트 워크플로 모두에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e20ea-123">This is a native activity that displays information about the ambient transaction and is used in both the service and client workflows used in this topic.</span></span> <span data-ttu-id="e20ea-124">이 활동에서 사용할 수 있도록 솔루션을 빌드하는 **일반적인** 섹션은 **도구 상자**합니다.</span><span class="sxs-lookup"><span data-stu-id="e20ea-124">Build the solution to make this activity available in the **Common** section of the **Toolbox**.</span></span>  
  
### <a name="implement-the-workflow-service"></a><span data-ttu-id="e20ea-125">워크플로 서비스 구현</span><span class="sxs-lookup"><span data-stu-id="e20ea-125">Implement the workflow service</span></span>  
  
1.  <span data-ttu-id="e20ea-126">새로 추가 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 워크플로 서비스인 `WorkflowService` 에 `Common` 프로젝트.</span><span class="sxs-lookup"><span data-stu-id="e20ea-126">Add a new [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Workflow Service, called `WorkflowService` to the `Common` project.</span></span> <span data-ttu-id="e20ea-127">마우스 오른쪽 단추로 클릭이 작업을 수행 하는 `Common` 프로젝트를 **추가**, **새 항목...** 선택, **워크플로** 아래 **설치 된 템플릿** 선택 **WCF 워크플로 서비스**합니다.</span><span class="sxs-lookup"><span data-stu-id="e20ea-127">To do this right click the `Common` project, select **Add**, **New Item ...**, Select **Workflow** under **Installed Templates** and select **WCF Workflow Service**.</span></span>  
  
     <span data-ttu-id="e20ea-128">![워크플로 서비스 추가](../../../../docs/framework/wcf/feature-details/media/addwfservice.JPG "AddWFService")</span><span class="sxs-lookup"><span data-stu-id="e20ea-128">![Adding a Workflow Service](../../../../docs/framework/wcf/feature-details/media/addwfservice.JPG "AddWFService")</span></span>  
  
2.  <span data-ttu-id="e20ea-129">기본 `ReceiveRequest` 및 `SendResponse` 활동을 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="e20ea-129">Delete the default `ReceiveRequest` and `SendResponse` activities.</span></span>  
  
3.  <span data-ttu-id="e20ea-130"><xref:System.Activities.Statements.WriteLine> 활동을 `Sequential Service` 활동으로 끌어 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="e20ea-130">Drag and drop a <xref:System.Activities.Statements.WriteLine> activity into the `Sequential Service` activity.</span></span> <span data-ttu-id="e20ea-131">다음 예제와 같이 텍스트 속성을 `"Workflow Service starting ..."`으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="e20ea-131">Set the text property to `"Workflow Service starting ..."` as shown in the following example.</span></span>  
  
     <span data-ttu-id="e20ea-132">![WriteLine 활동 추가](../../../../docs/framework/wcf/feature-details/media/addwriteline.JPG "AddWriteLine")</span><span class="sxs-lookup"><span data-stu-id="e20ea-132">![Adding a WriteLine activity](../../../../docs/framework/wcf/feature-details/media/addwriteline.JPG "AddWriteLine")</span></span>  
  
4.  <span data-ttu-id="e20ea-133"><xref:System.ServiceModel.Activities.TransactedReceiveScope>을 <xref:System.Activities.Statements.WriteLine> 활동 뒤로 끌어 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="e20ea-133">Drag and drop a <xref:System.ServiceModel.Activities.TransactedReceiveScope> after the <xref:System.Activities.Statements.WriteLine> activity.</span></span> <span data-ttu-id="e20ea-134"><xref:System.ServiceModel.Activities.TransactedReceiveScope> 에서 활동을 확인할 수 있습니다는 **메시징** 의 섹션은 **도구 상자**합니다.</span><span class="sxs-lookup"><span data-stu-id="e20ea-134">The <xref:System.ServiceModel.Activities.TransactedReceiveScope> activity can be found in the **Messaging** section of the **Toolbox**.</span></span> <span data-ttu-id="e20ea-135"><xref:System.ServiceModel.Activities.TransactedReceiveScope> 두 섹션으로 구성 된 활동 **요청** 및 **본문**합니다.</span><span class="sxs-lookup"><span data-stu-id="e20ea-135">The <xref:System.ServiceModel.Activities.TransactedReceiveScope> activity is composed of two sections **Request** and **Body**.</span></span> <span data-ttu-id="e20ea-136">**요청** 섹션에 포함 되어는 <xref:System.ServiceModel.Activities.Receive> 활동입니다.</span><span class="sxs-lookup"><span data-stu-id="e20ea-136">The **Request** section contains the <xref:System.ServiceModel.Activities.Receive> activity.</span></span> <span data-ttu-id="e20ea-137">**본문** 섹션에는 메시지가 수신 된 후 트랜잭션 내에서 실행할 활동이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e20ea-137">The **Body** section contains the activities to execute within a transaction after a message has been received.</span></span>  
  
     <span data-ttu-id="e20ea-138">![TransactedReceiveScope 활동 추가](../../../../docs/framework/wcf/feature-details/media/trs.JPG "TR")</span><span class="sxs-lookup"><span data-stu-id="e20ea-138">![Adding a TransactedReceiveScope activity](../../../../docs/framework/wcf/feature-details/media/trs.JPG "TRS")</span></span>  
  
5.  <span data-ttu-id="e20ea-139">선택 된 <xref:System.ServiceModel.Activities.TransactedReceiveScope> 활동과 클릭은 **변수** 단추입니다.</span><span class="sxs-lookup"><span data-stu-id="e20ea-139">Select the <xref:System.ServiceModel.Activities.TransactedReceiveScope> activity and click the **Variables** button.</span></span> <span data-ttu-id="e20ea-140">다음 변수를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="e20ea-140">Add the following variables.</span></span>  
  
     <span data-ttu-id="e20ea-141">![TransactedReceiveScope에 변수 추가](../../../../docs/framework/wcf/feature-details/media/trsvariables.JPG "TRSVariables")</span><span class="sxs-lookup"><span data-stu-id="e20ea-141">![Adding Variables to the TransactedReceiveScope](../../../../docs/framework/wcf/feature-details/media/trsvariables.JPG "TRSVariables")</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e20ea-142">기본적으로 여기에 포함된 데이터 변수를 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e20ea-142">You can delete the data variable that is there by default.</span></span> <span data-ttu-id="e20ea-143">기존 핸들 변수를 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e20ea-143">You can also use the existing handle variable.</span></span>  
  
6.  <span data-ttu-id="e20ea-144">끌어서 놓기는 <xref:System.ServiceModel.Activities.Receive> 내의 활동에서 **요청** 의 섹션은 <xref:System.ServiceModel.Activities.TransactedReceiveScope> 활동입니다.</span><span class="sxs-lookup"><span data-stu-id="e20ea-144">Drag and drop a <xref:System.ServiceModel.Activities.Receive> activity within the **Request** section of the <xref:System.ServiceModel.Activities.TransactedReceiveScope> activity.</span></span> <span data-ttu-id="e20ea-145">다음 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="e20ea-145">Set the following properties:</span></span>  
  
    |<span data-ttu-id="e20ea-146">속성</span><span class="sxs-lookup"><span data-stu-id="e20ea-146">Property</span></span>|<span data-ttu-id="e20ea-147">값</span><span class="sxs-lookup"><span data-stu-id="e20ea-147">Value</span></span>|  
    |--------------|-----------|  
    |<span data-ttu-id="e20ea-148">CanCreateInstance</span><span class="sxs-lookup"><span data-stu-id="e20ea-148">CanCreateInstance</span></span>|<span data-ttu-id="e20ea-149">True(확인란 선택)</span><span class="sxs-lookup"><span data-stu-id="e20ea-149">True (check the checkbox)</span></span>|  
    |<span data-ttu-id="e20ea-150">OperationName</span><span class="sxs-lookup"><span data-stu-id="e20ea-150">OperationName</span></span>|<span data-ttu-id="e20ea-151">StartSample</span><span class="sxs-lookup"><span data-stu-id="e20ea-151">StartSample</span></span>|  
    |<span data-ttu-id="e20ea-152">ServiceContractName</span><span class="sxs-lookup"><span data-stu-id="e20ea-152">ServiceContractName</span></span>|<span data-ttu-id="e20ea-153">ITransactionSample</span><span class="sxs-lookup"><span data-stu-id="e20ea-153">ITransactionSample</span></span>|  
  
     <span data-ttu-id="e20ea-154">워크플로가 다음과 같이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="e20ea-154">The workflow should look like this:</span></span>  
  
     <span data-ttu-id="e20ea-155">![Receive 활동 추가](../../../../docs/framework/wcf/feature-details/media/serviceaddreceive.JPG "ServiceAddReceive")</span><span class="sxs-lookup"><span data-stu-id="e20ea-155">![Adding a Receive activity](../../../../docs/framework/wcf/feature-details/media/serviceaddreceive.JPG "ServiceAddReceive")</span></span>  
  
7.  <span data-ttu-id="e20ea-156">클릭는 **정의...**  연결에 <xref:System.ServiceModel.Activities.Receive> 활동 다음과 같이 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e20ea-156">Click the **Define...** link in the <xref:System.ServiceModel.Activities.Receive> activity and make the following settings:</span></span>  
  
     <span data-ttu-id="e20ea-157">![Recieve 활동에 대 한 메시지 설정 지정](../../../../docs/framework/wcf/feature-details/media/receivemessagesettings.JPG "ReceiveMessageSettings")</span><span class="sxs-lookup"><span data-stu-id="e20ea-157">![Setting message settings for the Recieve activity](../../../../docs/framework/wcf/feature-details/media/receivemessagesettings.JPG "ReceiveMessageSettings")</span></span>  
  
8.  <span data-ttu-id="e20ea-158"><xref:System.Activities.Statements.Sequence> 활동을 <xref:System.ServiceModel.Activities.TransactedReceiveScope>의 본문 섹션으로 끌어 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="e20ea-158">Drag and drop a <xref:System.Activities.Statements.Sequence> activity into the Body section of the <xref:System.ServiceModel.Activities.TransactedReceiveScope>.</span></span> <span data-ttu-id="e20ea-159"><xref:System.Activities.Statements.Sequence> 활동 내에 두 개의 <xref:System.Activities.Statements.WriteLine> 활동을 끌어 놓고 <xref:System.Activities.Statements.WriteLine.Text%2A> 속성을 다음 표와 같이 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="e20ea-159">Within the <xref:System.Activities.Statements.Sequence> activity drag and drop two <xref:System.Activities.Statements.WriteLine> activities and set the <xref:System.Activities.Statements.WriteLine.Text%2A> properties as shown in the following table.</span></span>  
  
    |<span data-ttu-id="e20ea-160">동작</span><span class="sxs-lookup"><span data-stu-id="e20ea-160">Activity</span></span>|<span data-ttu-id="e20ea-161">값</span><span class="sxs-lookup"><span data-stu-id="e20ea-161">Value</span></span>|  
    |--------------|-----------|  
    |<span data-ttu-id="e20ea-162">1st WriteLine</span><span class="sxs-lookup"><span data-stu-id="e20ea-162">1st WriteLine</span></span>|<span data-ttu-id="e20ea-163">"Service: 완료 된 수신"</span><span class="sxs-lookup"><span data-stu-id="e20ea-163">"Service: Receive Completed"</span></span>|  
    |<span data-ttu-id="e20ea-164">2nd WriteLine</span><span class="sxs-lookup"><span data-stu-id="e20ea-164">2nd WriteLine</span></span>|<span data-ttu-id="e20ea-165">"Service: Received = " + requestMessage</span><span class="sxs-lookup"><span data-stu-id="e20ea-165">"Service: Received = " + requestMessage</span></span>|  
  
     <span data-ttu-id="e20ea-166">이제 워크플로가 다음과 같이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="e20ea-166">The workflow should now look like this:</span></span>  
  
     <span data-ttu-id="e20ea-167">![WriteLine 활동 추가](../../../../docs/framework/wcf/feature-details/media/afteraddingwritelines.JPG "AfterAddingWriteLines")</span><span class="sxs-lookup"><span data-stu-id="e20ea-167">![Adding WriteLine activities](../../../../docs/framework/wcf/feature-details/media/afteraddingwritelines.JPG "AfterAddingWriteLines")</span></span>  
  
9. <span data-ttu-id="e20ea-168">끌어서 놓기는 `PrintTransactionInfo` 두 번째 뒤로 <xref:System.Activities.Statements.WriteLine> 활동에는 **본문** 에 <xref:System.ServiceModel.Activities.TransactedReceiveScope> 활동입니다.</span><span class="sxs-lookup"><span data-stu-id="e20ea-168">Drag and drop the `PrintTransactionInfo` activity after the second <xref:System.Activities.Statements.WriteLine> activity in the **Body** in the <xref:System.ServiceModel.Activities.TransactedReceiveScope> activity.</span></span>  
  
     <span data-ttu-id="e20ea-169">![PrintTransactionInfo 추가 후](../../../../docs/framework/wcf/feature-details/media/afteraddingprinttransactioninfo.JPG "AfterAddingPrintTransactionInfo")</span><span class="sxs-lookup"><span data-stu-id="e20ea-169">![After adding PrintTransactionInfo](../../../../docs/framework/wcf/feature-details/media/afteraddingprinttransactioninfo.JPG "AfterAddingPrintTransactionInfo")</span></span>  
  
10. <span data-ttu-id="e20ea-170"><xref:System.Activities.Statements.Assign> 활동을 `PrintTransactionInfo` 활동 뒤로 끌어 놓고 해당 속성을 다음 표와 같이 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="e20ea-170">Drag and drop an <xref:System.Activities.Statements.Assign> activity after the `PrintTransactionInfo` activity and set its properties according to the following table.</span></span>  
  
    |<span data-ttu-id="e20ea-171">속성</span><span class="sxs-lookup"><span data-stu-id="e20ea-171">Property</span></span>|<span data-ttu-id="e20ea-172">값</span><span class="sxs-lookup"><span data-stu-id="e20ea-172">Value</span></span>|  
    |--------------|-----------|  
    |<span data-ttu-id="e20ea-173">후</span><span class="sxs-lookup"><span data-stu-id="e20ea-173">To</span></span>|<span data-ttu-id="e20ea-174">replyMessage</span><span class="sxs-lookup"><span data-stu-id="e20ea-174">replyMessage</span></span>|  
    |<span data-ttu-id="e20ea-175">값</span><span class="sxs-lookup"><span data-stu-id="e20ea-175">Value</span></span>|<span data-ttu-id="e20ea-176">"Service: Sending reply"</span><span class="sxs-lookup"><span data-stu-id="e20ea-176">"Service: Sending reply."</span></span>|  
  
11. <span data-ttu-id="e20ea-177"><xref:System.Activities.Statements.WriteLine> 활동을 <xref:System.Activities.Statements.Assign> 활동 뒤로 끌어 놓고 해당 <xref:System.Activities.Statements.WriteLine.Text%2A> 속성을 "Service: Begin reply"로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="e20ea-177">Drag and drop a <xref:System.Activities.Statements.WriteLine> activity after the <xref:System.Activities.Statements.Assign> activity and set its <xref:System.Activities.Statements.WriteLine.Text%2A> property to "Service: Begin reply."</span></span>  
  
     <span data-ttu-id="e20ea-178">이제 워크플로가 다음과 같이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="e20ea-178">The workflow should now look like this:</span></span>  
  
     <span data-ttu-id="e20ea-179">![Assign 및 WriteLine 추가 후](../../../../docs/framework/wcf/feature-details/media/afteraddingsbrwriteline.JPG "AfterAddingSBRWriteLine")</span><span class="sxs-lookup"><span data-stu-id="e20ea-179">![After adding Assign and WriteLine](../../../../docs/framework/wcf/feature-details/media/afteraddingsbrwriteline.JPG "AfterAddingSBRWriteLine")</span></span>  
  
12. <span data-ttu-id="e20ea-180">마우스 오른쪽 단추로 클릭는 <xref:System.ServiceModel.Activities.Receive> 활동과 선택 **SendReply 만들기** 지난 후 붙여 <xref:System.Activities.Statements.WriteLine> 활동입니다.</span><span class="sxs-lookup"><span data-stu-id="e20ea-180">Right click the <xref:System.ServiceModel.Activities.Receive> activity and select **Create SendReply** and paste it after the last <xref:System.Activities.Statements.WriteLine> activity.</span></span> <span data-ttu-id="e20ea-181">클릭는 **정의...**  연결에 `SendReplyToReceive` 활동 다음과 같이 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e20ea-181">Click the **Define...** link in the `SendReplyToReceive` activity and make the following settings.</span></span>  
  
     <span data-ttu-id="e20ea-182">![회신 메시지 설정](../../../../docs/framework/wcf/feature-details/media/replymessagesettings.JPG "ReplyMessageSettings")</span><span class="sxs-lookup"><span data-stu-id="e20ea-182">![Reply message settings](../../../../docs/framework/wcf/feature-details/media/replymessagesettings.JPG "ReplyMessageSettings")</span></span>  
  
13. <span data-ttu-id="e20ea-183">끌어서 놓기는 <xref:System.Activities.Statements.WriteLine> 뒤로 `SendReplyToReceive` 활동 집합과 있기 <xref:System.Activities.Statements.WriteLine.Text%2A> 속성을 "Service: 보낸 회신 합니다."</span><span class="sxs-lookup"><span data-stu-id="e20ea-183">Drag and drop a <xref:System.Activities.Statements.WriteLine> activity after the `SendReplyToReceive` activity and set it’s <xref:System.Activities.Statements.WriteLine.Text%2A> property to "Service: Reply sent."</span></span>  
  
14. <span data-ttu-id="e20ea-184"><xref:System.Activities.Statements.WriteLine> 활동을 워크플로의 맨 아래로 끌어 놓고 해당 <xref:System.Activities.Statements.WriteLine.Text%2A> 속성을 "Service: Workflow ends, press ENTER to exit"로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="e20ea-184">Drag and drop a <xref:System.Activities.Statements.WriteLine> activity at the bottom of the workflow and set its <xref:System.Activities.Statements.WriteLine.Text%2A> property to "Service: Workflow ends, press ENTER to exit."</span></span>  
  
     <span data-ttu-id="e20ea-185">완료된 서비스 워크플로는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e20ea-185">The completed service workflow should look like this:</span></span>  
  
     <span data-ttu-id="e20ea-186">![전체 서비스 워크플로](../../../../docs/framework/wcf/feature-details/media/servicecomplete.jpg "ServiceComplete")</span><span class="sxs-lookup"><span data-stu-id="e20ea-186">![Complete Service Workflow](../../../../docs/framework/wcf/feature-details/media/servicecomplete.jpg "ServiceComplete")</span></span>  
  
### <a name="implement-the-workflow-client"></a><span data-ttu-id="e20ea-187">워크플로 클라이언트 구현</span><span class="sxs-lookup"><span data-stu-id="e20ea-187">Implement the workflow client</span></span>  
  
1.  <span data-ttu-id="e20ea-188">`WorkflowClient` 프로젝트에 `Common`라는 새 WCF 워크플로 응용 프로그램을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="e20ea-188">Add a new WCF Workflow application, called `WorkflowClient` to the `Common` project.</span></span> <span data-ttu-id="e20ea-189">마우스 오른쪽 단추로 클릭이 작업을 수행 하는 `Common` 프로젝트를 **추가**, **새 항목...** 선택, **워크플로** 아래 **설치 된 템플릿** 선택 **활동**합니다.</span><span class="sxs-lookup"><span data-stu-id="e20ea-189">To do this right click the `Common` project, select **Add**, **New Item ...**, Select **Workflow** under **Installed Templates** and select **Activity**.</span></span>  
  
     <span data-ttu-id="e20ea-190">![활동 프로젝트 추가](../../../../docs/framework/wcf/feature-details/media/addactivity.JPG "AddActivity")</span><span class="sxs-lookup"><span data-stu-id="e20ea-190">![Add an Activity project](../../../../docs/framework/wcf/feature-details/media/addactivity.JPG "AddActivity")</span></span>  
  
2.  <span data-ttu-id="e20ea-191">디자인 화면으로 <xref:System.Activities.Statements.Sequence> 활동을 끌어 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="e20ea-191">Drag and drop a <xref:System.Activities.Statements.Sequence> activity onto the design surface.</span></span>  
  
3.  <span data-ttu-id="e20ea-192"><xref:System.Activities.Statements.Sequence> 활동 내에 <xref:System.Activities.Statements.WriteLine> 활동을 끌어 놓고 해당 <xref:System.Activities.Statements.WriteLine.Text%2A> 속성을 `"Client: Workflow starting"`으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="e20ea-192">Within the <xref:System.Activities.Statements.Sequence> activity drag and drop a <xref:System.Activities.Statements.WriteLine> activity and set its <xref:System.Activities.Statements.WriteLine.Text%2A> property to `"Client: Workflow starting"`.</span></span> <span data-ttu-id="e20ea-193">이제 워크플로가 다음과 같이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="e20ea-193">The workflow should now look like this:</span></span>  
  
     <span data-ttu-id="e20ea-194">![WriteLine 활동 추가](../../../../docs/framework/wcf/feature-details/media/clientaddwriteline.JPG "ClientAddWriteLine")</span><span class="sxs-lookup"><span data-stu-id="e20ea-194">![Add a WriteLine activity](../../../../docs/framework/wcf/feature-details/media/clientaddwriteline.JPG "ClientAddWriteLine")</span></span>  
  
4.  <span data-ttu-id="e20ea-195"><xref:System.Activities.Statements.TransactionScope> 활동을 <xref:System.Activities.Statements.WriteLine> 활동 뒤로 끌어 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="e20ea-195">Drag and drop a <xref:System.Activities.Statements.TransactionScope> activity after the <xref:System.Activities.Statements.WriteLine> activity.</span></span>  <span data-ttu-id="e20ea-196"><xref:System.Activities.Statements.TransactionScope> 활동을 선택하고 변수 단추를 클릭한 후 다음 변수를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="e20ea-196">Select the <xref:System.Activities.Statements.TransactionScope> activity, click the Variables button and add the following variables.</span></span>  
  
     <span data-ttu-id="e20ea-197">![TransactionScope에 변수를 추가할](../../../../docs/framework/wcf/feature-details/media/tsvariables.JPG "TSVariables")</span><span class="sxs-lookup"><span data-stu-id="e20ea-197">![Add variables to the TransactionScope](../../../../docs/framework/wcf/feature-details/media/tsvariables.JPG "TSVariables")</span></span>  
  
5.  <span data-ttu-id="e20ea-198"><xref:System.Activities.Statements.Sequence> 활동을 <xref:System.Activities.Statements.TransactionScope> 활동의 본문으로 끌어 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="e20ea-198">Drag and drop a <xref:System.Activities.Statements.Sequence> activity into the body of the <xref:System.Activities.Statements.TransactionScope> activity.</span></span>  
  
6.  <span data-ttu-id="e20ea-199">`PrintTransactionInfo` 활동을 <xref:System.Activities.Statements.Sequence> 안으로 끌어 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="e20ea-199">Drag and drop a `PrintTransactionInfo` activity within the <xref:System.Activities.Statements.Sequence></span></span>  
  
7.  <span data-ttu-id="e20ea-200">끌어서 놓기는 <xref:System.Activities.Statements.WriteLine> 뒤로 `PrintTransactionInfo` 활동 집합과 해당 <xref:System.Activities.Statements.WriteLine.Text%2A> 속성을 "Client: Beginning Send"입니다.</span><span class="sxs-lookup"><span data-stu-id="e20ea-200">Drag and drop a <xref:System.Activities.Statements.WriteLine> activity after the `PrintTransactionInfo` activity and set its <xref:System.Activities.Statements.WriteLine.Text%2A> property to "Client: Beginning Send".</span></span> <span data-ttu-id="e20ea-201">이제 워크플로가 다음과 같이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="e20ea-201">The workflow should now look like this:</span></span>  
  
     <span data-ttu-id="e20ea-202">![활동 추가](../../../../docs/framework/wcf/feature-details/media/clientaddcbswriteline.JPG "ClientAddCBSWriteLine")</span><span class="sxs-lookup"><span data-stu-id="e20ea-202">![Adding activities](../../../../docs/framework/wcf/feature-details/media/clientaddcbswriteline.JPG "ClientAddCBSWriteLine")</span></span>  
  
8.  <span data-ttu-id="e20ea-203"><xref:System.ServiceModel.Activities.Send> 활동을 <xref:System.Activities.Statements.Assign> 활동 뒤로 끌어 놓고 다음 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="e20ea-203">Drag and drop a <xref:System.ServiceModel.Activities.Send> activity after the <xref:System.Activities.Statements.Assign> activity and set the following properties:</span></span>  
  
    |<span data-ttu-id="e20ea-204">속성</span><span class="sxs-lookup"><span data-stu-id="e20ea-204">Property</span></span>|<span data-ttu-id="e20ea-205">값</span><span class="sxs-lookup"><span data-stu-id="e20ea-205">Value</span></span>|  
    |--------------|-----------|  
    |<span data-ttu-id="e20ea-206">EndpointConfigurationName</span><span class="sxs-lookup"><span data-stu-id="e20ea-206">EndpointConfigurationName</span></span>|<span data-ttu-id="e20ea-207">workflowServiceEndpoint</span><span class="sxs-lookup"><span data-stu-id="e20ea-207">workflowServiceEndpoint</span></span>|  
    |<span data-ttu-id="e20ea-208">OperationName</span><span class="sxs-lookup"><span data-stu-id="e20ea-208">OperationName</span></span>|<span data-ttu-id="e20ea-209">StartSample</span><span class="sxs-lookup"><span data-stu-id="e20ea-209">StartSample</span></span>|  
    |<span data-ttu-id="e20ea-210">ServiceContractName</span><span class="sxs-lookup"><span data-stu-id="e20ea-210">ServiceContractName</span></span>|<span data-ttu-id="e20ea-211">ITransactionSample</span><span class="sxs-lookup"><span data-stu-id="e20ea-211">ITransactionSample</span></span>|  
  
     <span data-ttu-id="e20ea-212">이제 워크플로가 다음과 같이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="e20ea-212">The workflow should now look like this:</span></span>  
  
     <span data-ttu-id="e20ea-213">![Send 활동 속성 설정](../../../../docs/framework/wcf/feature-details/media/clientsendsettings.JPG "ClientSendSettings")</span><span class="sxs-lookup"><span data-stu-id="e20ea-213">![Setting the Send activity properties](../../../../docs/framework/wcf/feature-details/media/clientsendsettings.JPG "ClientSendSettings")</span></span>  
  
9. <span data-ttu-id="e20ea-214">클릭는 **정의...**  에 연결 하 고 다음과 같이 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e20ea-214">Click the **Define...** link and make the following settings:</span></span>  
  
     <span data-ttu-id="e20ea-215">![Send 활동 메시지 설정](../../../../docs/framework/wcf/feature-details/media/sendmessagesettings.JPG "SendMessageSettings")</span><span class="sxs-lookup"><span data-stu-id="e20ea-215">![Send activity message settings](../../../../docs/framework/wcf/feature-details/media/sendmessagesettings.JPG "SendMessageSettings")</span></span>  
  
10. <span data-ttu-id="e20ea-216">마우스 오른쪽 단추로 클릭는 <xref:System.ServiceModel.Activities.Send> 활동과 선택 **ReceiveReply 만들기**합니다.</span><span class="sxs-lookup"><span data-stu-id="e20ea-216">Right click the <xref:System.ServiceModel.Activities.Send> activity and select **Create ReceiveReply**.</span></span> <span data-ttu-id="e20ea-217"><xref:System.ServiceModel.Activities.ReceiveReply> 활동이 자동으로 <xref:System.ServiceModel.Activities.Send> 활동 뒤에 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="e20ea-217">The <xref:System.ServiceModel.Activities.ReceiveReply> activity will be automatically placed after the <xref:System.ServiceModel.Activities.Send> activity.</span></span>  
  
11. <span data-ttu-id="e20ea-218">ReceiveReplyForSend 활동의 정의... 링크를 클릭하고 다음과 같이 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="e20ea-218">Click the Define... link on the ReceiveReplyForSend activity and make the following settings:</span></span>  
  
     <span data-ttu-id="e20ea-219">![ReceiveForSend 메시지 설정 지정](../../../../docs/framework/wcf/feature-details/media/clientreplymessagesettings.JPG "ClientReplyMessageSettings")</span><span class="sxs-lookup"><span data-stu-id="e20ea-219">![Setting the ReceiveForSend message settings](../../../../docs/framework/wcf/feature-details/media/clientreplymessagesettings.JPG "ClientReplyMessageSettings")</span></span>  
  
12. <span data-ttu-id="e20ea-220"><xref:System.Activities.Statements.WriteLine> 활동을 <xref:System.ServiceModel.Activities.Send> 활동과 <xref:System.ServiceModel.Activities.ReceiveReply> 활동 사이로 끌어 놓고 해당 <xref:System.Activities.Statements.WriteLine.Text%2A> 속성을 "Client: Send complete"로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="e20ea-220">Drag and drop a <xref:System.Activities.Statements.WriteLine> activity between the <xref:System.ServiceModel.Activities.Send> and <xref:System.ServiceModel.Activities.ReceiveReply> activities and set its <xref:System.Activities.Statements.WriteLine.Text%2A> property to "Client: Send complete."</span></span>  
  
13. <span data-ttu-id="e20ea-221"><xref:System.Activities.Statements.WriteLine> 활동을 <xref:System.ServiceModel.Activities.ReceiveReply> 활동 뒤로 끌어 놓고 해당 <xref:System.Activities.Statements.WriteLine.Text%2A> 속성을 "Client side: Reply received = " + replyMessage로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="e20ea-221">Drag and drop a <xref:System.Activities.Statements.WriteLine> activity after the <xref:System.ServiceModel.Activities.ReceiveReply> activity and set its <xref:System.Activities.Statements.WriteLine.Text%2A> property to "Client side: Reply received = " + replyMessage</span></span>  
  
14. <span data-ttu-id="e20ea-222">`PrintTransactionInfo` 활동을 <xref:System.Activities.Statements.WriteLine> 활동 뒤로 끌어 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="e20ea-222">Drag and drop a `PrintTransactionInfo` activity after the <xref:System.Activities.Statements.WriteLine> activity.</span></span>  
  
15. <span data-ttu-id="e20ea-223"><xref:System.Activities.Statements.WriteLine> 활동을 워크플로 끝으로 끌어 놓고 해당 <xref:System.Activities.Statements.WriteLine.Text%2A> 속성을 "Client workflow ends"로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="e20ea-223">Drag and drop a <xref:System.Activities.Statements.WriteLine> activity at the end of the workflow and set its <xref:System.Activities.Statements.WriteLine.Text%2A> property to "Client workflow ends."</span></span> <span data-ttu-id="e20ea-224">완료된 클라이언트 워크플로는 다음 다이어그램과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e20ea-224">The completed client workflow should look like the following diagram.</span></span>  
  
     <span data-ttu-id="e20ea-225">![완료 된 클라이언트 워크플로](../../../../docs/framework/wcf/feature-details/media/clientcompleteworkflow.jpg "ClientCompleteWorkflow")</span><span class="sxs-lookup"><span data-stu-id="e20ea-225">![The completed client workfliow](../../../../docs/framework/wcf/feature-details/media/clientcompleteworkflow.jpg "ClientCompleteWorkflow")</span></span>  
  
16. <span data-ttu-id="e20ea-226">솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="e20ea-226">Build the solution.</span></span>  
  
### <a name="create-the-service-application"></a><span data-ttu-id="e20ea-227">서비스 응용 프로그램 만들기</span><span class="sxs-lookup"><span data-stu-id="e20ea-227">Create the Service application</span></span>  
  
1.  <span data-ttu-id="e20ea-228">솔루션에 `Service`라는 새 콘솔 응용 프로그램 프로젝트를 추가하고,</span><span class="sxs-lookup"><span data-stu-id="e20ea-228">Add a new Console Application project called `Service` to the solution.</span></span> <span data-ttu-id="e20ea-229">다음 어셈블리에 대한 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="e20ea-229">Add references to the following assemblies:</span></span>  
  
    1.  <span data-ttu-id="e20ea-230">System.Activities.dll</span><span class="sxs-lookup"><span data-stu-id="e20ea-230">System.Activities.dll</span></span>  
  
    2.  <span data-ttu-id="e20ea-231">System.ServiceModel.dll</span><span class="sxs-lookup"><span data-stu-id="e20ea-231">System.ServiceModel.dll</span></span>  
  
    3.  <span data-ttu-id="e20ea-232">System.ServiceModel.Activities.dll</span><span class="sxs-lookup"><span data-stu-id="e20ea-232">System.ServiceModel.Activities.dll</span></span>  
  
2.  <span data-ttu-id="e20ea-233">생성된 Program.cs 파일을 열고 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="e20ea-233">Open the generated Program.cs file and the following code:</span></span>  
  
    ```  
    static void Main()  
          {  
              Console.WriteLine("Building the server.");  
              using (WorkflowServiceHost host = new WorkflowServiceHost(new DeclarativeServiceWorkflow(), new Uri("net.tcp://localhost:8000/TransactedReceiveService/Declarative")))  
              {                
                  //Start the server  
                  host.Open();  
                  Console.WriteLine("Service started.");  
  
                  Console.WriteLine();  
                  Console.ReadLine();  
                  //Shutdown  
                  host.Close();  
              };         
          }  
    ```  
  
3.  <span data-ttu-id="e20ea-234">프로젝트에 다음 app.config 파일을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="e20ea-234">Add the following app.config file to the project.</span></span>  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8" ?>  
    <!-- Copyright © Microsoft Corporation.  All rights reserved. -->  
    <configuration>  
        <system.serviceModel>  
            <bindings>  
                <netTcpBinding>  
                    <binding transactionFlow="true" />  
                </netTcpBinding>  
            </bindings>  
        </system.serviceModel>  
    </configuration>  
    ```  
  
### <a name="create-the-client-application"></a><span data-ttu-id="e20ea-235">클라이언트 응용 프로그램 만들기</span><span class="sxs-lookup"><span data-stu-id="e20ea-235">Create the client application</span></span>  
  
1.  <span data-ttu-id="e20ea-236">솔루션에 `Client`라는 새 콘솔 응용 프로그램 프로젝트를 추가하고,</span><span class="sxs-lookup"><span data-stu-id="e20ea-236">Add a new Console Application project called `Client` to the solution.</span></span> <span data-ttu-id="e20ea-237">System.Activities.dll에 대한 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="e20ea-237">Add a reference to System.Activities.dll.</span></span>  
  
2.  <span data-ttu-id="e20ea-238">program.cs 파일을 열고 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="e20ea-238">Open the program.cs file and add the following code.</span></span>  
  
    ```  
    class Program  
        {  
  
            private static AutoResetEvent syncEvent = new AutoResetEvent(false);  
  
            static void Main(string[] args)  
            {  
                //Build client  
                Console.WriteLine("Building the client.");  
                WorkflowApplication client = new WorkflowApplication(new DeclarativeClientWorkflow());  
                client.Completed = Program.Completed;  
                client.Aborted = Program.Aborted;  
                client.OnUnhandledException = Program.OnUnhandledException;  
  
                //Wait for service to start  
                Console.WriteLine("Press ENTER once service is started.");  
                Console.ReadLine();  
  
                //Start the client              
                Console.WriteLine("Starting the client.");  
                client.Run();  
                syncEvent.WaitOne();  
  
                //Sample complete  
                Console.WriteLine();  
                Console.WriteLine("Client complete. Press ENTER to exit.");  
                Console.ReadLine();  
            }  
  
            private static void Completed(WorkflowApplicationCompletedEventArgs e)  
            {  
                Program.syncEvent.Set();  
            }  
  
            private static void Aborted(WorkflowApplicationAbortedEventArgs e)  
            {  
                Console.WriteLine("Client Aborted: {0}", e.Reason);  
                Program.syncEvent.Set();  
            }  
  
            private static UnhandledExceptionAction OnUnhandledException(WorkflowApplicationUnhandledExceptionEventArgs e)  
            {  
                Console.WriteLine("Client had an unhandled exception: {0}", e.UnhandledException);  
                return UnhandledExceptionAction.Cancel;  
            }  
        }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="e20ea-239">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e20ea-239">See Also</span></span>  
 [<span data-ttu-id="e20ea-240">워크플로 서비스</span><span class="sxs-lookup"><span data-stu-id="e20ea-240">Workflow Services</span></span>](../../../../docs/framework/wcf/feature-details/workflow-services.md)  
 [<span data-ttu-id="e20ea-241">Windows Communication Foundation 트랜잭션 개요</span><span class="sxs-lookup"><span data-stu-id="e20ea-241">Windows Communication Foundation Transactions Overview</span></span>](../../../../docs/framework/wcf/feature-details/transactions-overview.md)  
 [<span data-ttu-id="e20ea-242">TransactedReceiveScope 사용</span><span class="sxs-lookup"><span data-stu-id="e20ea-242">Use of TransactedReceiveScope</span></span>](../../../../docs/framework/windows-workflow-foundation/samples/use-of-transactedreceivescope.md)
