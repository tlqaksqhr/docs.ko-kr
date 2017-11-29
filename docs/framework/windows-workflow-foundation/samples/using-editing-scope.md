---
title: "편집 범위 사용"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 79306f9e-318b-4687-9863-8b93d1841716
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 6aec54cef13bcd99fb65a6305e086fe577b6bc13
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="using-editing-scope"></a><span data-ttu-id="a9951-102">편집 범위 사용</span><span class="sxs-lookup"><span data-stu-id="a9951-102">Using Editing Scope</span></span>
<span data-ttu-id="a9951-103">이 샘플에서는 단일 원자 단위에서 실행 취소될 수 있도록 일련의 변경 내용을 일괄 처리하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a9951-103">This sample demonstrates how to batch a set of changes so that they can be undone in a single atomic unit.</span></span> <span data-ttu-id="a9951-104">기본적으로 활동 디자이너 작성자가 수행하는 동작은 실행 취소/다시 실행 시스템에 자동으로 통합됩니다.</span><span class="sxs-lookup"><span data-stu-id="a9951-104">By default, the actions taken by an activity designer author are automatically integrated into the Undo/Redo system.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="a9951-105">세부 항목</span><span class="sxs-lookup"><span data-stu-id="a9951-105">Demonstrates</span></span>  
 <span data-ttu-id="a9951-106">범위 편집과 실행 취소 및 다시 실행</span><span class="sxs-lookup"><span data-stu-id="a9951-106">Editing scope and Undo and Redo.</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="a9951-107">토론</span><span class="sxs-lookup"><span data-stu-id="a9951-107">Discussion</span></span>  
 <span data-ttu-id="a9951-108">이 샘플에서는 단일 작업 단위 내에서 <xref:System.Activities.Presentation.Model.ModelItem> 트리에 대한 일련의 변경 내용을 일괄 처리하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a9951-108">This sample demonstrates how to batch a set of changes to the <xref:System.Activities.Presentation.Model.ModelItem> tree within a single unit of work.</span></span> <span data-ttu-id="a9951-109">WPF 디자이너에서 직접 <xref:System.Activities.Presentation.Model.ModelItem> 값에 바인딩할 때 변경 내용이 자동으로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a9951-109">Note that when binding to <xref:System.Activities.Presentation.Model.ModelItem> values directly from a WPF designer, changes are applied automatically.</span></span> <span data-ttu-id="a9951-110">이 샘플에서는 단일 변경 내용이 아닌 일괄 처리할 여러 개의 변경 내용을 명령적 코드를 통해 처리할 때 수행해야 하는 작업을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a9951-110">This sample demonstrates what must be done when multiple changes to be batched are being made through imperative code, rather than a single change.</span></span>  
  
 <span data-ttu-id="a9951-111">이 샘플에서는 세 가지 활동이 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="a9951-111">In this sample, three activities are added.</span></span> <span data-ttu-id="a9951-112">편집을 시작하면 <xref:System.Activities.Presentation.Model.ModelItem.BeginEdit%2A>의 인스턴스에서 <xref:System.Activities.Presentation.Model.ModelItem>가 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="a9951-112">When editing begins, <xref:System.Activities.Presentation.Model.ModelItem.BeginEdit%2A> is called on an instance of <xref:System.Activities.Presentation.Model.ModelItem>.</span></span> <span data-ttu-id="a9951-113">이 편집 범위 내의 <xref:System.Activities.Presentation.Model.ModelItem> 트리에 대한 변경 내용이 일괄 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="a9951-113">Changes made to the <xref:System.Activities.Presentation.Model.ModelItem> tree within this editing scope are batched.</span></span> <span data-ttu-id="a9951-114"><xref:System.Activities.Presentation.Model.ModelItem.BeginEdit%2A> 명령은 이 인스턴스를 제어하는 데 사용할 수 있는 <xref:System.Activities.Presentation.Model.EditingScope>를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="a9951-114">The <xref:System.Activities.Presentation.Model.ModelItem.BeginEdit%2A> command returns an <xref:System.Activities.Presentation.Model.EditingScope>, which can be used to control this instance.</span></span> <span data-ttu-id="a9951-115"><xref:System.Activities.Presentation.Model.EditingScope.OnComplete%2A> 또는 <xref:System.Activities.Presentation.Model.EditingScope.OnRevert%2A>를 호출하여 편집 범위를 커밋하거나 되돌릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9951-115">Either <xref:System.Activities.Presentation.Model.EditingScope.OnComplete%2A> or <xref:System.Activities.Presentation.Model.EditingScope.OnRevert%2A> can be called to either commit or revert the editing scope.</span></span>  
  
 <span data-ttu-id="a9951-116">여러 개의 변경 내용 집합을 더 큰 편집 범위의 일부로 추적하고 개별적으로 제어할 수 있도록<xref:System.Activities.Presentation.Model.EditingScope> 개체를 중첩할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9951-116">You can also nest <xref:System.Activities.Presentation.Model.EditingScope> objects, which allows for multiple sets of changes to be tracked as part of a larger editing scope and can be controlled individually.</span></span> <span data-ttu-id="a9951-117">이 기능을 사용할 수 있는 시나리오는 모든 변경 내용이 단일 원자 단위 작업으로 처리될 여러 대화 상자의 변경 내용을 개별적으로 커밋하거나 되돌려야 하는 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="a9951-117">A scenario that may use this feature would be when changes from multiple dialogs must be committed or reverted separately, with all changes being treated as a single atomic operation.</span></span> <span data-ttu-id="a9951-118">이 샘플에서는 편집 범위가 <xref:System.Collections.ObjectModel.ObservableCollection%601> 형식의 <xref:System.Activities.Presentation.Model.ModelEditingScope>을 사용하여 누적됩니다.</span><span class="sxs-lookup"><span data-stu-id="a9951-118">In this sample, the editing scopes are stacked using an <xref:System.Collections.ObjectModel.ObservableCollection%601> of type <xref:System.Activities.Presentation.Model.ModelEditingScope>.</span></span> <span data-ttu-id="a9951-119">디자인 화면에서 중첩 한도를 확인할 수 있도록 <xref:System.Collections.ObjectModel.ObservableCollection%601>이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a9951-119">The <xref:System.Collections.ObjectModel.ObservableCollection%601> is used so that the depth of the nesting can be observed on the designer surface.</span></span>  
  
