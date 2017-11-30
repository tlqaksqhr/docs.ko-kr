---
title: "방법: 바인딩된 컨트롤 만들기 및 표시된 데이터 형식 지정"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data [Windows Forms], formatting
- bound controls [Windows Forms], creating
- bound controls [Windows Forms], formatting data
ms.assetid: d5a56228-899d-41d9-8af8-87b3f4ec2f94
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a8c2836d841215ed3ca8e04461b1298cd41287de
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-bound-control-and-format-the-displayed-data"></a><span data-ttu-id="56ae5-102">방법: 바인딩된 컨트롤 만들기 및 표시된 데이터 형식 지정</span><span class="sxs-lookup"><span data-stu-id="56ae5-102">How to: Create a Bound Control and Format the Displayed Data</span></span>
<span data-ttu-id="56ae5-103">Windows Forms 데이터 바인딩 사용 하 여 데이터 바인딩된 컨트롤에 표시 되는 데이터의 서식을 지정할 수 있습니다는 **서식 지정 및 고급 바인딩** 대화 상자.</span><span class="sxs-lookup"><span data-stu-id="56ae5-103">With Windows Forms data binding, you can format the data displayed in a data-bound control by using the **Formatting and Advanced Binding** dialog box.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="56ae5-104">표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56ae5-104">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="56ae5-105">설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="56ae5-105">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="56ae5-106">자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="56ae5-106">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-bind-a-control-and-format-the-displayed-data"></a><span data-ttu-id="56ae5-107">컨트롤을 바인딩하고 표시된 데이터의 서식을 지정하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="56ae5-107">To bind a control and format the displayed data</span></span>  
  
