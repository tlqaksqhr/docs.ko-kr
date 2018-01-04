---
title: "방법: 기존 서비스 계약을 사용하는 워크플로 서비스 만들기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 11d11b59-acc4-48bf-8e4b-e97b516aa0a9
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a754875dc3f7968086f4f92044205b8ebceb01e2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-workflow-service-that-consumes-an-existing-service-contract"></a><span data-ttu-id="27342-102">방법: 기존 서비스 계약을 사용하는 워크플로 서비스 만들기</span><span class="sxs-lookup"><span data-stu-id="27342-102">How to: Create a workflow service that consumes an existing service contract</span></span>
[!INCLUDE[net_v45](../../../includes/net-v45-md.md)]<span data-ttu-id="27342-103">는 계약 중심 워크플로 개발의 형태로 웹 서비스와 워크플로 간에 보다 우수한 통합 성능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="27342-103"> features better integration between web services and workflows in the form of contract-first workflow development.</span></span> <span data-ttu-id="27342-104">계약 중심 워크플로 개발 도구를 사용하면 코드에서 계약을 먼저 디자인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27342-104">The contract-first workflow development tool allows you to design the contract in code first.</span></span> <span data-ttu-id="27342-105">그러면 이 도구는 계약의 작업을 위해 도구 상자에 활동 템플릿을 자동으로 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="27342-105">The tool then automatically generates an activity template in the toolbox for the operations in the contract.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="27342-106">이 항목에서는 계약 중심 워크플로 서비스를 만들기 위한 단계별 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="27342-106">This topic provides step-by-step guidance on creating a contract-first workflow service.</span></span> [!INCLUDE[crabout](../../../includes/crabout-md.md)]<span data-ttu-id="27342-107">계약 중심 워크플로 서비스 개발, 참조 [계약 중심 워크플로 서비스 개발](../../../docs/framework/windows-workflow-foundation/contract-first-workflow-service-development.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="27342-107"> contract-first workflow service development, see [Contract First Workflow Service Development](../../../docs/framework/windows-workflow-foundation/contract-first-workflow-service-development.md).</span></span>  
  
### <a name="creating-the-workflow-project"></a><span data-ttu-id="27342-108">워크플로 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="27342-108">Creating the workflow project</span></span>  
  
1.  <span data-ttu-id="27342-109">[!INCLUDE[vs_current_short](../../../includes/vs-current-short-md.md)]선택, **파일**, **새 프로젝트**합니다.</span><span class="sxs-lookup"><span data-stu-id="27342-109">In [!INCLUDE[vs_current_short](../../../includes/vs-current-short-md.md)], select **File**, **New Project**.</span></span> <span data-ttu-id="27342-110">선택의 **WCF** 노드 아래의 **C#** 에서 노드는 **템플릿** 트리, 선택한는 **WCF 워크플로 서비스 응용 프로그램** 서식 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="27342-110">Select the **WCF** node under the **C#** node in the **Templates** tree, and select the **WCF Workflow Service Application** template.</span></span>  
  
2.  <span data-ttu-id="27342-111">새 프로젝트의 이름을 `ContractFirst` 클릭 **확인**합니다.</span><span class="sxs-lookup"><span data-stu-id="27342-111">Name the new project `ContractFirst` and click **Ok**.</span></span>  
  
### <a name="creating-the-service-contract"></a><span data-ttu-id="27342-112">서비스 계약 만들기</span><span class="sxs-lookup"><span data-stu-id="27342-112">Creating the service contract</span></span>  
  
1.  <span data-ttu-id="27342-113">프로젝트를 마우스 오른쪽 단추로 클릭 **솔루션 탐색기** 선택 **추가**, **새 항목...** .</span><span class="sxs-lookup"><span data-stu-id="27342-113">Right-click the project in **Solution Explorer** and select **Add**, **New Item…**.</span></span> <span data-ttu-id="27342-114">선택은 **코드** 왼쪽의 노드 및 **클래스** 오른쪽에 서식 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="27342-114">Select the **Code** node on the left, and the **Class** template on the right.</span></span> <span data-ttu-id="27342-115">클래스의 새 이름을 `IBookService` 클릭 **확인**합니다.</span><span class="sxs-lookup"><span data-stu-id="27342-115">Name the new class `IBookService` and click **Ok**.</span></span>  
  
2.  <span data-ttu-id="27342-116">표시되는 코드 창의 맨 위에서 `System.Servicemodel`에 Using 문을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="27342-116">In the top of the code window that appears, add a Using statement to `System.Servicemodel`.</span></span>  
  
    ```  
    using System.ServiceModel;  
    ```  
  
3.  <span data-ttu-id="27342-117">샘플 클래스 정의를 다음과 같은 인터페이스 정의로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="27342-117">Change the sample class definition to the following interface definition.</span></span>  
  
    ```  
    [ServiceContract]  
        public interface IBookService  
        {  
            [OperationContract]  
            void Buy(string bookName);  
  
            [OperationContract(IsOneWay=true)]  
            void Checkout();  
        }  
    ```  
  
