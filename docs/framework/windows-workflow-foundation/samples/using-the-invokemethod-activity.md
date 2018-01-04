---
title: "InvokeMethod 활동 사용"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b6643550-d043-4ac7-8069-9c55ebbb4233
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c5d3f6734f9d6a3b0e2279b2bb6cca71141c8f5f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="using-the-invokemethod-activity"></a><span data-ttu-id="ae726-102">InvokeMethod 활동 사용</span><span class="sxs-lookup"><span data-stu-id="ae726-102">Using the InvokeMethod Activity</span></span>
<span data-ttu-id="ae726-103">이 샘플에 사용 하는 방법을 보여 줍니다는 <!--zz <xref:System.Activities.Statements.InvokeMethod%601> --> [ <code>System.Activities.Statements.InvokeMethod\\`1</code> ](https://msdn.microsoft.com/library/dd647677.aspx) public 클래스의 공용 메서드를 호출 하는 활동입니다.</span><span class="sxs-lookup"><span data-stu-id="ae726-103">This sample demonstrates how to use the <!--zz <xref:System.Activities.Statements.InvokeMethod%601> -->[<code>System.Activities.Statements.InvokeMethod\\`1</code>](https://msdn.microsoft.com/library/dd647677.aspx) activity to invoke public methods in public classes.</span></span> <span data-ttu-id="ae726-104"><!--zz <xref:System.Activities.Statements.InvokeMethod%601> --> [ <code>System.Activities.Statements.InvokeMethod\\`1</code> ](https://msdn.microsoft.com/library/dd647677.aspx) 활동 하면 워크플로에서 개체에 대해 메서드를 호출, 매개 변수를 전달, 반환 값을 제네릭 메서드의 형식을 지정 하는 메서드는 동기적 있는지 여부를 지정 하거나 비동기입니다.</span><span class="sxs-lookup"><span data-stu-id="ae726-104">The <!--zz <xref:System.Activities.Statements.InvokeMethod%601> -->[<code>System.Activities.Statements.InvokeMethod\\`1</code>](https://msdn.microsoft.com/library/dd647677.aspx) activity allows a workflow to call methods against objects, pass in parameters, get the return value, specify types for generic methods, and specify whether the method is synchronous or asynchronous.</span></span> 
  
<span data-ttu-id="ae726-105">비 제네릭 버전의 <xref:System.Activities.Statements.InvokeMethod> 활동 경우 반환 값으로 설정 되어는 <xref:System.Activities.Statements.InvokeMethod.Result%2A> 속성과 제네릭 버전의는 <!--zz <xref:System.Activities.Statements.InvokeMethod%601> --> [ <code>System.Activities.Statements.InvokeMethod\`1</code> ](https://msdn.microsoft.com/library/dd647677.aspx) 반환 되는 반환 값 통해는 <!--zz <xref:System.Activities.Statements.InvokeMethod.Result%601.Result%2A> --> [ <code>System.Activities.Statements.InvokeMethod\`1.Result</code> ](https://msdn.microsoft.com/library/dd987724.aspx) 형식의 속성이 `TResult`합니다.</span><span class="sxs-lookup"><span data-stu-id="ae726-105">There is a non-generic version of the <xref:System.Activities.Statements.InvokeMethod> activity where the return value is set to the <xref:System.Activities.Statements.InvokeMethod.Result%2A> property and a generic version of the <!--zz <xref:System.Activities.Statements.InvokeMethod%601> -->[<code>System.Activities.Statements.InvokeMethod\`1</code>](https://msdn.microsoft.com/library/dd647677.aspx) activity where the return value is returned through the <!--zz <xref:System.Activities.Statements.InvokeMethod.Result%601.Result%2A> -->[<code>System.Activities.Statements.InvokeMethod\`1.Result</code>](https://msdn.microsoft.com/library/dd987724.aspx) property of type `TResult`.</span></span> 
  
 <span data-ttu-id="ae726-106">이 샘플에서는 다양한 메서드 형식을 호출하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ae726-106">This sample demonstrates how to call various method types.</span></span> <span data-ttu-id="ae726-107">다음 목록에는 이 샘플에서 보여 주는 메서드 형식이 자세히 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae726-107">The following list details the method types demonstrated in this sample:</span></span>  
  
-   <span data-ttu-id="ae726-108">매개 변수를 사용하지 않고 인스턴스 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="ae726-108">Invoke an instance method without parameters.</span></span>  
  
-   <span data-ttu-id="ae726-109">두 개의 매개 변수(System.String 및 System.Int32)를 사용하여 인스턴스 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="ae726-109">Invoke an instance method with two parameters (System.String and System.Int32).</span></span>  
  
-   <span data-ttu-id="ae726-110">두 개의 매개 변수(System.String 및 System.Int32)와 System.String[] 형식의 매개 변수 배열을 사용하여 인스턴스 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="ae726-110">Invoke an instance method with two parameters (System.String and System.Int32) and a parameter array of type System.String[].</span></span>  
  
-   <span data-ttu-id="ae726-111">두 개의 매개 변수(두 개의 System.Int32 숫자)와 System.Int32 형식의 결과를 사용하여 인스턴스 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="ae726-111">Invoke an instance method with two parameters (two System.Int32 numbers) and a result of type System.Int32.</span></span>  
  
     <span data-ttu-id="ae726-112">반환 값은 변수에 바인딩되고 <xref:System.Activities.Statements.WriteLine> 활동을 사용하여 콘솔에 출력됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae726-112">The return value is bound to a variable and printed to the console using the <xref:System.Activities.Statements.WriteLine> activity.</span></span>  
  
-   <span data-ttu-id="ae726-113">두 개의 매개 변수(System.String 및 System.Int32)를 사용하여 정적 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="ae726-113">Invoke a static method with two parameters (System.String and System.Int32).</span></span>  
  
-   <span data-ttu-id="ae726-114">제네릭 매개 변수 한 개(System.String)를 사용하여 인스턴스 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="ae726-114">Invoke an instance method with one generic parameter (System.String).</span></span>  
  
-   <span data-ttu-id="ae726-115">두 개의 제네릭 매개 변수(System.String 및 System.Int32)를 사용하여 정적 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="ae726-115">Invoke a static method with two generic parameters (System.String and System.Int32).</span></span>  
  
-   <span data-ttu-id="ae726-116">참조(System.String)로 전달되는 매개 변수 한 개가 있는 인스턴스 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="ae726-116">Invoke an instance method that has one parameter passed by reference (System.String).</span></span>  
  
     <span data-ttu-id="ae726-117">참조된 매개 변수는 변수에 바인딩되고 <xref:System.Activities.Statements.WriteLine> 활동을 사용하여 콘솔에 출력됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae726-117">The referenced parameter is bound to a variable and printed to the console using the <xref:System.Activities.Statements.WriteLine> activity.</span></span>  
  
-   <span data-ttu-id="ae726-118">비동기 인스턴스 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="ae726-118">Invoke an asynchronous instance method.</span></span>  
  
## <a name="to-use-this-sample"></a><span data-ttu-id="ae726-119">이 샘플을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="ae726-119">To use this sample</span></span>  
  
1.  <span data-ttu-id="ae726-120">[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]에서 InvokeMethodUsage.sln 솔루션 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="ae726-120">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the InvokeMethodUsage.sln solution file.</span></span>  
  
2.  <span data-ttu-id="ae726-121">Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="ae726-121">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="ae726-122">Ctrl+F5를 눌러 솔루션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ae726-122">To run the solution, press CTRL+F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ae726-123">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae726-123">The samples may already be installed on your machine.</span></span> <span data-ttu-id="ae726-124">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="ae726-124">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="ae726-125">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="ae726-125">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="ae726-126">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae726-126">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\InvokeMethod`