## <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="a9951-120">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="a9951-120">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="a9951-121">샘플을 빌드하고 실행한 다음 왼쪽의 단추를 사용하여 워크플로를 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="a9951-121">Build and run the sample, and then use the buttons on the left to modify the workflow.</span></span>  
  
2.  <span data-ttu-id="a9951-122">클릭 **범위를 편집 열고**합니다.</span><span class="sxs-lookup"><span data-stu-id="a9951-122">Click **Open Editing Scope**.</span></span>  
  
    1.  <span data-ttu-id="a9951-123">이 명령은 편집 범위를 만들어 편집 스택에 푸시하는 <xref:System.Activities.Presentation.Model.ModelItem.BeginEdit%2A>를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="a9951-123">This command calls <xref:System.Activities.Presentation.Model.ModelItem.BeginEdit%2A> that creates an editing scope and pushes it onto the editing stack.</span></span>  
  
    2.  <span data-ttu-id="a9951-124">그러면 선택한 <xref:System.Activities.Presentation.Model.ModelItem>에 세 개의 활동이 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="a9951-124">Three activities are then added to the selected <xref:System.Activities.Presentation.Model.ModelItem>.</span></span> <span data-ttu-id="a9951-125"><xref:System.Activities.Presentation.Model.ModelItem.BeginEdit%2A>를 사용하여 편집 범위를 열지 않았다면 디자이너 캔버스에 세 개의 새 활동이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="a9951-125">Note that if the editing scope had not been opened with <xref:System.Activities.Presentation.Model.ModelItem.BeginEdit%2A>, three new activities would appear on the designer canvas.</span></span> <span data-ttu-id="a9951-126">이 작업은 <xref:System.Activities.Presentation.Model.EditingScope> 내에서 여전히 보류 중이므로 디자이너가 아직 업데이트되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="a9951-126">Because this operation is still pending within the <xref:System.Activities.Presentation.Model.EditingScope>, the designer is not yet updated.</span></span>  
  
3.  <span data-ttu-id="a9951-127">키를 눌러 **편집 범위 닫기** 에 편집 범위를 커밋합니다.</span><span class="sxs-lookup"><span data-stu-id="a9951-127">Press **Close Editing Scope** to commit the editing scope.</span></span> <span data-ttu-id="a9951-128">그러면 디자이너에 세 개의 활동이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="a9951-128">Three activities appear in the designer.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="a9951-129">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9951-129">The samples may already be installed on your machine.</span></span> <span data-ttu-id="a9951-130">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="a9951-130">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="a9951-131">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="a9951-131">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="a9951-132">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9951-132">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\CustomActivityDesigners\UsingEditingScope`