1.  <span data-ttu-id="56ae5-108">데이터 소스에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="56ae5-108">Connect to a data source.</span></span>  
  
     <span data-ttu-id="56ae5-109">자세한 내용은 참조 [데이터 원본에 연결할](../../../docs/framework/data/adonet/connecting-to-a-data-source.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="56ae5-109">For more information, see [Connecting to a Data Source](../../../docs/framework/data/adonet/connecting-to-a-data-source.md).</span></span>  
  
2.  <span data-ttu-id="56ae5-110">폼에서 컨트롤을 선택하고 속성 창을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="56ae5-110">In the form, select the control, and then open the Properties window.</span></span>  
  
3.  <span data-ttu-id="56ae5-111">확장 된 **(DataBindings)** 속성을 선택한 다음는 **(고급)** 상자에서 줄임표 단추를 클릭 (![VisualStudioEllipsesButton 스크린 샷] (../../../docs/framework/winforms/media/vbellipsesbutton.png " vbEllipsesButton")) 표시 하는 **서식 지정 및 고급 바인딩** 해당 컨트롤에 대 한 속성의 전체 목록이 들어 있는 대화 상자.</span><span class="sxs-lookup"><span data-stu-id="56ae5-111">Expand the **(DataBindings)** property, and then in the **(Advanced)** box, click the ellipsis button (![VisualStudioEllipsesButton screenshot](../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) to display the **Formatting and Advanced Binding** dialog box, which has a complete list of properties for that control.</span></span>  
  
4.  <span data-ttu-id="56ae5-112">클릭 하 고 바인딩할 속성 선택 하 고 **바인딩** 화살표입니다.</span><span class="sxs-lookup"><span data-stu-id="56ae5-112">Select the property you want to bind, and then click the **Binding** arrow.</span></span>  
  
     <span data-ttu-id="56ae5-113">사용 가능한 데이터 소스 목록이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="56ae5-113">A list of available data sources is displayed.</span></span>  
  
5.  <span data-ttu-id="56ae5-114">원하는 단일 데이터 요소를 찾을 때까지 바인딩할 데이터 소스를 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="56ae5-114">Expand the data source you want to bind to until you find the single data element you want.</span></span>  
  
     <span data-ttu-id="56ae5-115">예를 들어 데이터 집합의 테이블에서 열 값에 바인딩할 경우 데이터 집합 이름을 확장하고 나서 테이블을 이름을 확장하여 열 이름을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="56ae5-115">For example, if you are binding to a column value in a dataset's table, expand the name of the dataset, and then expand the table name to display column names.</span></span>  
  
6.  <span data-ttu-id="56ae5-116">바인딩할 요소 이름을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="56ae5-116">Click the name of an element to bind to.</span></span>  
  
7.  <span data-ttu-id="56ae5-117">에 **형식의 서식을** 상자 컨트롤에 표시 되는 데이터에 적용할 형식을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="56ae5-117">In the **Format type** box, click the format you want to apply to the data displayed in the control.</span></span>  
  
     <span data-ttu-id="56ae5-118">모든 경우에 데이터 소스에 <xref:System.DBNull>이 있으면 컨트롤에 표시된 값을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56ae5-118">In every case, you can specify the value displayed in the control if the data source contains <xref:System.DBNull>.</span></span> <span data-ttu-id="56ae5-119">그러지 않으면 선택한 형식 유형에 따라 옵션이 약간 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="56ae5-119">Otherwise, the options vary slightly, depending on the format type you choose.</span></span> <span data-ttu-id="56ae5-120">다음 표에서는 형식 유형 및 옵션을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="56ae5-120">The following table shows the format types and options.</span></span>  
  
    |<span data-ttu-id="56ae5-121">형식 유형</span><span class="sxs-lookup"><span data-stu-id="56ae5-121">Format type</span></span>|<span data-ttu-id="56ae5-122">서식 지정 옵션</span><span class="sxs-lookup"><span data-stu-id="56ae5-122">Formatting option</span></span>|  
    |-----------------|-----------------------|  
    |<span data-ttu-id="56ae5-123">서식 없음</span><span class="sxs-lookup"><span data-stu-id="56ae5-123">No Formatting</span></span>|<span data-ttu-id="56ae5-124">옵션 없음.</span><span class="sxs-lookup"><span data-stu-id="56ae5-124">No options.</span></span>|  
    |<span data-ttu-id="56ae5-125">Numeric</span><span class="sxs-lookup"><span data-stu-id="56ae5-125">Numeric</span></span>|<span data-ttu-id="56ae5-126">소수 자릿수를 사용 하 여 지정 **소수 자릿수** up-down 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="56ae5-126">Specify number of decimal places by using **Decimal places** up-down control.</span></span>|  
    |<span data-ttu-id="56ae5-127">통화</span><span class="sxs-lookup"><span data-stu-id="56ae5-127">Currency</span></span>|<span data-ttu-id="56ae5-128">소수 자릿수를 사용 하 여 지정 **소수 자릿수** up-down 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="56ae5-128">Specify number of decimal places by using **Decimal places** up-down control.</span></span>|  
    |<span data-ttu-id="56ae5-129">날짜 시간</span><span class="sxs-lookup"><span data-stu-id="56ae5-129">Date Time</span></span>|<span data-ttu-id="56ae5-130">에 항목 중 하나를 선택 하 여 날짜 및 시간을 표시할 방법을 선택은 **형식** 선택 상자.</span><span class="sxs-lookup"><span data-stu-id="56ae5-130">Select how the date and time should be displayed by selecting one of the items in the **Type** selection box.</span></span>|  
    |<span data-ttu-id="56ae5-131">지수</span><span class="sxs-lookup"><span data-stu-id="56ae5-131">Scientific</span></span>|<span data-ttu-id="56ae5-132">소수 자릿수를 사용 하 여 지정 **소수 자릿수** up-down 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="56ae5-132">Specify number of decimal places by using **Decimal places** up-down control.</span></span>|  
    |<span data-ttu-id="56ae5-133">사용자 지정</span><span class="sxs-lookup"><span data-stu-id="56ae5-133">Custom</span></span>|<span data-ttu-id="56ae5-134">사용자 지정 서식 문자열 사용을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="56ae5-134">Specify a custom format string using.</span></span><br /><br /> <span data-ttu-id="56ae5-135">자세한 내용은 참조 [형식 지정](../../../docs/standard/base-types/formatting-types.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="56ae5-135">For more information, see [Formatting Types](../../../docs/standard/base-types/formatting-types.md).</span></span> <span data-ttu-id="56ae5-136">**참고:** 사용자 지정 형식 문자열은 데이터 소스와 바인딩된 컨트롤 간에 성공적으로 왕복 시간이 보장 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="56ae5-136">**Note:**  Custom format strings are not guaranteed to successfully round trip between the data source and bound control.</span></span> <span data-ttu-id="56ae5-137">대신에 바인딩에 대한 <xref:System.Windows.Forms.Binding.Parse> 또는 <xref:System.Windows.Forms.Binding.Format> 이벤트를 처리하고 이벤트 처리 코드에 사용자 지정 서식 지정을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="56ae5-137">Instead handle the <xref:System.Windows.Forms.Binding.Parse> or <xref:System.Windows.Forms.Binding.Format> event for the binding and apply custom formatting in the event-handling code.</span></span>|  
  
8.  <span data-ttu-id="56ae5-138">클릭 **확인** 를 닫으려면는 **서식 지정 및 고급 바인딩** 대화 상자 및 속성 창으로 돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="56ae5-138">Click **OK** to close the **Formatting and Advanced Binding** dialog box and return to the Properties window.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56ae5-139">참고 항목</span><span class="sxs-lookup"><span data-stu-id="56ae5-139">See Also</span></span>  
 [<span data-ttu-id="56ae5-140">방법: Windows Form에 단순 바인딩된 컨트롤 만들기</span><span class="sxs-lookup"><span data-stu-id="56ae5-140">How to: Create a Simple-Bound Control on a Windows Form</span></span>](../../../docs/framework/winforms/how-to-create-a-simple-bound-control-on-a-windows-form.md)  
 [<span data-ttu-id="56ae5-141">Windows Forms에서 사용자 입력 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="56ae5-141">User Input Validation in Windows Forms</span></span>](../../../docs/framework/winforms/user-input-validation-in-windows-forms.md)  
 [<span data-ttu-id="56ae5-142">Windows Forms 데이터 바인딩</span><span class="sxs-lookup"><span data-stu-id="56ae5-142">Windows Forms Data Binding</span></span>](../../../docs/framework/winforms/windows-forms-data-binding.md)
