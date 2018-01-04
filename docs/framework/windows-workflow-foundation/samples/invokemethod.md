---
title: InvokeMethod
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 04988eb3-65f8-456d-b1bd-509f5d05a57c
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b90ebec929b310442cde2be8d96386e016a9bbb4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="invokemethod"></a><span data-ttu-id="4c13a-102">InvokeMethod</span><span class="sxs-lookup"><span data-stu-id="4c13a-102">InvokeMethod</span></span>
<span data-ttu-id="4c13a-103">이 샘플에서는 <xref:System.Activities.Statements.InvokeMethod> 활동을 사용하여 클래스의 메서드를 호출하는 여러 가지 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4c13a-103">This sample shows the different ways of using the <xref:System.Activities.Statements.InvokeMethod> activity to invoke methods of a class.</span></span>  
  
 <span data-ttu-id="4c13a-104">메서드는 클래스에 속하며 클래스에 포함된 작업 집합을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4c13a-104">A method belongs to a class and represents a contained set of operations.</span></span> <span data-ttu-id="4c13a-105"><xref:System.Activities.Statements.InvokeMethod> 활동을 사용하면 개체 또는 형식에 대해 메서드를 호출하고, 매개 변수를 전달하고, 반환 값을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c13a-105">The <xref:System.Activities.Statements.InvokeMethod> activity gives you the ability to call methods against objects or types, pass in parameters, and get the return value.</span></span> <span data-ttu-id="4c13a-106">메서드는 동기적으로 또는 비동기적으로 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c13a-106">Methods can be invoked synchronously or asynchronously.</span></span>  
  
## <a name="sample-details"></a><span data-ttu-id="4c13a-107">샘플 세부 정보</span><span class="sxs-lookup"><span data-stu-id="4c13a-107">Sample Details</span></span>  
 <span data-ttu-id="4c13a-108">이 샘플에서는 <xref:System.Activities.Statements.InvokeMethod> 활동을 사용하여 다음과 같은 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="4c13a-108">This sample uses the <xref:System.Activities.Statements.InvokeMethod> activity to perform the following scenarios:</span></span>  
  
1.  <span data-ttu-id="4c13a-109">매개 변수를 사용하지 않고 인스턴스 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="4c13a-109">Invoke an instance method without parameters.</span></span>  
  
2.  <span data-ttu-id="4c13a-110">두 개의 매개 변수(<xref:System.String> 및 <xref:System.Int32>)를 사용하여 인스턴스 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="4c13a-110">Invoke an instance method with two parameters (<xref:System.String> and <xref:System.Int32>).</span></span>  
  
3.  <span data-ttu-id="4c13a-111">두 개의 매개 변수(<xref:System.String> 및 <xref:System.Int32>)와 <xref:System.String>[] 형식의 매개 변수 배열을 사용하여 인스턴스 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="4c13a-111">Invoke an instance method with two parameters (<xref:System.String> and <xref:System.Int32>) and a parameter array of type <xref:System.String>[].</span></span>  
  
4.  <span data-ttu-id="4c13a-112"><xref:System.Int32> 형식의 두 매개 변수와 <xref:System.Int32> 형식의 결과를 사용하여 인스턴스 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="4c13a-112">Invoke an instance method with two parameters of type <xref:System.Int32> and a result of type <xref:System.Int32>.</span></span> <span data-ttu-id="4c13a-113">이 경우 결과 값은 변수에 바인딩되어 다른 활동에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c13a-113">In this scenario, the result value is bound to a variable and used in another activity.</span></span> <span data-ttu-id="4c13a-114">이 결과 값은 <xref:System.Activities.Statements.WriteLine> 활동을 사용하여 콘솔에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c13a-114">It is displayed in the console using the <xref:System.Activities.Statements.WriteLine> activity.</span></span>  
  
5.  <span data-ttu-id="4c13a-115"><xref:System.String> 및 <xref:System.Int32> 형식의 두 매개 변수를 사용하여 정적 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="4c13a-115">Invoke a static method with two parameters of type <xref:System.String> and <xref:System.Int32>.</span></span>  
  
6.  <span data-ttu-id="4c13a-116"><xref:System.String> 형식의 제네릭 매개 변수 하나를 사용하여 인스턴스 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="4c13a-116">Invoke an instance method with one generic parameter of type <xref:System.String>.</span></span>  
  
7.  <span data-ttu-id="4c13a-117"><xref:System.String> 및 <xref:System.Int32> 형식의 두 제네릭 매개 변수를 사용하여 정적 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="4c13a-117">Invoke a static method with two generic parameters of type <xref:System.String> and <xref:System.Int32>.</span></span>  
  
