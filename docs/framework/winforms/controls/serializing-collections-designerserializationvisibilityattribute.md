---
title: '연습: DesignerSerializationVisibilityAttribute를 사용하여 표준 형식의 컬렉션 serialize'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- serialization [Windows Forms], collections
- standard types [Windows Forms], collections
- collections [Windows Forms], serializing
- collections [Windows Forms], standard types
ms.assetid: 020c9df4-fdc5-4dae-815a-963ecae5668c
ms.openlocfilehash: a502ecc30911f2296bf48eaa195f5b6452b7588a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33541300"
---
# <a name="walkthrough-serializing-collections-of-standard-types-with-the-designerserializationvisibilityattribute"></a><span data-ttu-id="26412-102">연습: DesignerSerializationVisibilityAttribute를 사용하여 표준 형식의 컬렉션 serialize</span><span class="sxs-lookup"><span data-stu-id="26412-102">Walkthrough: Serializing Collections of Standard Types with the DesignerSerializationVisibilityAttribute</span></span>
<span data-ttu-id="26412-103">사용자 지정 컨트롤 노출 하는 속성으로 컬렉션 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26412-103">Your custom controls will sometimes expose a collection as a property.</span></span> <span data-ttu-id="26412-104">이 연습에서는 사용 하는 방법을 보여 줍니다.는 <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute> 디자인 타임에 컬렉션을 serialize 하는 방법을 제어 하는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="26412-104">This walkthrough demonstrates how to use the <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute> class to control how a collection is serialized at design time.</span></span> <span data-ttu-id="26412-105">적용 된 <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content> 컬렉션 속성에 값을 입력 하면 속성을 serialize 합니다.</span><span class="sxs-lookup"><span data-stu-id="26412-105">Applying the <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content> value to your collection property ensures that the property will be serialized.</span></span>  
  
 <span data-ttu-id="26412-106">단일 목록으로이 항목의 코드를 복사 하려면 참조 [하는 방법: serialize 할 컬렉션의 표준 형식과 DesignerSerializationVisibilityAttribute](http://msdn.microsoft.com/library/7829fcdd-8205-405f-8231-a1282a9835c9)합니다.</span><span class="sxs-lookup"><span data-stu-id="26412-106">To copy the code in this topic as a single listing, see [How to: Serialize Collections of Standard Types with the DesignerSerializationVisibilityAttribute](http://msdn.microsoft.com/library/7829fcdd-8205-405f-8231-a1282a9835c9).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="26412-107">표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26412-107">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="26412-108">설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="26412-108">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="26412-109">자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="26412-109">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="26412-110">전제 조건</span><span class="sxs-lookup"><span data-stu-id="26412-110">Prerequisites</span></span>  
 <span data-ttu-id="26412-111">이 연습을 완료하려면 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="26412-111">In order to complete this walkthrough, you will need:</span></span>  
  
-   <span data-ttu-id="26412-112">충분 한 권한이을 만들고 Visual Studio가 설치 된 컴퓨터에서 Windows Forms 응용 프로그램 프로젝트를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26412-112">Sufficient permissions to be able to create and run Windows Forms application projects on the computer where Visual Studio is installed.</span></span>  
  
## <a name="creating-a-control-that-has-a-serializable-collection"></a><span data-ttu-id="26412-113">직렬화 가능 컬렉션을 포함 하는 컨트롤 만들기</span><span class="sxs-lookup"><span data-stu-id="26412-113">Creating a Control That Has a Serializable Collection</span></span>  
 <span data-ttu-id="26412-114">첫 번째 단계는 컨트롤을 속성으로 직렬화 가능 컬렉션을 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="26412-114">The first step is to create a control that has a serializable collection as a property.</span></span> <span data-ttu-id="26412-115">사용 하 여이 컬렉션의 내용을 편집할 수는 **컬렉션 편집기**에서 액세스할 수 있는 **속성** 창.</span><span class="sxs-lookup"><span data-stu-id="26412-115">You can edit the contents of this collection using the **Collection Editor**, which you can access from the **Properties** window.</span></span>  
  
#### <a name="to-create-a-control-with-a-serializable-collection"></a><span data-ttu-id="26412-116">직렬화 가능 컬렉션을 사용 하 여 컨트롤을 만들려면</span><span class="sxs-lookup"><span data-stu-id="26412-116">To create a control with a serializable collection</span></span>  
  
1.  <span data-ttu-id="26412-117">라는 Windows 컨트롤 라이브러리 프로젝트 만들기 `SerializationDemoControlLib`합니다.</span><span class="sxs-lookup"><span data-stu-id="26412-117">Create a Windows Control Library project called `SerializationDemoControlLib`.</span></span> <span data-ttu-id="26412-118">자세한 내용은 참조 [Windows 컨트롤 라이브러리 템플릿](http://msdn.microsoft.com/library/722f4e2d-1310-4ed5-8f33-593337ab66b4)합니다.</span><span class="sxs-lookup"><span data-stu-id="26412-118">For more information, see [Windows Control Library Template](http://msdn.microsoft.com/library/722f4e2d-1310-4ed5-8f33-593337ab66b4).</span></span>  
  
2.  <span data-ttu-id="26412-119">이름 바꾸기 `UserControl1` 를 `SerializationDemoControl`합니다.</span><span class="sxs-lookup"><span data-stu-id="26412-119">Rename `UserControl1` to `SerializationDemoControl`.</span></span> <span data-ttu-id="26412-120">자세한 내용은 참조 [하는 방법: 식별자 이름 바꾸기](http://msdn.microsoft.com/library/2430f732-2b70-4516-8cf6-a7bb71cc9724)합니다.</span><span class="sxs-lookup"><span data-stu-id="26412-120">For more information, see [How to: Rename Identifiers](http://msdn.microsoft.com/library/2430f732-2b70-4516-8cf6-a7bb71cc9724).</span></span>  
  
3.  <span data-ttu-id="26412-121">에 **속성** 창의 설정의 값은 <xref:System.Windows.Forms.Padding.All%2A?displayProperty=nameWithType> 속성을 `10`합니다.</span><span class="sxs-lookup"><span data-stu-id="26412-121">In the **Properties** window, set the value of the <xref:System.Windows.Forms.Padding.All%2A?displayProperty=nameWithType> property to `10`.</span></span>  
  
4.  <span data-ttu-id="26412-122">위치는 <xref:System.Windows.Forms.TextBox> 컨트롤에 `SerializationDemoControl`합니다.</span><span class="sxs-lookup"><span data-stu-id="26412-122">Place a <xref:System.Windows.Forms.TextBox> control in the `SerializationDemoControl`.</span></span>  
  
5.  <span data-ttu-id="26412-123"><xref:System.Windows.Forms.TextBox> 컨트롤을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="26412-123">Select the <xref:System.Windows.Forms.TextBox> control.</span></span> <span data-ttu-id="26412-124">에 **속성** 창에서 다음 속성을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="26412-124">In the **Properties** window, set the following properties.</span></span>  
  
    |<span data-ttu-id="26412-125">속성</span><span class="sxs-lookup"><span data-stu-id="26412-125">Property</span></span>|<span data-ttu-id="26412-126">다음으로 변경</span><span class="sxs-lookup"><span data-stu-id="26412-126">Change to</span></span>|  
    |--------------|---------------|  
    |<span data-ttu-id="26412-127">**Multiline**</span><span class="sxs-lookup"><span data-stu-id="26412-127">**Multiline**</span></span>|`true`|  
    |<span data-ttu-id="26412-128">**도킹**</span><span class="sxs-lookup"><span data-stu-id="26412-128">**Dock**</span></span>|<xref:System.Windows.Forms.DockStyle.Fill>|  
    |<span data-ttu-id="26412-129">**스크롤 막대**</span><span class="sxs-lookup"><span data-stu-id="26412-129">**ScrollBars**</span></span>|<xref:System.Windows.Forms.ScrollBars.Vertical>|  
    |<span data-ttu-id="26412-130">**ReadOnly**</span><span class="sxs-lookup"><span data-stu-id="26412-130">**ReadOnly**</span></span>|`true`|  
  
6.  <span data-ttu-id="26412-131">에 **코드 편집기**, 라는 문자열 배열 필드를 선언 `stringsValue` 에서 `SerializationDemoControl`합니다.</span><span class="sxs-lookup"><span data-stu-id="26412-131">In the **Code Editor**, declare a string array field named `stringsValue` in `SerializationDemoControl`.</span></span>  
  
     [!code-cpp[System.ComponentModel.DesignerSerializationVisibilityAttribute#4](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/cpp/form1.cpp#4)]
     [!code-csharp[System.ComponentModel.DesignerSerializationVisibilityAttribute#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/CS/form1.cs#4)]
     [!code-vb[System.ComponentModel.DesignerSerializationVisibilityAttribute#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/VB/form1.vb#4)]  
  
7.  <span data-ttu-id="26412-132">정의 `Strings` 속성에는 `SerializationDemoControl`합니다.</span><span class="sxs-lookup"><span data-stu-id="26412-132">Define the `Strings` property on the `SerializationDemoControl`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="26412-133"><xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content> 값 컬렉션의 serialization을 사용 하도록 설정 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="26412-133">The <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content> value is used to enable serialization of the collection.</span></span>  
  
 [!code-cpp[System.ComponentModel.DesignerSerializationVisibilityAttribute#5](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/cpp/form1.cpp#5)]
 [!code-csharp[System.ComponentModel.DesignerSerializationVisibilityAttribute#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/CS/form1.cs#5)]
 [!code-vb[System.ComponentModel.DesignerSerializationVisibilityAttribute#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/VB/form1.vb#5)]  
  
1.  <span data-ttu-id="26412-134">F5 키를 눌러 프로젝트를 빌드하고 **UserControl 테스트 컨테이너**에서 컨트롤을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="26412-134">Press F5 to build the project and run your control in the **UserControl Test Container**.</span></span>  
  
2.  <span data-ttu-id="26412-135">찾을 `Strings` 속성에는 <xref:System.Windows.Forms.PropertyGrid> 의 **UserControl Test Container**합니다.</span><span class="sxs-lookup"><span data-stu-id="26412-135">Find the `Strings` property in the <xref:System.Windows.Forms.PropertyGrid> of the **UserControl Test Container**.</span></span> <span data-ttu-id="26412-136">클릭는 `Strings` 속성을 다음 줄임표 (![VisualStudioEllipsesButton 스크린 샷](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) 버튼을 클릭은 **문자열컬렉션편집기**.</span><span class="sxs-lookup"><span data-stu-id="26412-136">Click the `Strings` property, then click the ellipsis (![VisualStudioEllipsesButton screenshot](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) button to open the **String Collection Editor**.</span></span>  
  
3.  <span data-ttu-id="26412-137">여러 문자열을 입력에서 **문자열 컬렉션 편집기**합니다.</span><span class="sxs-lookup"><span data-stu-id="26412-137">Enter several strings in the **String Collection Editor**.</span></span> <span data-ttu-id="26412-138">각 문자열의 끝에서 ENTER 키를 눌러 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="26412-138">Separate them by pressing the ENTER key at the end of each string.</span></span> <span data-ttu-id="26412-139">클릭 **확인** 문자열 입력 했으면 합니다.</span><span class="sxs-lookup"><span data-stu-id="26412-139">Click **OK** when you are finished entering strings.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="26412-140">입력 문자열에 표시 된 <xref:System.Windows.Forms.TextBox> 의 `SerializationDemoControl`합니다.</span><span class="sxs-lookup"><span data-stu-id="26412-140">The strings you typed appear in the <xref:System.Windows.Forms.TextBox> of the `SerializationDemoControl`.</span></span>  
  
## <a name="serializing-a-collection-property"></a><span data-ttu-id="26412-141">컬렉션 속성을 직렬화합니다.</span><span class="sxs-lookup"><span data-stu-id="26412-141">Serializing a Collection Property</span></span>  
 <span data-ttu-id="26412-142">컨트롤의 serialization 동작을 테스트 하려면 폼에 배치를 사용 하 여 컬렉션의 내용을 변경 하는 **컬렉션 편집기**합니다.</span><span class="sxs-lookup"><span data-stu-id="26412-142">To test the serialization behavior of your control, you will place it on a form and change the contents of the collection with the **Collection Editor**.</span></span> <span data-ttu-id="26412-143">특별 한 디자이너 파일을 확인 하 여 직렬화 된 컬렉션 상태를 볼 수는 **Windows Forms 디자이너** 에서 코드를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="26412-143">You can see the serialized collection state by looking at a special designer file, into which the **Windows Forms Designer** emits code.</span></span>  
  
#### <a name="to-serialize-a-collection"></a><span data-ttu-id="26412-144">컬렉션을 serialize 하는 데</span><span class="sxs-lookup"><span data-stu-id="26412-144">To serialize a collection</span></span>  
  
1.  <span data-ttu-id="26412-145">Windows 응용 프로그램 프로젝트를 솔루션에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="26412-145">Add a Windows Application project to the solution.</span></span> <span data-ttu-id="26412-146">프로젝트 이름을 `SerializationDemoControlTest`로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="26412-146">Name the project `SerializationDemoControlTest`.</span></span>  
  
2.  <span data-ttu-id="26412-147">에 **도구 상자**, 이라는 탭 찾을 **SerializationDemoControlLib 구성 요소**합니다.</span><span class="sxs-lookup"><span data-stu-id="26412-147">In the **Toolbox**, find the tab named **SerializationDemoControlLib Components**.</span></span> <span data-ttu-id="26412-148">이 탭에서 찾을 수 있습니다는 `SerializationDemoControl`합니다.</span><span class="sxs-lookup"><span data-stu-id="26412-148">In this tab, you will find the `SerializationDemoControl`.</span></span> <span data-ttu-id="26412-149">자세한 내용은 [연습: 도구 상자에 자동으로 사용자 지정 구성 요소 채우기](../../../../docs/framework/winforms/controls/walkthrough-automatically-populating-the-toolbox-with-custom-components.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="26412-149">For more information, see [Walkthrough: Automatically Populating the Toolbox with Custom Components](../../../../docs/framework/winforms/controls/walkthrough-automatically-populating-the-toolbox-with-custom-components.md).</span></span>  
  
3.  <span data-ttu-id="26412-150">위치는 `SerializationDemoControl` 폼에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26412-150">Place a `SerializationDemoControl` on your form.</span></span>  
  
4.  <span data-ttu-id="26412-151">찾을 `Strings` 속성에는 **속성** 창.</span><span class="sxs-lookup"><span data-stu-id="26412-151">Find the `Strings` property in the **Properties** window.</span></span> <span data-ttu-id="26412-152">클릭는 `Strings` 속성을 다음 줄임표 (![VisualStudioEllipsesButton 스크린 샷](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) 버튼을 클릭은 **문자열컬렉션편집기**.</span><span class="sxs-lookup"><span data-stu-id="26412-152">Click the `Strings` property, then click the ellipsis (![VisualStudioEllipsesButton screenshot](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) button to open the **String Collection Editor**.</span></span>  
  
5.  <span data-ttu-id="26412-153">여러 문자열을 입력에서 **문자열 컬렉션 편집기**합니다.</span><span class="sxs-lookup"><span data-stu-id="26412-153">Type several strings in the **String Collection Editor**.</span></span> <span data-ttu-id="26412-154">각 문자열의 끝에서 ENTER 키를 눌러 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="26412-154">Separate them by pressing the ENTER key at the end of each string.</span></span> <span data-ttu-id="26412-155">클릭 **확인** 문자열 입력 했으면 합니다.</span><span class="sxs-lookup"><span data-stu-id="26412-155">Click **OK** when you are finished entering strings.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="26412-156">입력 문자열에 표시 된 <xref:System.Windows.Forms.TextBox> 의 `SerializationDemoControl`합니다.</span><span class="sxs-lookup"><span data-stu-id="26412-156">The strings you typed appear in the <xref:System.Windows.Forms.TextBox> of the `SerializationDemoControl`.</span></span>  
  
1.  <span data-ttu-id="26412-157">**솔루션 탐색기**에서 **모든 파일 표시** 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="26412-157">In **Solution Explorer**, click the **Show All Files** button.</span></span>  
  
2.  <span data-ttu-id="26412-158">열기는 **Form1** 노드.</span><span class="sxs-lookup"><span data-stu-id="26412-158">Open the **Form1** node.</span></span> <span data-ttu-id="26412-159">아래에 라는 파일을은 **form1. designer.cs** 또는 **Form1.Designer.vb**합니다.</span><span class="sxs-lookup"><span data-stu-id="26412-159">Beneath it is a file called **Form1.Designer.cs** or **Form1.Designer.vb**.</span></span> <span data-ttu-id="26412-160">이 파일을는 **Windows Forms 디자이너** 에서 폼과 해당 자식 컨트롤의 디자인 타임 상태를 나타내는 코드를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="26412-160">This is the file into which the **Windows Forms Designer** emits code representing the design-time state of your form and its child controls.</span></span> <span data-ttu-id="26412-161">**코드 편집기**에서 이 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="26412-161">Open this file in the **Code Editor**.</span></span>  
  
3.  <span data-ttu-id="26412-162">라는 영역을 열고 **Windows Form 디자이너에서 생성 한 코드** 라는 섹션을 찾아서 **serializationDemoControl1**합니다.</span><span class="sxs-lookup"><span data-stu-id="26412-162">Open the region called **Windows Form Designer generated code** and find the section labeled **serializationDemoControl1**.</span></span> <span data-ttu-id="26412-163">이 레이블은 아래에 컨트롤의 serialize 된 상태를 나타내는 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="26412-163">Beneath this label is the code representing the serialized state of your control.</span></span> <span data-ttu-id="26412-164">5 단계에서 입력 문자열에 대 한 할당에 표시 된 `Strings` 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="26412-164">The strings you typed in step 5 appear in an assignment to the `Strings` property.</span></span> <span data-ttu-id="26412-165">C# 및 Visual Basic의 경우 다음 코드 예제에서는 표시 되는 내용 문자열 "red", "주황색" 및 "노란색"를 입력 한 경우 유사한 코드를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="26412-165">The following code examples in C# and Visual Basic, show code similar to what you will see if you typed the strings "red", "orange", and "yellow".</span></span>  
  
    ```csharp  
    this.serializationDemoControl1.Strings = new string[] {  
            "red",  
            "orange",  
            "yellow"};  
    ```  
    
    ```vb  
    Me.serializationDemoControl1.Strings = New String() {"red", "orange", "yellow"}  
    ```
  
4.  <span data-ttu-id="26412-166">에 **코드 편집기**의 값을 변경는 <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute> 에 `Strings` 속성을 <xref:System.ComponentModel.DesignerSerializationVisibility.Hidden>합니다.</span><span class="sxs-lookup"><span data-stu-id="26412-166">In the **Code Editor**, change the value of the <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute> on the `Strings` property to <xref:System.ComponentModel.DesignerSerializationVisibility.Hidden>.</span></span>  
  
    ```csharp  
    [DesignerSerializationVisibility(DesignerSerializationVisibility.Hidden)]  
    ```  
    ```vb  
    <DesignerSerializationVisibility(DesignerSerializationVisibility.Hidden)> _  
    ```  
  
5. <span data-ttu-id="26412-167">솔루션 및 3 및 4 단계를 반복 하 여 다시 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="26412-167">Rebuild the solution and repeat steps 3 and 4.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="26412-168">이 경우에 **Windows Forms 디자이너** 에 대 한 할당을 내보내는 `Strings` 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="26412-168">In this case, the **Windows Forms Designer** emits no assignment to the `Strings` property.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="26412-169">다음 단계</span><span class="sxs-lookup"><span data-stu-id="26412-169">Next Steps</span></span>  
 <span data-ttu-id="26412-170">표준 형식의 컬렉션을 serialize 하는 방법을 알게 되 면 디자인 타임 환경에 사용자 지정 컨트롤을 보다 강력 하 게 통합 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="26412-170">Once you know how to serialize a collection of standard types, consider integrating your custom controls more deeply into the design-time environment.</span></span> <span data-ttu-id="26412-171">다음 항목에는 사용자 지정 컨트롤의 디자인 타임 통합 향상 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="26412-171">The following topics describe how to enhance the design-time integration of your custom controls:</span></span>  
  
-   [<span data-ttu-id="26412-172">디자인 타임 아키텍처</span><span class="sxs-lookup"><span data-stu-id="26412-172">Design-Time Architecture</span></span>](http://msdn.microsoft.com/library/4881917b-628f-4689-b872-472e4f8a4e3a)  
  
-   [<span data-ttu-id="26412-173">Windows Forms 컨트롤의 특성</span><span class="sxs-lookup"><span data-stu-id="26412-173">Attributes in Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/attributes-in-windows-forms-controls.md)  
  
-   [<span data-ttu-id="26412-174">Serialization 디자이너 개요</span><span class="sxs-lookup"><span data-stu-id="26412-174">Designer Serialization Overview</span></span>](http://msdn.microsoft.com/library/c342635a-aa5f-4281-915b-b013738af15a)  
  
-   [<span data-ttu-id="26412-175">연습: Visual Studio의 디자인 타임 기능을 사용하는 Windows Forms 컨트롤 만들기</span><span class="sxs-lookup"><span data-stu-id="26412-175">Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features</span></span>](../../../../docs/framework/winforms/controls/creating-a-wf-control-design-time-features.md)  
  
## <a name="see-also"></a><span data-ttu-id="26412-176">참고 항목</span><span class="sxs-lookup"><span data-stu-id="26412-176">See Also</span></span>  
 <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute>  
 [<span data-ttu-id="26412-177">Serialization 디자이너 개요</span><span class="sxs-lookup"><span data-stu-id="26412-177">Designer Serialization Overview</span></span>](http://msdn.microsoft.com/library/c342635a-aa5f-4281-915b-b013738af15a)  
 [<span data-ttu-id="26412-178">방법: designerserializationvisibilityattribute를 사용 하 여 표준 형식의 컬렉션 Serialize</span><span class="sxs-lookup"><span data-stu-id="26412-178">How to: Serialize Collections of Standard Types with the DesignerSerializationVisibilityAttribute</span></span>](http://msdn.microsoft.com/library/7829fcdd-8205-405f-8231-a1282a9835c9)  
 [<span data-ttu-id="26412-179">연습: 도구 상자에 자동으로 사용자 지정 구성 요소 채우기</span><span class="sxs-lookup"><span data-stu-id="26412-179">Walkthrough: Automatically Populating the Toolbox with Custom Components</span></span>](../../../../docs/framework/winforms/controls/walkthrough-automatically-populating-the-toolbox-with-custom-components.md)
