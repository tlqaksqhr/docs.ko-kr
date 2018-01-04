---
title: "LINQ to Objects 활동"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 403c82e8-7f2b-42f6-93cd-95c35bc76ead
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ff77211000cfdda9c35e5a0dcbc69fc0eaf5c3be
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="linq-to-objects-activity"></a><span data-ttu-id="5def5-102">LINQ to Objects 활동</span><span class="sxs-lookup"><span data-stu-id="5def5-102">LINQ to Objects Activity</span></span>
<span data-ttu-id="5def5-103">이 샘플에서는 LINQ to Objects를 사용하여 컬렉션의 요소를 쿼리하는 활동을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5def5-103">This sample demonstrates how to create an activity to use LINQ to Objects to query elements in a collection.</span></span>  
  
## <a name="activity-details-for-findincollection"></a><span data-ttu-id="5def5-104">FindInCollection의 활동 세부 정보</span><span class="sxs-lookup"><span data-stu-id="5def5-104">Activity Details for FindInCollection</span></span>  
 <span data-ttu-id="5def5-105">이 활동을 사용하면 사용자가 LINQ to Objects를 사용하여 메모리에 있는 컬렉션의 요소를 쿼리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5def5-105">This activity allows users to query elements from collections in memory using LINQ to Objects.</span></span> <span data-ttu-id="5def5-106">결과를 필터링하려면 람다 식 형식의 LINQ 조건자를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5def5-106">You must provide a LINQ predicate in the form of a lambda expression to filter the results.</span></span> <span data-ttu-id="5def5-107">이 활동은 <xref:System.Activities.Statements.AddToCollection%601> 활동과 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5def5-107">This activity can be used in conjunction with <xref:System.Activities.Statements.AddToCollection%601> activities.</span></span>  
  
 <span data-ttu-id="5def5-108">다음 표에서는 활동의 속성 및 반환 값에 대해 자세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5def5-108">The following table details the property and return values for the activity.</span></span>  
  
|<span data-ttu-id="5def5-109">속성 또는 반환 값</span><span class="sxs-lookup"><span data-stu-id="5def5-109">Property or Return Value</span></span>|<span data-ttu-id="5def5-110">설명</span><span class="sxs-lookup"><span data-stu-id="5def5-110">Description</span></span>|  
|------------------------------|-----------------|  
|<span data-ttu-id="5def5-111">`Collection` 속성</span><span class="sxs-lookup"><span data-stu-id="5def5-111">`Collection` property</span></span>|<span data-ttu-id="5def5-112">소스 컬렉션을 지정하는 필수 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="5def5-112">A required property that specifies the source collection.</span></span>|  
|<span data-ttu-id="5def5-113">`Predicate` 속성</span><span class="sxs-lookup"><span data-stu-id="5def5-113">`Predicate` property</span></span>|<span data-ttu-id="5def5-114">람다 식 형식으로 컬렉션의 필터를 지정하는 필수 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="5def5-114">A required property that specifies the filter for the collection in the form of a lambda expression.</span></span>|  
|<span data-ttu-id="5def5-115">반환 값</span><span class="sxs-lookup"><span data-stu-id="5def5-115">Return Value</span></span>|<span data-ttu-id="5def5-116">필터링된 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="5def5-116">The filtered collection.</span></span>|  
  
## <a name="code-sample-that-uses-the-custom-activity"></a><span data-ttu-id="5def5-117">사용자 지정 활동을 사용하는 코드 샘플</span><span class="sxs-lookup"><span data-stu-id="5def5-117">Code Sample that uses the Custom Activity</span></span>  
 <span data-ttu-id="5def5-118">다음 코드 예제에서는 `FindInCollection` 사용자 지정 활동을 사용하여 직원 컬렉션에서 `Role` 속성이 `Manager`로 설정되고 `Location` 속성이 `Redmond`로 설정된 모든 행을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="5def5-118">The following code example uses the `FindInCollection` custom activity to find all rows in a collection of employees that have a `Role` property set to `Manager` and the `Location` property set to `Redmond`.</span></span>  
  
