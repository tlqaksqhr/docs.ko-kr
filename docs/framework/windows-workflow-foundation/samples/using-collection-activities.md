---
title: 컬렉션 활동 사용
ms.date: 03/30/2017
ms.assetid: e1977cf8-1695-4071-b946-7046fe39601e
ms.openlocfilehash: 3c30a7fb46d9b155ec645a7b6845715d808d63b6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33516602"
---
# <a name="using-collection-activities"></a><span data-ttu-id="35926-102">컬렉션 활동 사용</span><span class="sxs-lookup"><span data-stu-id="35926-102">Using Collection Activities</span></span>
<span data-ttu-id="35926-103">이 샘플에서는 <xref:System.Activities.Statements.AddToCollection%601> 인터페이스를 구현하는 클래스를 사용하여 <xref:System.Activities.Statements.ClearCollection%601>, <xref:System.Activities.Statements.ExistsInCollection%601>, <xref:System.Activities.Statements.RemoveFromCollection%601> 및 <xref:System.Collections.ICollection> 컬렉션 활동을 사용하는 방법과 컬렉션을 반복하여 컬렉션의 각 요소 내용을 출력하는 사용자 지정 활동을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="35926-103">This sample demonstrates how to use the collection activities (<xref:System.Activities.Statements.AddToCollection%601>, <xref:System.Activities.Statements.ClearCollection%601>, <xref:System.Activities.Statements.ExistsInCollection%601>, and <xref:System.Activities.Statements.RemoveFromCollection%601>) with a class that implements the <xref:System.Collections.ICollection> interface and how to create a custom activity that iterates over a collection to print out the contents of each element in the collection.</span></span> <span data-ttu-id="35926-104">`PrintCollection`이라는 사용자 지정 활동은 `Numbers`라는 컬렉션의 항목 멤버를 콘솔에 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="35926-104">The custom activity, which is named `PrintCollection`, prints to the console the item members of a collection named `Numbers`.</span></span>  
  
 <span data-ttu-id="35926-105">다음 표에서는 워크플로에 대한 컬렉션 조작 기능을 제공하는 네 가지 활동을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="35926-105">The following table describes the four activities that provide collection manipulation for workflows.</span></span>  
  
|<span data-ttu-id="35926-106">활동 이름</span><span class="sxs-lookup"><span data-stu-id="35926-106">Activity name</span></span>|<span data-ttu-id="35926-107">설명</span><span class="sxs-lookup"><span data-stu-id="35926-107">Description</span></span>|  
|-------------------|-----------------|  
|<xref:System.Activities.Statements.AddToCollection%601>|<span data-ttu-id="35926-108">컬렉션에 항목을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="35926-108">Adds an item to a collection.</span></span>|  
|<xref:System.Activities.Statements.ClearCollection%601>|<span data-ttu-id="35926-109">컬렉션에서 모든 항목을 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="35926-109">Clears all items in a collection</span></span>|  
|<xref:System.Activities.Statements.ExistsInCollection%601>|<span data-ttu-id="35926-110">지정된 항목이 컬렉션에 있는 경우 `true`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="35926-110">Returns `true` if specified item exists in collection.</span></span>|  
|<xref:System.Activities.Statements.RemoveFromCollection%601>|<span data-ttu-id="35926-111">컬렉션에서 항목을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="35926-111">Removes an item from a collection.</span></span>|  
  
 <span data-ttu-id="35926-112">이 샘플은 두 개의 솔루션으로 구성되어 있습니다. 그 중 하나는 CodedWorkflow 디렉터리에 있고, 다른 하나는 DesignerWorkflow 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35926-112">The sample consists of two solutions, one under the CodedWorkflow directory and the other under the DesignerWorkflow directory.</span></span> <span data-ttu-id="35926-113">이들 솔루션은 동일한 용도로 활동을 사용하는 서로 다른 두 가지 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="35926-113">They demonstrate two different ways of using the activities for the same purposes.</span></span>  
  
