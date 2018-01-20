---
title: "방법: Windows Form에 단순 바인딩된 컨트롤 만들기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data binding [Windows Forms], simple data binding
- Windows Forms controls, data binding
ms.assetid: 3bcaded8-0f1a-4cc0-8830-f59be253bf4e
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 887f5cd89e52cf91c4e18fab5c97f82cba9a5b85
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-create-a-simple-bound-control-on-a-windows-form"></a><span data-ttu-id="d8d45-102">방법: Windows Form에 단순 바인딩된 컨트롤 만들기</span><span class="sxs-lookup"><span data-stu-id="d8d45-102">How to: Create a Simple-Bound Control on a Windows Form</span></span>
<span data-ttu-id="d8d45-103">와 *단순 바인딩*, 컨트롤에서 데이터 집합 테이블에서 열 값과 같은 단일 데이터 요소를 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8d45-103">With *simple binding*, you can display a single data element, such as a column value from a dataset table, in a control.</span></span> <span data-ttu-id="d8d45-104">컨트롤의 속성을 데이터 값에 단순 바인딩할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8d45-104">You can simple-bind any property of a control to a data value.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d8d45-105">표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8d45-105">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="d8d45-106">설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d8d45-106">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="d8d45-107">자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d8d45-107">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-simple-bind-a-control"></a><span data-ttu-id="d8d45-108">단순 컨트롤을 바인딩</span><span class="sxs-lookup"><span data-stu-id="d8d45-108">To simple-bind a control</span></span>  
  
1.  <span data-ttu-id="d8d45-109">데이터 소스에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="d8d45-109">Connect to a data source.</span></span> <span data-ttu-id="d8d45-110">자세한 내용은 참조 [데이터 원본에 연결할](../../../docs/framework/data/adonet/connecting-to-a-data-source.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d8d45-110">For more information, see [Connecting to a Data Source](../../../docs/framework/data/adonet/connecting-to-a-data-source.md).</span></span>  
  
2.  <span data-ttu-id="d8d45-111">양식에서 컨트롤을 선택 하 고 표시 된 **속성** 창.</span><span class="sxs-lookup"><span data-stu-id="d8d45-111">In the form, select the control and display the **Properties** window.</span></span>  
  
3.  <span data-ttu-id="d8d45-112">확장 된 **(DataBindings)** 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="d8d45-112">Expand the **(DataBindings)** property.</span></span>  
  
     <span data-ttu-id="d8d45-113">가장 자주 바인딩된 속성 아래에 표시 됩니다는 **(DataBindings)** 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="d8d45-113">The properties most often bound are displayed underneath the **(DataBindings)** property.</span></span> <span data-ttu-id="d8d45-114">예를 들어 대부분의 컨트롤에에서는 **텍스트** 속성이 바인딩되는 가장 자주 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8d45-114">For example, in most controls, the **Text** property is most frequently bound.</span></span>  
  
4.  <span data-ttu-id="d8d45-115">속성 하려는 경우 바인딩 중 하나가 아닙니다 일반적인 바인딩된 속성을 클릭는 **줄임표** 단추 (![VisualStudioEllipsesButton 스크린 샷](../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton") )에 **(고급)** 상자를 표시 하려면는 **서식 지정 및 고급 바인딩** 해당 컨트롤에 대 한 속성의 전체 목록을 대화 상자.</span><span class="sxs-lookup"><span data-stu-id="d8d45-115">If the property you want to bind is not one of the commonly bound properties, click the **Ellipsis** button (![VisualStudioEllipsesButton screenshot](../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) in the **(Advanced)** box to display the **Formatting and Advanced Binding** dialog box with a complete list of properties for that control.</span></span>  
  
5.  <span data-ttu-id="d8d45-116">바인딩하고 아래의 드롭다운 화살표를 클릭 하 고 원하는 속성을 선택 **바인딩**합니다.</span><span class="sxs-lookup"><span data-stu-id="d8d45-116">Select the property you want to bind and click the drop-down arrow under **Binding**.</span></span>  
  
     <span data-ttu-id="d8d45-117">사용 가능한 데이터 소스 목록이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8d45-117">A list of available data sources is displayed.</span></span>  
  
6.  <span data-ttu-id="d8d45-118">원하는 단일 데이터 요소를 찾을 때까지 바인딩할 데이터 소스를 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="d8d45-118">Expand the data source you want to bind to until you find the single data element you want.</span></span> <span data-ttu-id="d8d45-119">예를 들어 데이터 집합의 테이블에서 열 값에 바인딩할 경우 데이터 집합 이름을 확장하고 나서 테이블을 이름을 확장하여 열 이름을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="d8d45-119">For example, if you are binding to a column value in a dataset's table, expand the name of the dataset, and then expand the table name to display column names.</span></span>  
  
7.  <span data-ttu-id="d8d45-120">바인딩할 요소 이름을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d8d45-120">Click the name of an element to bind to.</span></span>  
  
8.  <span data-ttu-id="d8d45-121">작업 하는 경우는 **서식 지정 및 고급 바인딩** 대화 상자를 클릭 **확인** 돌아가려면는 **속성** 창.</span><span class="sxs-lookup"><span data-stu-id="d8d45-121">If you were working in the **Formatting and Advanced Binding** dialog box, click **OK** to return to the **Properties** window.</span></span>  
  
9. <span data-ttu-id="d8d45-122">컨트롤의 추가 속성을 바인딩할 경우 3-7 단계를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8d45-122">If you want to bind additional properties of the control, repeat steps 3 through 7.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d8d45-123">되기 때문에 단순 바인딩된 컨트롤에는 하나의 데이터 요소만 표시 Windows Form을 단순 바인딩된 컨트롤에서 탐색 논리를 포함 하는 매우 일반적인.</span><span class="sxs-lookup"><span data-stu-id="d8d45-123">Because simple-bound controls show only a single data element, it is very typical to include navigation logic in a Windows Form with simple-bound controls.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8d45-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d8d45-124">See Also</span></span>  
 <xref:System.Windows.Forms.Binding>  
 [<span data-ttu-id="d8d45-125">Windows Forms 데이터 바인딩</span><span class="sxs-lookup"><span data-stu-id="d8d45-125">Windows Forms Data Binding</span></span>](../../../docs/framework/winforms/windows-forms-data-binding.md)  
 [<span data-ttu-id="d8d45-126">데이터 바인딩 및 Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d8d45-126">Data Binding and Windows Forms</span></span>](../../../docs/framework/winforms/data-binding-and-windows-forms.md)
