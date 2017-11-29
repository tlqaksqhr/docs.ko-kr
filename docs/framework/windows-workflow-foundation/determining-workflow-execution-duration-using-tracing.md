---
title: "추적을 사용하여 워크플로 실행 기간 확인"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f04ad0fd-edc7-4cbc-8979-356f2a1131c4
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: acdc4f7d58eb0f5737adb59b113ea24d723d3b61
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="determining-workflow-execution-duration-using-tracing"></a><span data-ttu-id="d8bbf-102">추적을 사용하여 워크플로 실행 기간 확인</span><span class="sxs-lookup"><span data-stu-id="d8bbf-102">Determining Workflow Execution Duration Using Tracing</span></span>
<span data-ttu-id="d8bbf-103">이 항목에서는 성공적으로 완료된 자체 호스트되는 워크플로가 실행하는 데 걸리는 시간을 워크플로 추적을 사용하여 확인하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d8bbf-103">This topic demonstrates how to determine the time it takes for a successfully completed, self-hosted workflow to execute by using workflow tracing.</span></span>  
  
### <a name="to-determine-workflow-application-execution-duration-by-using-workflow-tracing"></a><span data-ttu-id="d8bbf-104">워크플로 추적을 사용하여 워크플로 응용 프로그램 실행 기간을 확인하려면</span><span class="sxs-lookup"><span data-stu-id="d8bbf-104">To determine workflow application execution duration by using workflow tracing</span></span>  
  
1.  <span data-ttu-id="d8bbf-105">[!INCLUDE[vs2010](../../../includes/vs2010-md.md)]를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="d8bbf-105">Open [!INCLUDE[vs2010](../../../includes/vs2010-md.md)].</span></span>  <span data-ttu-id="d8bbf-106">선택 **파일**, **새**, **프로젝트**합니다.</span><span class="sxs-lookup"><span data-stu-id="d8bbf-106">Select **File**, **New**, **Project**.</span></span>  <span data-ttu-id="d8bbf-107">아래 **C#**, 선택는 **워크플로** 노드.</span><span class="sxs-lookup"><span data-stu-id="d8bbf-107">Under **C#**, select the **Workflow** node.</span></span>  <span data-ttu-id="d8bbf-108">선택 **워크플로 콘솔 응용 프로그램** 템플릿 목록에서.</span><span class="sxs-lookup"><span data-stu-id="d8bbf-108">Select **Workflow Console Application** from the list of templates.</span></span>  <span data-ttu-id="d8bbf-109">새 프로젝트의 이름을 `WorkflowDurationTracing` 클릭 **확인**합니다.</span><span class="sxs-lookup"><span data-stu-id="d8bbf-109">Name the new project `WorkflowDurationTracing` and click **OK**.</span></span>  
  
2.  <span data-ttu-id="d8bbf-110">Workflow1.xaml을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="d8bbf-110">Open Workflow1.xaml.</span></span>  <span data-ttu-id="d8bbf-111"><xref:System.Activities.Statements.Delay> 활동을 디자이너 화면으로 끌어서 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="d8bbf-111">Drag a <xref:System.Activities.Statements.Delay> activity onto the designer surface.</span></span> <span data-ttu-id="d8bbf-112">활동의 Duration 속성에 00:00:10 값(10초)을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="d8bbf-112">Assign the value 00:00:10 (ten seconds) to the Duration property of the activity.</span></span>  
  
3.  <span data-ttu-id="d8bbf-113">클릭 하 여 이벤트 뷰어를 열고 **시작**, **실행**, 입력 및 `eventvwr.exe`합니다.</span><span class="sxs-lookup"><span data-stu-id="d8bbf-113">Open Event Viewer by clicking **Start**, **Run**, and entering `eventvwr.exe`.</span></span>  
  
