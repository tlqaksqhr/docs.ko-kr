---
title: "연습: Windows Forms 응용 프로그램에서 데이터 흐름 사용"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- TPL dataflow library, in Windows Forms
- Task Parallel Library, dataflows
- Windows Forms, and TPL
ms.assetid: 9c65cdf7-660c-409f-89ea-59d7ec8e127c
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d2775cc99020fd99d6e7d79cdf3e1ffcc3219146
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="walkthrough-using-dataflow-in-a-windows-forms-application"></a><span data-ttu-id="dc5db-102">연습: Windows Forms 응용 프로그램에서 데이터 흐름 사용</span><span class="sxs-lookup"><span data-stu-id="dc5db-102">Walkthrough: Using Dataflow in a Windows Forms Application</span></span>
<span data-ttu-id="dc5db-103">이 문서에서는 Windows Forms 응용 프로그램에서 이미지 처리를 수행하는 데이터 흐름 블록의 네트워크를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="dc5db-103">This document demonstrates how to create a network of dataflow blocks that perform image processing in a Windows Forms application.</span></span>  
  
 <span data-ttu-id="dc5db-104">이 예제는 지정된 폴더에서 이미지 파일을 로드하고 합성 이미지를 만들어 결과를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="dc5db-104">This example loads image files from the specified folder, creates a composite image, and displays the result.</span></span> <span data-ttu-id="dc5db-105">이 예제에서는 네트워크를 통해 이미지를 라우팅하는 데 데이터 흐름 모델을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="dc5db-105">The example uses the dataflow model to route images through the network.</span></span> <span data-ttu-id="dc5db-106">데이터 흐름 모델에서는, 프로그램의 개별 구성 요소가 메시지를 전달하여 서로 통신합니다.</span><span class="sxs-lookup"><span data-stu-id="dc5db-106">In the dataflow model, independent components of a program communicate with one another by sending messages.</span></span> <span data-ttu-id="dc5db-107">구성 요소가 메시지를 받으면 어떤 작업을 수행한 후 결과를 다른 구성 요소에 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="dc5db-107">When a component receives a message, it performs some action and then passes the result to another component.</span></span> <span data-ttu-id="dc5db-108">이를 응용 프로그램에서 제어 구조(예 : 조건 문, 루프 등)를 사용하는 제어 흐름 모델과 비교하여 프로그램에서 작업 순서를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="dc5db-108">Compare this with the control flow model, in which an application uses control structures, for example, conditional statements, loops, and so on, to control the order of operations in a program.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="dc5db-109">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="dc5db-109">Prerequisites</span></span>  
 <span data-ttu-id="dc5db-110">이 연습을 시작하기 전에 [데이터 흐름](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)을 읽어 보세요.</span><span class="sxs-lookup"><span data-stu-id="dc5db-110">Read [Dataflow](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md) before you start this walkthrough.</span></span>  
  
> [!TIP]
>  <span data-ttu-id="dc5db-111">TPL 데이터 흐름 라이브러리(<xref:System.Threading.Tasks.Dataflow?displayProperty=nameWithType> 네임스페이스)는 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]와 함께 배포되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dc5db-111">The TPL Dataflow Library (<xref:System.Threading.Tasks.Dataflow?displayProperty=nameWithType> namespace) is not distributed with the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)].</span></span> <span data-ttu-id="dc5db-112">설치 하는 <xref:System.Threading.Tasks.Dataflow> 네임 스페이스에서 프로젝트를 열고 [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], 선택 **NuGet 패키지 관리** 프로젝트 메뉴에 대 한 온라인 검색에서는 `Microsoft.Tpl.Dataflow` 패키지 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc5db-112">To install the <xref:System.Threading.Tasks.Dataflow> namespace, open your project in [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], choose **Manage NuGet Packages** from the Project menu, and search online for the `Microsoft.Tpl.Dataflow` package.</span></span>  
 
  
## <a name="sections"></a><span data-ttu-id="dc5db-113">섹션</span><span class="sxs-lookup"><span data-stu-id="dc5db-113">Sections</span></span>  
 <span data-ttu-id="dc5db-114">이 연습에는 다음과 같은 섹션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc5db-114">This walkthrough contains the following sections:</span></span>  
  