8.  <span data-ttu-id="4c13a-118"><xref:System.String> 형식의 참조로 전달되는 매개 변수 하나가 있는 인스턴스 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="4c13a-118">Invoke an instance method that has one parameter passed by reference of type <xref:System.String>.</span></span> <span data-ttu-id="4c13a-119">이 경우 참조 매개 변수는 변수 `outParam`에 바인딩되어 다른 활동에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c13a-119">In this scenario, the reference parameter is bound to a variable (`outParam`) and used in another activity.</span></span> <span data-ttu-id="4c13a-120">이 결과 값은 <xref:System.Activities.Statements.WriteLine> 활동을 사용하여 콘솔에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c13a-120">It is displayed on the console using the <xref:System.Activities.Statements.WriteLine> activity.</span></span>  
  
9. <span data-ttu-id="4c13a-121">비동기 인스턴스 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="4c13a-121">Invoke an asynchronous instance method.</span></span>  
  
10. <span data-ttu-id="4c13a-122">두 개의 <xref:System.Activities.Statements.InvokeMethod> 활동을 사용하여 동일한 개체 인스턴스에 대해 두 개의 서로 다른 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="4c13a-122">Invoke two different methods on the same instance of an object using two <xref:System.Activities.Statements.InvokeMethod> activities.</span></span>  
  
11. <span data-ttu-id="4c13a-123">개체 인스턴스에 값을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="4c13a-123">Store a value in an instance of an object.</span></span>  
  
12. <span data-ttu-id="4c13a-124">개체 인스턴스에서 값을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="4c13a-124">Retrieve a value from an instance of an object.</span></span>  
  
## <a name="to-use-this-sample"></a><span data-ttu-id="4c13a-125">이 샘플을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="4c13a-125">To use this sample</span></span>  
 <span data-ttu-id="4c13a-126">이 샘플은 두 가지 버전으로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c13a-126">This sample is provided in two versions.</span></span> <span data-ttu-id="4c13a-127">CodedWorkflow\CS 폴더에 있는 이 샘플의 첫 번째 버전에서는 <xref:System.Activities.Statements.InvokeMethod> 프로그래밍 모델을 사용하는 C# 코드를 통해 [!INCLUDE[wf](../../../../includes/wf-md.md)]를 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4c13a-127">The first version of this sample demonstrates the usage of <xref:System.Activities.Statements.InvokeMethod> through C# code using the [!INCLUDE[wf](../../../../includes/wf-md.md)] programming model and can be found under the CodedWorkflow\CS folder.</span></span> <span data-ttu-id="4c13a-128">DesignerWorkflow\CS 폴더에 있는 두 번째 버전에서는 XAML을 통해 <xref:System.Activities.Statements.InvokeMethod>를 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4c13a-128">The second version demonstrates the usage of <xref:System.Activities.Statements.InvokeMethod> using XAML and can be found under the DesignerWorkflow\CS folder.</span></span>  
  
#### <a name="to-run-the-coded-workflow-sample"></a><span data-ttu-id="4c13a-129">코딩된 워크플로 샘플을 실행하려면</span><span class="sxs-lookup"><span data-stu-id="4c13a-129">To run the coded workflow sample</span></span>  
  
1.  <span data-ttu-id="4c13a-130">[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]에서 CodedWorkflow\CS 폴더에 있는 InvokeMethodUsage.sln 솔루션 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="4c13a-130">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the InvokeMethodUsage.sln solution file in the CodedWorkflow\CS folder.</span></span>  
  
2.  <span data-ttu-id="4c13a-131">Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="4c13a-131">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="4c13a-132">Ctrl+F5를 눌러 솔루션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="4c13a-132">To run the solution, press CTRL+F5.</span></span>  
  
#### <a name="to-run-the-designer-workflow-sample"></a><span data-ttu-id="4c13a-133">디자이너 워크플로 샘플을 실행하려면</span><span class="sxs-lookup"><span data-stu-id="4c13a-133">To run the designer workflow sample</span></span>  
  
1.  <span data-ttu-id="4c13a-134">[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]에서 DesignerWorkflow\CS 폴더에 있는 InvokeMethodUsage.sln 솔루션 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="4c13a-134">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the InvokeMethodUsage.sln solution file in the DesignerWorkflow\CS folder.</span></span>  
  
2.  <span data-ttu-id="4c13a-135">Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="4c13a-135">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="4c13a-136">Ctrl+F5를 눌러 솔루션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="4c13a-136">To run the solution, press CTRL+F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="4c13a-137">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c13a-137">The samples may already be installed on your machine.</span></span> <span data-ttu-id="4c13a-138">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="4c13a-138">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="4c13a-139">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="4c13a-139">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="4c13a-140">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c13a-140">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\InvokeMethod`