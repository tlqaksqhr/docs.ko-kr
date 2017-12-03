---
title: Programming Model Item Tree
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0229efde-19ac-4bdc-a187-c6227a7bd1a5
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: fc58f5d91618c8b4caa97da12b7b0e20e007448c
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="programming-model-item-tree"></a><span data-ttu-id="c3771-102">Programming Model Item Tree</span><span class="sxs-lookup"><span data-stu-id="c3771-102">Programming Model Item Tree</span></span>
<span data-ttu-id="c3771-103">이 샘플에서는 <xref:System.Activities.Presentation.Model.ModelItem> 트리 뷰에서 선언적 데이터 바인딩을 사용하여 [!INCLUDE[avalon1](../../../../includes/avalon1-md.md)]을 탐색하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c3771-103">This sample demonstrates how to navigate the <xref:System.Activities.Presentation.Model.ModelItem> tree using declarative data binding from the [!INCLUDE[avalon1](../../../../includes/avalon1-md.md)] Tree View.</span></span>  
  
## <a name="sample-details"></a><span data-ttu-id="c3771-104">샘플 세부 정보</span><span class="sxs-lookup"><span data-stu-id="c3771-104">Sample Details</span></span>  
 <span data-ttu-id="c3771-105"><xref:System.Activities.Presentation.Model.ModelItem> 트리는 [!INCLUDE[wfd1](../../../../includes/wfd1-md.md)] 인프라에서 편집할 기본 인스턴스에 대한 데이터를 노출하는 데 사용되는 추상화입니다.</span><span class="sxs-lookup"><span data-stu-id="c3771-105">The <xref:System.Activities.Presentation.Model.ModelItem> tree is the abstraction that is used by the [!INCLUDE[wfd1](../../../../includes/wfd1-md.md)] infrastructure to expose the data about the underlying instance being edited.</span></span> <span data-ttu-id="c3771-106">다음 그림에서는 [!INCLUDE[wfd2](../../../../includes/wfd2-md.md)] 내의 다양한 인프라 계층을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c3771-106">The following illustration is a depiction of the various layers of infrastructure within the [!INCLUDE[wfd2](../../../../includes/wfd2-md.md)].</span></span>  
  
 <span data-ttu-id="c3771-107">![Workflow Designer 아키텍처](../../../../docs/framework/windows-workflow-foundation/samples/media/workflowdesignerarch.JPG "WorkflowDesignerArch")</span><span class="sxs-lookup"><span data-stu-id="c3771-107">![Workflow Designer Architecture](../../../../docs/framework/windows-workflow-foundation/samples/media/workflowdesignerarch.JPG "WorkflowDesignerArch")</span></span>  
  
 <span data-ttu-id="c3771-108"><xref:System.Activities.Presentation.Model.ModelItem>은 내부 값에 대한 포인터와 <xref:System.Activities.Presentation.Model.ModelProperty> 개체의 컬렉션으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="c3771-108">A <xref:System.Activities.Presentation.Model.ModelItem> consists of a pointer to the underlying value, as well as a collection of <xref:System.Activities.Presentation.Model.ModelProperty> objects.</span></span> <span data-ttu-id="c3771-109"><xref:System.Activities.Presentation.Model.ModelProperty> 개체는 속성의 이름 및 형식 같은 데이터와 값에 대한 포인터로 구성되며 이 값은 또 다른 <xref:System.Activities.Presentation.Model.ModelItem>입니다.</span><span class="sxs-lookup"><span data-stu-id="c3771-109">A <xref:System.Activities.Presentation.Model.ModelProperty> object in turn, consists of data such as the name and type of the property and then a pointer to the value, which in turn, is another <xref:System.Activities.Presentation.Model.ModelItem>.</span></span> <span data-ttu-id="c3771-110">값 변환기는 <xref:System.Activities.Presentation.Model.ModelItem>에서 반환된 <xref:System.Activities.Presentation.Model.ModelProperty>의 일부를 조작하여 트리 뷰에 올바르게 나타나도록 하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c3771-110">A value converter is used to manipulate some of the <xref:System.Activities.Presentation.Model.ModelItem>s returned from a <xref:System.Activities.Presentation.Model.ModelProperty> to make them appear correctly in the tree view.</span></span> <span data-ttu-id="c3771-111">그런 다음 샘플에서는 다음 예제에 표시된 것과 같은 명령적 구문을 사용하여 <xref:System.Activities.Presentation.Model.ModelItem> 트리에 대해 명령적으로 프로그래밍하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c3771-111">The sample then demonstrates how to imperatively program against the <xref:System.Activities.Presentation.Model.ModelItem> tree using the imperative syntax, as seen in the following example.</span></span>  
  
```csharp  
ModelItem mi = wd.Context.Services.GetService<ModelService>().Root;  
ModelProperty mp = mi.Properties["Activities"];  
mp.Collection.Add(new Persist());  
ModelItem justAdded = mp.Collection.Last();  
justAdded.Properties["DisplayName"].SetValue("new name");  
```  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="c3771-112">이 샘플을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="c3771-112">To use this sample</span></span>  
  
1.  <span data-ttu-id="c3771-113">[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]에서 ProgrammingModelItemTree.sln 솔루션을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="c3771-113">Open the ProgrammingModelItemTree.sln solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="c3771-114">선택 하 여 솔루션을 빌드합니다 **솔루션 빌드** 에서 **빌드** 메뉴.</span><span class="sxs-lookup"><span data-stu-id="c3771-114">Build the solution by selecting **Build Solution** from the **Build** menu.</span></span>  
  
3.  <span data-ttu-id="c3771-115">F5 키를 눌러 응용 프로그램을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c3771-115">Press F5 to run the application.</span></span> <span data-ttu-id="c3771-116">그러면 [!INCLUDE[avalon2](../../../../includes/avalon2-md.md)] 폼이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c3771-116">The [!INCLUDE[avalon2](../../../../includes/avalon2-md.md)] form is then displayed.</span></span>  
  
4.  <span data-ttu-id="c3771-117">클릭는 **WF 로드** 로드 하는 단추는 <xref:System.Activities.Presentation.Model.ModelItem> 트리 뷰에 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="c3771-117">Click the **Load WF** button to load the <xref:System.Activities.Presentation.Model.ModelItem> and bind it to the tree view.</span></span>  
  
5.  <span data-ttu-id="c3771-118">클릭 하 고 **트리 변경** 단추를 트리에 항목이 추가 되 고 속성을 설정 하려면 앞의 코드가 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c3771-118">Clicking the **Change Model Item Tree** button executes the preceding code to add an item into the tree and set a property.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="c3771-119">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3771-119">The samples may already be installed on your computer.</span></span> <span data-ttu-id="c3771-120">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="c3771-120">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="c3771-121">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="c3771-121">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="c3771-122">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3771-122">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Designer\ProgrammingModelItemTree`  
  
## <a name="see-also"></a><span data-ttu-id="c3771-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c3771-123">See Also</span></span>  
 <xref:System.Windows.Data.IValueConverter>