4.  <span data-ttu-id="27342-118">키를 눌러 프로젝트를 빌드합니다 **Ctrl + Shift + B**합니다.</span><span class="sxs-lookup"><span data-stu-id="27342-118">Build the project by pressing **Ctrl+Shift+B**.</span></span>  
  
### <a name="importing-the-service-contract"></a><span data-ttu-id="27342-119">서비스 계약 가져오기</span><span class="sxs-lookup"><span data-stu-id="27342-119">Importing the service contract</span></span>  
  
1.  <span data-ttu-id="27342-120">프로젝트를 마우스 오른쪽 단추로 클릭 **솔루션 탐색기** 선택 **서비스 계약 가져오기**합니다.</span><span class="sxs-lookup"><span data-stu-id="27342-120">Right-click the project in **Solution Explorer** and select **Import Service Contract**.</span></span> <span data-ttu-id="27342-121">아래  **\<현재 프로젝트 >**를 모든 하위 노드를 열고 선택 **IBookService**합니다.</span><span class="sxs-lookup"><span data-stu-id="27342-121">Under **\<Current Project>**, open all sub-nodes and select **IBookService**.</span></span> <span data-ttu-id="27342-122">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="27342-122">Click **OK**.</span></span>  
  
2.  <span data-ttu-id="27342-123">작업이 성공적으로 완료되었음을 알리는 대화 상자가 열리고 프로젝트가 빌드된 후 생성된 활동이 도구 상자에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="27342-123">A dialog will open, alerting you that the operation completed successfully, and that the generated activities will appear in the toolbox after you build the project.</span></span> <span data-ttu-id="27342-124">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="27342-124">Click **OK**.</span></span>  
  
3.  <span data-ttu-id="27342-125">키를 눌러 프로젝트를 빌드합니다 **Ctrl + Shift + B**, 가져온된 활동이 도구 상자에 표시 되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="27342-125">Build the project by pressing **Ctrl+Shift+B**, so that the imported activities will appear in the toolbox.</span></span>  
  
4.  <span data-ttu-id="27342-126">**솔루션 탐색기**, Service1.xamlx를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="27342-126">In **Solution Explorer**, open Service1.xamlx.</span></span> <span data-ttu-id="27342-127">워크플로 서비스가 디자이너에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="27342-127">The workflow service will appear in the designer.</span></span>  
  
5.  <span data-ttu-id="27342-128">선택 된 **시퀀스** 활동입니다.</span><span class="sxs-lookup"><span data-stu-id="27342-128">Select the **Sequence** activity.</span></span> <span data-ttu-id="27342-129">속성 창에서 클릭 된 **...**</span><span class="sxs-lookup"><span data-stu-id="27342-129">In the Properties window, click the **…**</span></span> <span data-ttu-id="27342-130">단추는 **ImplementedContract** 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="27342-130">button in the **ImplementedContract** property.</span></span> <span data-ttu-id="27342-131">에 **형식 컬렉션 편집기** 창이 나타나면 클릭는 **형식** 드롭다운을 선택 하 고는 **형식 찾아보기...**</span><span class="sxs-lookup"><span data-stu-id="27342-131">In the **Type Collection Editor** window that appears, click the **Type** dropdown, and select the **Browse for Types…**</span></span> <span data-ttu-id="27342-132">항목입니다.</span><span class="sxs-lookup"><span data-stu-id="27342-132">entry.</span></span> <span data-ttu-id="27342-133">에 **찾아보기.Net 유형을 선택** 대화에서  **\<현재 프로젝트 >**를 모든 하위 노드를 열고 선택 **IBookService**합니다.</span><span class="sxs-lookup"><span data-stu-id="27342-133">In the **Browse and Select a .Net Type** dialog, under **\<Current Project>**, open all sub-nodes and select **IBookService**.</span></span> <span data-ttu-id="27342-134">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="27342-134">Click **OK**.</span></span> <span data-ttu-id="27342-135">에 **형식 컬렉션 편집기** 대화 상자를 클릭 하 여 **확인**합니다.</span><span class="sxs-lookup"><span data-stu-id="27342-135">In the **Type Collection Editor** dialog, click **OK**.</span></span>  
  
6.  <span data-ttu-id="27342-136">선택 하 고 삭제는 **ReceiveRequest** 및 **SendResponse** 활동입니다.</span><span class="sxs-lookup"><span data-stu-id="27342-136">Select and delete the **ReceiveRequest** and **SendResponse** activities.</span></span>  
  
7.  <span data-ttu-id="27342-137">도구 상자에서 끌어는 **Buy_ReceiveAndSendReply** 및 **Checkout_Receive** 활동을 놓으면는 **순차 서비스** 활동입니다.</span><span class="sxs-lookup"><span data-stu-id="27342-137">From the toolbox, drag a **Buy_ReceiveAndSendReply** and a **Checkout_Receive** activity onto the **Sequential Service** activity.</span></span>
