---
title: Using the WorkflowInvoker Class
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0a966164-3990-4e78-8aa2-c6797ebbee94
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 8bb6c4049b56702c8fad226c20884ff581ec6203
ms.sourcegitcommit: 5177d6ae2e9baf026f07ee0631556700a5a193f7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2017
---
# <a name="using-the-workflowinvoker-class"></a><span data-ttu-id="0564c-102">Using the WorkflowInvoker Class</span><span class="sxs-lookup"><span data-stu-id="0564c-102">Using the WorkflowInvoker Class</span></span>
<span data-ttu-id="0564c-103">이 샘플에서는 <xref:System.Activities.WorkflowInvoker> 클래스를 사용하여 활동을 마치 메서드처럼 호출하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0564c-103">This sample demonstrates how to use the <xref:System.Activities.WorkflowInvoker> class to invoke an activity as if it were a method.</span></span>  
  
## <a name="sample-details"></a><span data-ttu-id="0564c-104">샘플 세부 정보</span><span class="sxs-lookup"><span data-stu-id="0564c-104">Sample Details</span></span>  
 <span data-ttu-id="0564c-105"><xref:System.Activities.WorkflowInvoker> 클래스를 사용하면 활동을 매우 간단하게 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0564c-105">Using the <xref:System.Activities.WorkflowInvoker> class is the simplest way to execute an activity.</span></span> <span data-ttu-id="0564c-106">이 클래스는 활동을 마치 메서드 호출과 같이 직접 실행하기 위한 것으로,</span><span class="sxs-lookup"><span data-stu-id="0564c-106">It is designed for directly running an activity as if it were a method call.</span></span> <span data-ttu-id="0564c-107">활동을 실행하는 데 다른 호스팅 변형에서 제공하는 컨트롤 인프라가 필요하지 않은 경우에 사용할 수 있는 간단하면서도 성능이 우수하고 사용하기 쉬운 API입니다.</span><span class="sxs-lookup"><span data-stu-id="0564c-107">It is a lightweight, high-performing, easy to use API for use in scenarios where an activity’s execution does not require the control infrastructure provided by other hosting variations.</span></span>  
  
 <span data-ttu-id="0564c-108">파생 되는 사용자 지정 활동을 사용 하 여 샘플 <xref:System.Activities.CodeActivity%601>< Int32\> 라는 `Add` 두 개를 추가 하는 <xref:System.Activities.InArgument%601>, `X` 및 `Y`, 반환 하 고는 `Result` <xref:System.Activities.OutArgument%601>합니다.</span><span class="sxs-lookup"><span data-stu-id="0564c-108">The sample uses a custom activity that derives from <xref:System.Activities.CodeActivity%601><Int32\> named `Add` that adds two <xref:System.Activities.InArgument%601>, `X` and `Y`, and returns a `Result`<xref:System.Activities.OutArgument%601>.</span></span> <span data-ttu-id="0564c-109">(<xref:System.Activities.CodeActivity%601>\<T >에서 파생 <xref:System.Activities.Activity%601>< T\>을는 <xref:System.Activities.OutArgument%601> \<T > 명명 된 `Result`.) A `Dictionary` \<문자열, 개체 >를 통해 호출 되는 활동에 인수를 전달 하는 데 사용 <xref:System.Activities.WorkflowInvoker>합니다.</span><span class="sxs-lookup"><span data-stu-id="0564c-109">(<xref:System.Activities.CodeActivity%601>\<T> derives from <xref:System.Activities.Activity%601><T\>, which has an <xref:System.Activities.OutArgument%601>\<T> named `Result`.) A `Dictionary`\<string, object> is used to pass arguments into an activity being invoked through <xref:System.Activities.WorkflowInvoker>.</span></span> <span data-ttu-id="0564c-110">사전의 키는 호출되는 활동의 인수 이름에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="0564c-110">The key of the dictionary corresponds to the name of an argument on the invoked activity.</span></span> <span data-ttu-id="0564c-111">특정 키와 연결된 값은 키가 식별하는 인수에 바인딩됩니다.</span><span class="sxs-lookup"><span data-stu-id="0564c-111">The value associated with a particular key is bound to the argument identified by the key.</span></span>  
  
 <span data-ttu-id="0564c-112">이 샘플에서는 <xref:System.Activities.WorkflowInvoker.Invoke%2A>를 호출하고 `X` 및 `Y`의 값이 들어 있는 사전을 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="0564c-112">The sample calls <xref:System.Activities.WorkflowInvoker.Invoke%2A> and passes a dictionary that contains values for `X` and `Y`.</span></span> <span data-ttu-id="0564c-113"><xref:System.Activities.WorkflowInvoker> 클래스는 이러한 값을 `Add` 활동의 인수에 바인딩하고 활동을 실행한 다음 결과를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="0564c-113">The <xref:System.Activities.WorkflowInvoker> class binds these values to the `Add` activity’s arguments, executes the activity, and returns the result.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="0564c-114">이 샘플을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="0564c-114">To use this sample</span></span>  
  
1.  <span data-ttu-id="0564c-115">[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]에서 Invoker.sln 솔루션 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="0564c-115">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the Invoker.sln solution file.</span></span>  
  
2.  <span data-ttu-id="0564c-116">Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="0564c-116">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="0564c-117">F5 키를 눌러 솔루션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="0564c-117">To run the solution, press F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="0564c-118">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0564c-118">The samples may already be installed on your machine.</span></span> <span data-ttu-id="0564c-119">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="0564c-119">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="0564c-120">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="0564c-120">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="0564c-121">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0564c-121">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Execution\WorkflowInvoker`