4.  <span data-ttu-id="d8bbf-114">워크플로 추적을 활성화 하지 않은 확장 **Applications and Services Logs**, **Microsoft**, **Windows**, **응용 프로그램 서버-응용 프로그램** .</span><span class="sxs-lookup"><span data-stu-id="d8bbf-114">If you haven’t enabled workflow tracing, expand **Applications and Services Logs**, **Microsoft**, **Windows**, **Application Server-Applications**.</span></span> <span data-ttu-id="d8bbf-115">선택 **보기**, **분석 및 디버그 로그 표시**합니다.</span><span class="sxs-lookup"><span data-stu-id="d8bbf-115">Select **View**, **Show Analytic and Debug Logs**.</span></span> <span data-ttu-id="d8bbf-116">마우스 오른쪽 단추로 클릭 **디버그** 선택 **로그 사용**합니다.</span><span class="sxs-lookup"><span data-stu-id="d8bbf-116">Right-click **Debug** and select **Enable Log**.</span></span> <span data-ttu-id="d8bbf-117">워크플로가 실행된 후 추적 내용을 볼 수 있도록 이벤트 뷰어를 열어 둡니다.</span><span class="sxs-lookup"><span data-stu-id="d8bbf-117">Leave Event Viewer open so that traces can be viewed after the workflow is run.</span></span>  
  
5.  <span data-ttu-id="d8bbf-118">Ctrl+Shift+B를 눌러 워크플로 응용 프로그램을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d8bbf-118">Execute the workflow application by pressing CTRL+SHIFT+B.</span></span>  
  
6.  <span data-ttu-id="d8bbf-119">이벤트 뷰어에서 ID가 1009인 최근 이벤트 및 다음과 비슷한 메시지를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="d8bbf-119">In Event Viewer, find a recent event with ID 1009 and a message similar to the following.</span></span> <span data-ttu-id="d8bbf-120">메시지가 기록된 시간을 기록해 둡니다.</span><span class="sxs-lookup"><span data-stu-id="d8bbf-120">Make a note of the time that the message was logged.</span></span>  
  
 <span data-ttu-id="d8bbf-121">**부모 작업 ', DisplayName: ', InstanceId: ' 예약 된 자식 작업 'WorkflowDurationTracking.Workflow1', DisplayName: 'Workflow1', InstanceId: '1'.**</span><span class="sxs-lookup"><span data-stu-id="d8bbf-121">**Parent Activity '', DisplayName: '', InstanceId: '' scheduled child Activity 'WorkflowDurationTracking.Workflow1', DisplayName: 'Workflow1', InstanceId: '1'.**</span></span>  
  
7.  <span data-ttu-id="d8bbf-122">ID가 1001인 다른 최근 이벤트 및 다음과 비슷한 메시지를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="d8bbf-122">Find another recent event with ID 1001 and a message similar to the following.</span></span>  <span data-ttu-id="d8bbf-123">이 메시지의 기록된 값에서 이전 메시지 시간을 빼서 워크플로 실행 기간을 확인합니다. 이 시간은 10초 정도여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8bbf-123">Subtract the previous message time from this message’s Logged value to determine workflow execution duration, which should be around 10 seconds.</span></span>  
  
 <span data-ttu-id="d8bbf-124">**WorkflowInstance Id: ' 1bbac57b-3322-498e-9e27-8833fda3a5bf' Closed 상태로 완료 되었습니다.**</span><span class="sxs-lookup"><span data-stu-id="d8bbf-124">**WorkflowInstance Id: '1bbac57b-3322-498e-9e27-8833fda3a5bf' has completed in the Closed state.**</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8bbf-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d8bbf-125">See Also</span></span>  
 [<span data-ttu-id="d8bbf-126">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="d8bbf-126">Workflow Tracing</span></span>](../../../docs/framework/windows-workflow-foundation/workflow-tracing.md)  
 [<span data-ttu-id="d8bbf-127">Windows Server App Fabric 모니터링</span><span class="sxs-lookup"><span data-stu-id="d8bbf-127">Windows Server App Fabric Monitoring</span></span>](http://go.microsoft.com/fwlink/?LinkId=201273)  
 [<span data-ttu-id="d8bbf-128">App Fabric로 응용 프로그램 모니터링</span><span class="sxs-lookup"><span data-stu-id="d8bbf-128">Monitoring Applications with App Fabric</span></span>](http://go.microsoft.com/fwlink/?LinkId=201275)