-   [<span data-ttu-id="dc5db-115">Windows Forms 응용 프로그램 만들기</span><span class="sxs-lookup"><span data-stu-id="dc5db-115">Creating the Windows Forms Application</span></span>](#winforms)  
  
-   [<span data-ttu-id="dc5db-116">데이터 흐름 네트워크 만들기</span><span class="sxs-lookup"><span data-stu-id="dc5db-116">Creating the Dataflow Network</span></span>](#network)  
  
-   [<span data-ttu-id="dc5db-117">사용자 인터페이스에 데이터 흐름 네트워크 연결</span><span class="sxs-lookup"><span data-stu-id="dc5db-117">Connecting the Dataflow Network to the User Interface</span></span>](#ui)  
  
-   [<span data-ttu-id="dc5db-118">전체 예제</span><span class="sxs-lookup"><span data-stu-id="dc5db-118">The Complete Example</span></span>](#complete)  
  
<a name="winforms"></a>   
## <a name="creating-the-windows-forms-application"></a><span data-ttu-id="dc5db-119">Windows Forms 응용 프로그램 만들기</span><span class="sxs-lookup"><span data-stu-id="dc5db-119">Creating the Windows Forms Application</span></span>  
 <span data-ttu-id="dc5db-120">이 섹션에서는 기본 Windows Forms 응용 프로그램을 만들고 기본 폼에 컨트롤을 추가하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="dc5db-120">This section describes how to create the basic Windows Forms application and add controls to the main form.</span></span>  
  
#### <a name="to-create-the-windows-forms-application"></a><span data-ttu-id="dc5db-121">Windows Forms 응용 프로그램을 만들려면</span><span class="sxs-lookup"><span data-stu-id="dc5db-121">To Create the Windows Forms Application</span></span>  
  
1.  <span data-ttu-id="dc5db-122">[!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]에서 [!INCLUDE[csprcs](../../../includes/csprcs-md.md)] 또는 Visual Basic **Windows Forms 응용 프로그램** 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="dc5db-122">In [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)], create a [!INCLUDE[csprcs](../../../includes/csprcs-md.md)] or Visual Basic **Windows Forms Application** project.</span></span> <span data-ttu-id="dc5db-123">이 문서에서 프로젝트 이름은 `CompositeImages`입니다.</span><span class="sxs-lookup"><span data-stu-id="dc5db-123">In this document, the project is named `CompositeImages`.</span></span>  
  
2.  <span data-ttu-id="dc5db-124">기본 폼인 Form1.cs의 폼 디자이너에서 (Form1.vb [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]), 추가 <xref:System.Windows.Forms.ToolStrip> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc5db-124">On the form designer for the main form, Form1.cs (Form1.vb for [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]), add a <xref:System.Windows.Forms.ToolStrip> control.</span></span>  
  
3.  <span data-ttu-id="dc5db-125">추가 <xref:System.Windows.Forms.ToolStripButton> 컨트롤을 <xref:System.Windows.Forms.ToolStrip> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc5db-125">Add a <xref:System.Windows.Forms.ToolStripButton> control to the <xref:System.Windows.Forms.ToolStrip> control.</span></span> <span data-ttu-id="dc5db-126">설정의 <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> 속성을 <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text> 및 <xref:System.Windows.Forms.ToolStripItem.Text%2A> 속성을 **폴더 선택**합니다.</span><span class="sxs-lookup"><span data-stu-id="dc5db-126">Set the <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> property to <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text> and the <xref:System.Windows.Forms.ToolStripItem.Text%2A> property to **Choose Folder**.</span></span>  
  
4.  <span data-ttu-id="dc5db-127">두 번째 추가 <xref:System.Windows.Forms.ToolStripButton> 컨트롤을 <xref:System.Windows.Forms.ToolStrip> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc5db-127">Add a second <xref:System.Windows.Forms.ToolStripButton> control to the <xref:System.Windows.Forms.ToolStrip> control.</span></span> <span data-ttu-id="dc5db-128">설정의 <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> 속성을 <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text>, <xref:System.Windows.Forms.ToolStripItem.Text%2A> 속성을 **취소**, 및 <xref:System.Windows.Forms.ToolStripItem.Enabled%2A> 속성을 `False`합니다.</span><span class="sxs-lookup"><span data-stu-id="dc5db-128">Set the <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> property to <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text>, the <xref:System.Windows.Forms.ToolStripItem.Text%2A> property to **Cancel**, and the <xref:System.Windows.Forms.ToolStripItem.Enabled%2A> property to `False`.</span></span>  
  
5.  <span data-ttu-id="dc5db-129">추가 <xref:System.Windows.Forms.PictureBox> 기본 폼에는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="dc5db-129">Add a <xref:System.Windows.Forms.PictureBox> object to the main form.</span></span> <span data-ttu-id="dc5db-130"><xref:System.Windows.Forms.Control.Dock%2A> 속성을 <xref:System.Windows.Forms.DockStyle.Fill>으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="dc5db-130">Set the <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>  
  
<a name="network"></a>   
## <a name="creating-the-dataflow-network"></a><span data-ttu-id="dc5db-131">데이터 흐름 네트워크 만들기</span><span class="sxs-lookup"><span data-stu-id="dc5db-131">Creating the Dataflow Network</span></span>  
 <span data-ttu-id="dc5db-132">이 섹션에서는 이미지 처리를 수행하는 데이터 흐름 네트워크를 만드는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="dc5db-132">This section describes how to create the dataflow network that performs image processing.</span></span>  
  
#### <a name="to-create-the-dataflow-network"></a><span data-ttu-id="dc5db-133">데이터 흐름 네트워크를 만들려면</span><span class="sxs-lookup"><span data-stu-id="dc5db-133">To Create the Dataflow Network</span></span>  
  
1.  <span data-ttu-id="dc5db-134">프로젝트에 System.Threading.Tasks.Dataflow.dll에 대한 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="dc5db-134">Add a reference to System.Threading.Tasks.Dataflow.dll to your project.</span></span>  
  
2.  <span data-ttu-id="dc5db-135">Form1.cs([!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]에서는 Form1.vb)에 다음 `using`([!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]에서는 `Using`) 문이 포함되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="dc5db-135">Ensure that Form1.cs (Form1.vb for [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) contains the following `using` (`Using` in [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) statements:</span></span>  
  
     [!code-csharp[TPLDataflow_CompositeImages#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_compositeimages/cs/compositeimages/form1.cs#1)]  
  
3.  <span data-ttu-id="dc5db-136">`Form1` 클래스에 다음 데이터 멤버를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="dc5db-136">Add the following data members to the `Form1` class:</span></span>  
  
     [!code-csharp[TPLDataflow_CompositeImages#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_compositeimages/cs/compositeimages/form1.cs#2)]  
  
4.  <span data-ttu-id="dc5db-137">다음 `CreateImageProcessingNetwork` 메서드를 `Form1` 클래스에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="dc5db-137">Add the following method, `CreateImageProcessingNetwork`, to the `Form1` class.</span></span> <span data-ttu-id="dc5db-138">이 메서드는 이미지 처리 네트워크를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="dc5db-138">This method creates the image processing network.</span></span>  
  
     [!code-csharp[TPLDataflow_CompositeImages#3](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_compositeimages/cs/compositeimages/form1.cs#3)]  
  
5.  <span data-ttu-id="dc5db-139">`LoadBitmaps` 메서드를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="dc5db-139">Implement the `LoadBitmaps` method.</span></span>  
  
     [!code-csharp[TPLDataflow_CompositeImages#4](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_compositeimages/cs/compositeimages/form1.cs#4)]  
  
6.  <span data-ttu-id="dc5db-140">`CreateCompositeBitmap` 메서드를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="dc5db-140">Implement the `CreateCompositeBitmap` method.</span></span>  
  
     [!code-csharp[TPLDataflow_CompositeImages#5](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_compositeimages/cs/compositeimages/form1.cs#5)]  
  
    > [!NOTE]
    >  <span data-ttu-id="dc5db-141">C# 버전의는 `CreateCompositeBitmap` 메서드에 대 한 포인터를 사용 하 여 효율적으로 처리할 수 있도록 하는 <xref:System.Drawing.Bitmap?displayProperty=nameWithType> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="dc5db-141">The C# version of the `CreateCompositeBitmap` method uses pointers to enable efficient processing of the <xref:System.Drawing.Bitmap?displayProperty=nameWithType> objects.</span></span> <span data-ttu-id="dc5db-142">따라서 [unsafe](~/docs/csharp/language-reference/keywords/unsafe.md) 키워드를 사용하려면 프로젝트에서 **안전하지 않은 코드 허용** 옵션을 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc5db-142">Therefore, you must enable the **Allow unsafe code** option in your project in order to use the [unsafe](~/docs/csharp/language-reference/keywords/unsafe.md) keyword.</span></span> <span data-ttu-id="dc5db-143">안전 하지 않은 코드를 사용 하는 방법에 대 한 자세한 내용은 [!INCLUDE[csprcs](../../../includes/csprcs-md.md)] 프로젝트에서 참조 [빌드 페이지, 프로젝트 디자이너 (C#)] https://msdn.microsoft.com/library/kb4wyys2).</span><span class="sxs-lookup"><span data-stu-id="dc5db-143">For more information about how to enable unsafe code in a [!INCLUDE[csprcs](../../../includes/csprcs-md.md)] project, see [Build Page, Project Designer (C#)]https://msdn.microsoft.com/library/kb4wyys2).</span></span>  
  
 <span data-ttu-id="dc5db-144">다음 표에서는 네트워크의 멤버를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="dc5db-144">The following table describes the members of the network.</span></span>  
  
|<span data-ttu-id="dc5db-145">멤버</span><span class="sxs-lookup"><span data-stu-id="dc5db-145">Member</span></span>|<span data-ttu-id="dc5db-146">형식</span><span class="sxs-lookup"><span data-stu-id="dc5db-146">Type</span></span>|<span data-ttu-id="dc5db-147">설명</span><span class="sxs-lookup"><span data-stu-id="dc5db-147">Description</span></span>|  
|------------|----------|-----------------|  
|`loadBitmaps`|<xref:System.Threading.Tasks.Dataflow.TransformBlock%602>|<span data-ttu-id="dc5db-148">입력으로 폴더 경로 사용 하 고 컬렉션을 생성 <xref:System.Drawing.Bitmap> 개체를 출력으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc5db-148">Takes a folder path as input and produces a collection of <xref:System.Drawing.Bitmap> objects as output.</span></span>|  
|`createCompositeBitmap`|<xref:System.Threading.Tasks.Dataflow.TransformBlock%602>|<span data-ttu-id="dc5db-149">컬렉션을 가져와서 <xref:System.Drawing.Bitmap> 입력으로 개체를 출력으로 복합 비트맵을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc5db-149">Takes a collection of <xref:System.Drawing.Bitmap> objects as input and produces a composite bitmap as output.</span></span>|  
|`displayCompositeBitmap`|<xref:System.Threading.Tasks.Dataflow.ActionBlock%601>|<span data-ttu-id="dc5db-150">폼에 복합 비트맵을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="dc5db-150">Displays the composite bitmap on the form.</span></span>|  
|`operationCancelled`|<xref:System.Threading.Tasks.Dataflow.ActionBlock%601>|<span data-ttu-id="dc5db-151">작업이 취소되었고 사용자가 다른 폴더를 선택할 수 있음을 나타내는 이미지를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="dc5db-151">Displays an image to indicate that the operation is canceled and enables the user to select another folder.</span></span>|  
  
 <span data-ttu-id="dc5db-152">이 예제에서는 네트워크를 구성 하도록 데이터 흐름 블록을 연결 하기 위해 사용 된 <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601.LinkTo%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="dc5db-152">To connect the dataflow blocks to form a network, this example uses the <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601.LinkTo%2A> method.</span></span> <span data-ttu-id="dc5db-153"><xref:System.Threading.Tasks.Dataflow.ISourceBlock%601.LinkTo%2A> 메서드를 사용 하는 오버 로드 된 버전을 포함 한 <xref:System.Predicate%601> 대상 블록을 수락할지 아니면 거부 메시지를 결정 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="dc5db-153">The <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601.LinkTo%2A> method contains an overloaded version that takes a <xref:System.Predicate%601> object that determines whether the target block accepts or rejects a message.</span></span> <span data-ttu-id="dc5db-154">이 필터링 메커니즘을 통해 메시지 블록은 특정 값만 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc5db-154">This filtering mechanism enables message blocks to receive only certain values.</span></span> <span data-ttu-id="dc5db-155">이 예제에서는 네트워크가 두 방법 중 하나로 분기할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc5db-155">In this example, the network can branch in one of two ways.</span></span> <span data-ttu-id="dc5db-156">주 분기에서는 디스크에서 이미지를 로드하고 복합 이미지를 만들고 폼에 이미지를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="dc5db-156">The main branch loads the images from disk, creates the composite image, and displays that image on the form.</span></span> <span data-ttu-id="dc5db-157">대체 분기는 현재 작업을 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="dc5db-157">The alternate branch cancels the current operation.</span></span> <span data-ttu-id="dc5db-158"><xref:System.Predicate%601> 특정 메시지를 거부 하 여 다른 분기를 전환할 수 main 분기에 따라 데이터 흐름 블록 개체를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc5db-158">The <xref:System.Predicate%601> objects enable the dataflow blocks along the main branch to switch to the alternative branch by rejecting certain messages.</span></span> <span data-ttu-id="dc5db-159">예를 들어 사용자가 작업을 취소하면 데이터 흐름 블록 `createCompositeBitmap`은 출력으로 `null`([!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]에서 `Nothing`)을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="dc5db-159">For example, if the user cancels the operation, the dataflow block `createCompositeBitmap` produces `null` (`Nothing` in [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) as its output.</span></span> <span data-ttu-id="dc5db-160">데이터 흐름 블록 `displayCompositeBitmap`은 `null` 입력 값을 거부하므로 메시지가 `operationCancelled`에 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc5db-160">The dataflow block `displayCompositeBitmap` rejects `null` input values, and therefore, the message is offered to `operationCancelled`.</span></span> <span data-ttu-id="dc5db-161">데이터 흐름 블록 `operationCancelled`은 모든 메시지를 수락하므로 작업이 취소됨을 나타내는 이미지를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="dc5db-161">The dataflow block `operationCancelled` accepts all messages and therefore, displays an image to indicate that the operation is canceled.</span></span>  
  
 <span data-ttu-id="dc5db-162">다음 그림에서는 이미지 처리 네트워크를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="dc5db-162">The following illustration shows the image processing network.</span></span>  
  
 <span data-ttu-id="dc5db-163">![이미지 처리 네트워크](../../../docs/standard/parallel-programming/media/dataflowwinforms.png "DataflowWinForms")</span><span class="sxs-lookup"><span data-stu-id="dc5db-163">![The image processing network](../../../docs/standard/parallel-programming/media/dataflowwinforms.png "DataflowWinForms")</span></span>  
  
 <span data-ttu-id="dc5db-164">`displayCompositeBitmap` 및 `operationCancelled` 데이터 흐름 블록이 사용자 인터페이스에서 작동하기 때문에 이러한 작업은 사용자 인터페이스 스레드에서 발생해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc5db-164">Because the `displayCompositeBitmap` and `operationCancelled` dataflow blocks act on the user interface, it is important that these actions occur on the user-interface thread.</span></span> <span data-ttu-id="dc5db-165">이를 위해, 생성 하는 동안 이러한 개체는 다음과 같이 제공 됩니다. 한 <xref:System.Threading.Tasks.Dataflow.ExecutionDataflowBlockOptions> 있는 개체는 <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.TaskScheduler%2A> 속성이로 설정 <xref:System.Threading.Tasks.TaskScheduler.FromCurrentSynchronizationContext%2A?displayProperty=nameWithType>합니다.</span><span class="sxs-lookup"><span data-stu-id="dc5db-165">To accomplish this, during construction, these objects each provide a <xref:System.Threading.Tasks.Dataflow.ExecutionDataflowBlockOptions> object that has the <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.TaskScheduler%2A> property set to <xref:System.Threading.Tasks.TaskScheduler.FromCurrentSynchronizationContext%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="dc5db-166"><xref:System.Threading.Tasks.TaskScheduler.FromCurrentSynchronizationContext%2A?displayProperty=nameWithType> 메서드는 현재 동기화 컨텍스트에서 작업을 수행하는 <xref:System.Threading.Tasks.TaskScheduler> 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="dc5db-166">The <xref:System.Threading.Tasks.TaskScheduler.FromCurrentSynchronizationContext%2A?displayProperty=nameWithType> method creates a <xref:System.Threading.Tasks.TaskScheduler> object that performs work on the current synchronization context.</span></span> <span data-ttu-id="dc5db-167">`CreateImageProcessingNetwork` 메서드가 사용자 인터페이스 스레드에서 실행되는 **폴더 선택** 단추 처리기에서 호출되기 때문에 `displayCompositeBitmap` 및 `operationCancelled` 데이터 흐름 블록에 대한 작업도 사용자 인터페이스 스레드에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc5db-167">Because the `CreateImageProcessingNetwork` method is called from the handler of the **Choose Folder** button, which runs on the user-interface thread, the actions for the `displayCompositeBitmap` and `operationCancelled` dataflow blocks also run on the user-interface thread.</span></span>  
  
 <span data-ttu-id="dc5db-168">이 예에서는 공유 취소 토큰을 사용 하 여 설정 하는 대신는 <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.CancellationToken%2A> 속성 때문에 <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.CancellationToken%2A> 속성은 영구적으로 데이터 흐름 블록 실행을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc5db-168">This example uses a shared cancellation token instead of setting the <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.CancellationToken%2A> property because the <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.CancellationToken%2A> property permanently cancels dataflow block execution.</span></span> <span data-ttu-id="dc5db-169">이 예제에서는 취소 토큰을 통해 사용자가 하나 이상의 작업을 취소한 경우에도, 동일한 데이터 흐름 네트워크를 여러 번 재사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc5db-169">A cancellation token enables this example to reuse the same dataflow network multiple times, even when the user cancels one or more operations.</span></span> <span data-ttu-id="dc5db-170">사용 하는 예제에 대 한 <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.CancellationToken%2A> 영구적으로 데이터 흐름 블록의 실행을 취소 하려면 참조 [하는 방법: 데이터 흐름 블록 취소](../../../docs/standard/parallel-programming/how-to-cancel-a-dataflow-block.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="dc5db-170">For an example that uses <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.CancellationToken%2A> to permanently cancel the execution of a dataflow block, see [How to: Cancel a Dataflow Block](../../../docs/standard/parallel-programming/how-to-cancel-a-dataflow-block.md).</span></span>  
  
<a name="ui"></a>   
## <a name="connecting-the-dataflow-network-to-the-user-interface"></a><span data-ttu-id="dc5db-171">사용자 인터페이스에 데이터 흐름 네트워크 연결</span><span class="sxs-lookup"><span data-stu-id="dc5db-171">Connecting the Dataflow Network to the User Interface</span></span>  
 <span data-ttu-id="dc5db-172">이 섹션에서는 사용자 인터페이스에 데이터 흐름 네트워크를 연결하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="dc5db-172">This section describes how to connect the dataflow network to the user interface.</span></span> <span data-ttu-id="dc5db-173">복합 이미지 생성 및 작업 취소는 **폴더 선택** 및 **취소** 단추에서 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc5db-173">The creation of the composite image and cancellation of the operation are initiated from the **Choose Folder** and **Cancel** buttons.</span></span> <span data-ttu-id="dc5db-174">사용자가 이러한 단추 중 하나를 선택하면 해당 작업이 비동기식으로 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc5db-174">When the user chooses either of these buttons, the appropriate action is initiated in an asynchronous manner.</span></span>  
  
#### <a name="to-connect-the-dataflow-network-to-the-user-interface"></a><span data-ttu-id="dc5db-175">사용자 인터페이스에 데이터 흐름 네트워크를 연결하려면</span><span class="sxs-lookup"><span data-stu-id="dc5db-175">To Connect the Dataflow Network to the User Interface</span></span>  
  
1.  <span data-ttu-id="dc5db-176">기본 폼의 폼 디자이너에서에 대 한 이벤트 처리기를 만들고는 <xref:System.Windows.Forms.ToolStripItem.Click> 에 대 한 이벤트는 **폴더 선택** 단추입니다.</span><span class="sxs-lookup"><span data-stu-id="dc5db-176">On the form designer for the main form, create an event handler for the <xref:System.Windows.Forms.ToolStripItem.Click> event for the **Choose Folder** button.</span></span>  
  
2.  <span data-ttu-id="dc5db-177">구현 된 <xref:System.Windows.Forms.ToolStripItem.Click> 에 대 한 이벤트는 **폴더 선택** 단추입니다.</span><span class="sxs-lookup"><span data-stu-id="dc5db-177">Implement the <xref:System.Windows.Forms.ToolStripItem.Click> event for the **Choose Folder** button.</span></span>  
  
     [!code-csharp[TPLDataflow_CompositeImages#6](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_compositeimages/cs/compositeimages/form1.cs#6)]  
  
3.  <span data-ttu-id="dc5db-178">기본 폼의 폼 디자이너에서에 대 한 이벤트 처리기를 만들고는 <xref:System.Windows.Forms.ToolStripItem.Click> 에 대 한 이벤트는 **취소** 단추입니다.</span><span class="sxs-lookup"><span data-stu-id="dc5db-178">On the form designer for the main form, create an event handler for the <xref:System.Windows.Forms.ToolStripItem.Click> event for the **Cancel** button.</span></span>  
  
4.  <span data-ttu-id="dc5db-179">구현 된 <xref:System.Windows.Forms.ToolStripItem.Click> 에 대 한 이벤트는 **취소** 단추입니다.</span><span class="sxs-lookup"><span data-stu-id="dc5db-179">Implement the <xref:System.Windows.Forms.ToolStripItem.Click> event for the **Cancel** button.</span></span>  
  
     [!code-csharp[TPLDataflow_CompositeImages#7](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_compositeimages/cs/compositeimages/form1.cs#7)]  
  
<a name="complete"></a>   
## <a name="the-complete-example"></a><span data-ttu-id="dc5db-180">전체 예제</span><span class="sxs-lookup"><span data-stu-id="dc5db-180">The Complete Example</span></span>  
 <span data-ttu-id="dc5db-181">다음 예제에서는 이 연습의 전체 코드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="dc5db-181">The following example shows the complete code for this walkthrough.</span></span>  
  
 [!code-csharp[TPLDataflow_CompositeImages#100](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_compositeimages/cs/compositeimages/form1.cs#100)]  
  
 <span data-ttu-id="dc5db-182">다음 그림에서는 \Sample Pictures\ 공통 폴더에 대한 일반적인 출력을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="dc5db-182">The following illustration shows typical output for the common \Sample Pictures\ folder.</span></span>  
  
 <span data-ttu-id="dc5db-183">![Windows Forms 응용 프로그램](../../../docs/standard/parallel-programming/media/tpldataflow-compositeimages.gif "TPLDataflow_CompositeImages")</span><span class="sxs-lookup"><span data-stu-id="dc5db-183">![The Windows Forms Application](../../../docs/standard/parallel-programming/media/tpldataflow-compositeimages.gif "TPLDataflow_CompositeImages")</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="dc5db-184">다음 단계</span><span class="sxs-lookup"><span data-stu-id="dc5db-184">Next Steps</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc5db-185">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dc5db-185">See Also</span></span>  
 [<span data-ttu-id="dc5db-186">데이터 흐름</span><span class="sxs-lookup"><span data-stu-id="dc5db-186">Dataflow</span></span>](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)