|<span data-ttu-id="35926-114">솔루션</span><span class="sxs-lookup"><span data-stu-id="35926-114">Solution</span></span>|<span data-ttu-id="35926-115">설명</span><span class="sxs-lookup"><span data-stu-id="35926-115">Description</span></span>|<span data-ttu-id="35926-116">기본 파일</span><span class="sxs-lookup"><span data-stu-id="35926-116">Main Files</span></span>|  
|-|-|-|  
|<span data-ttu-id="35926-117">CodedWorkflow</span><span class="sxs-lookup"><span data-stu-id="35926-117">CodedWorkflow</span></span>|<span data-ttu-id="35926-118">컬렉션 활동을 프로그래밍 방식으로 호출하는 방법을 보여 주는 샘플 클라이언트 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="35926-118">Sample client application that demonstrates how to invoke the collection activities programmatically.</span></span>|<span data-ttu-id="35926-119">**PrintCollection.cs**: 콘솔에 컬렉션의 모든 항목이 인쇄 하는 도우미 활동입니다.</span><span class="sxs-lookup"><span data-stu-id="35926-119">**PrintCollection.cs**: helper activity to print out to the console every item in a collection.</span></span><br /><br /> <span data-ttu-id="35926-120">**Program.cs**: 프로그래밍 방식으로 일련의 컬렉션 활동이 포함 되 고이 실행 하는 시퀀스 활동을 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="35926-120">**Program.cs**: programmatically builds a sequence activity that contains a series of collection activities, and executes it.</span></span>|  
|<span data-ttu-id="35926-121">DesignerWorkflow</span><span class="sxs-lookup"><span data-stu-id="35926-121">DesignerWorkflow</span></span>|<span data-ttu-id="35926-122">컬렉션 활동을 워크플로 디자이너에서 선언적으로 사용하는 방법을 보여 주는 샘플 클라이언트 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="35926-122">Sample client application that demonstrates how to use the collection activities declaratively in the workflow designer.</span></span>|<span data-ttu-id="35926-123">**CollectionWorkflow.xaml**: 컬렉션 활동을 사용 하는 디자이너를 통해 선언적으로 만든 워크플로입니다.</span><span class="sxs-lookup"><span data-stu-id="35926-123">**CollectionWorkflow.xaml**: a workflow created declaratively with the designer that uses the collection activities.</span></span><br /><br /> <span data-ttu-id="35926-124">**PrintCollection.cs**: 콘솔에 컬렉션의 모든 항목이 인쇄 하는 도우미 활동입니다.</span><span class="sxs-lookup"><span data-stu-id="35926-124">**PrintCollection.cs**: helper activity to print out to the console every item in a collection.</span></span><br /><br /> <span data-ttu-id="35926-125">**Program.cs**: CollectionWorkflow.xaml에서 설명 하는 워크플로 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="35926-125">**Program.cs**: invokes the workflow described in CollectionWorkflow.xaml.</span></span>|  
  
 <span data-ttu-id="35926-126">이 데모에서는 `Numbers`이라는 사용자 정의된 활동을 통해 `PrintCollection` 컬렉션의 항목 멤버가 콘솔에 출력됩니다.</span><span class="sxs-lookup"><span data-stu-id="35926-126">In the demonstration, the item members of collection `Numbers` are printed on the console using a custom-defined activity called `PrintCollection`.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="35926-127">이 샘플을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="35926-127">To use this sample</span></span>  
  
1.  <span data-ttu-id="35926-128">[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]에서 Collection.sln 솔루션 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="35926-128">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the Collection.sln solution file.</span></span>  
  
2.  <span data-ttu-id="35926-129">Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="35926-129">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="35926-130">Ctrl+F5를 눌러 솔루션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="35926-130">To run the solution, press CTRL+F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="35926-131">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35926-131">The samples may already be installed on your machine.</span></span> <span data-ttu-id="35926-132">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="35926-132">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="35926-133">이 디렉터리가로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4에 대 한 Windows WF (Workflow Foundation) 샘플](http://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플.</span><span class="sxs-lookup"><span data-stu-id="35926-133">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="35926-134">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35926-134">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\Collection`