```csharp  
// Find all program managers in Redmond in the employees collection.  
  
Activity wf = new FindInCollection<Employee>  
{  
    Collections = new LambdaValue<IEnumerable<Employee>>(c => employees),                
    Predicate = new LambdaValue<Func<Employee, bool>>(c => new Func<Employee, bool>(e => e.Role.Equals("Manager") && e.Location.Equals("Redmond")))  
};  
```  
  
 <span data-ttu-id="5def5-119">다음 코드에서는 사용자 지정 FindInCollection 활동, <xref:System.Activities.Statements.AddToCollection%601> 및 <xref:System.Activities.Statements.ForEach%601> 활동을 사용하여 컬렉션을 직원으로 채우고, 레드먼드에 있으면서 개발자 역할을 가진 모든 직원을 찾은 다음, 결과 목록을 반복하는 워크플로 프로그램을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5def5-119">The following code shows how to create a workflow program that uses the custom FindInCollection activity, <xref:System.Activities.Statements.AddToCollection%601>, and <xref:System.Activities.Statements.ForEach%601> activities to populate a collection with employees, find all the employees that have developer roles and are located in Redmond, and then iterate through the resulting list.</span></span>  
  
```csharp  
// Create the Linq predicate for the find expression  
  
Func<Employee, bool> predicate = e => e.Role == "DEV" && e.Location.Equals("Redmond");  
  
// Create workflow program  
Activity sampleWorkflow = new Sequence  
{  
    Variables = { employees, devsFromRedmond },  
    Activities =  
    {  
        new Assign<IList<Employee>>  
        {  
            To = employees,  
            Value = new LambdaValue<IList<Employee>>(c => new List<Employee>())  
        },  
        new AddToCollection<Employee>  
        {  
            Collection = new InArgument<ICollection<Employee>>(employees),  
            Item =  new LambdaValue<Employee>(c => new Employee(1, "Employee 1", "DEV", "Redmond"))  
        },  
        new AddToCollection<Employee>  
        {  
            Collection = new InArgument<ICollection<Employee>>(employees),  
            Item =  new LambdaValue<Employee>(c => new Employee(2, "Employee 2", "DEV", "Redmond"))  
        },  
        new AddToCollection<Employee>  
        {  
            Collection = new InArgument<ICollection<Employee>>(employees),  
            Item =  new LambdaValue<Employee>(c => new Employee(3, "Employee 3", "PM", "Redmond"))  
        },  
        new AddToCollection<Employee>  
        {  
            Collection = new InArgument<ICollection<Employee>>(employees),  
            Item =  new LambdaValue<Employee>(c => new Employee(4, "Employee 4", "PM", "China"))  
        },  
        new FindInCollection<Employee>  
        {  
            Collections = new InArgument<IEnumerable<Employee>>(employees),  
            Predicate = new LambdaValue<Func<Employee, bool>>(c => predicate),  
            Result = new OutArgument<IList<Employee>>(devsFromRedmond)  
        },  
        new ForEach<Employee>  
        {  
            Values = new InArgument<IEnumerable<Employee>>(devsFromRedmond),  
            Body = new ActivityAction<Employee>  
            {  
                Argument = iterationVariable,  
                Handler = new WriteLine  
                {  
                    Text = new InArgument<string>(env => iterationVariable.Get(env).ToString())  
                }  
            }  
        }  
    }  
};  
```  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="5def5-120">이 샘플을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="5def5-120">To use this sample</span></span>  
  
1.  <span data-ttu-id="5def5-121">[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]을 사용하여 LinqToObjects.sln 솔루션 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="5def5-121">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the LinqToObjects.sln solution file.</span></span>  
  
2.  <span data-ttu-id="5def5-122">Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="5def5-122">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="5def5-123">F5 키를 눌러 솔루션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="5def5-123">To run the solution, press F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="5def5-124">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5def5-124">The samples may already be installed on your machine.</span></span> <span data-ttu-id="5def5-125">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="5def5-125">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="5def5-126">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="5def5-126">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="5def5-127">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5def5-127">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\Linq\LinqToObjects`  
  
## <a name="see-also"></a><span data-ttu-id="5def5-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5def5-128">See Also</span></span>  
 [<span data-ttu-id="5def5-129">람다 식 (C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="5def5-129">Lambda Expressions (C# Programming Guide)</span></span>](http://go.microsoft.com/fwlink/?LinkId=150381)  
 [<span data-ttu-id="5def5-130">LINQ to Objects</span><span class="sxs-lookup"><span data-stu-id="5def5-130">LINQ to Objects</span></span>](http://go.microsoft.com/fwlink/?LinkID=150380)
