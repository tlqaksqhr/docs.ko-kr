---
title: '방법: MDI 자식 폼 정렬'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- child forms [Windows Forms], arranging
- MDI [Windows Forms], arranging child forms
ms.assetid: a0786378-3206-4ccc-898e-7d3b38cc5089
ms.openlocfilehash: d5c0d24ff8a7188a669c218ce8b0dc66ffa56c47
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33521029"
---
# <a name="how-to-arrange-mdi-child-forms"></a><span data-ttu-id="3f511-102">방법: MDI 자식 폼 정렬</span><span class="sxs-lookup"><span data-stu-id="3f511-102">How to: Arrange MDI Child Forms</span></span>
<span data-ttu-id="3f511-103">응용 프로그램에는 바둑판식 배열, 계단식 배열, 정렬 등 열려 있는 MDI 자식 폼의 레이아웃을 제어하는 작업을 위한 메뉴 명령이 있는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="3f511-103">Often, applications will have menu commands for actions such as Tile, Cascade, and Arrange, which control the layout of the open MDI child forms.</span></span> <span data-ttu-id="3f511-104"><xref:System.Windows.Forms.Form.LayoutMdi%2A> 메서드를 <xref:System.Windows.Forms.MdiLayout> 열거형 값 중 하나와 함께 사용하여 MDI 부모 폼에서 자식 폼을 다시 정렬할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f511-104">You can use the <xref:System.Windows.Forms.Form.LayoutMdi%2A> method with one of the <xref:System.Windows.Forms.MdiLayout> enumeration values to rearrange the child forms in an MDI parent form.</span></span>  
  
 <span data-ttu-id="3f511-105"><xref:System.Windows.Forms.MdiLayout> 열거형 값은 자식 폼을 계단식으로, 가로/세로 바둑판식으로 또는 MDI 폼 아래쪽에 정렬된 자식 폼 아이콘으로 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="3f511-105">The <xref:System.Windows.Forms.MdiLayout> enumeration values display child forms as cascading, as horizontally or vertically tiled, or as child form icons arranged along the lower portion of the MDI form.</span></span> <span data-ttu-id="3f511-106">이러한 값 Windows 명령 것과 동일한 효과가 **계단식 창 배열**, **windows 나란히 표시**, **창 가로 정렬 보기**, 및 **바탕 화면 보기** 각각.</span><span class="sxs-lookup"><span data-stu-id="3f511-106">These values have the same effect as the Windows commands **Cascade windows**, **Show windows side by side**, **Show windows stacked**, and **Show the desktop**, respectively.</span></span>  
  
 <span data-ttu-id="3f511-107">이러한 메서드는 메뉴 항목의 <xref:System.Windows.Forms.Control.Click> 이벤트에 의해 호출되는 이벤트 처리기로 사용되는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="3f511-107">Often, these methods are used as the event handlers called by a menu item's <xref:System.Windows.Forms.Control.Click> event.</span></span> <span data-ttu-id="3f511-108">이러한 방식을 통해 "계단식 창 배열" 텍스트가 포함된 메뉴 항목이 MDI 자식 창에서 적절하게 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f511-108">In this way, a menu item with the text "Cascade Windows" can have the desired effect on the MDI child windows.</span></span>  
  
### <a name="to-arrange-child-forms"></a><span data-ttu-id="3f511-109">자식 폼을 정렬하려면</span><span class="sxs-lookup"><span data-stu-id="3f511-109">To arrange child forms</span></span>  
  
1.  <span data-ttu-id="3f511-110">메서드에서 <xref:System.Windows.Forms.Form.LayoutMdi%2A> 메서드를 사용하여 MDI 부모 폼의 <xref:System.Windows.Forms.MdiLayout> 열거형을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="3f511-110">In a method, use the <xref:System.Windows.Forms.Form.LayoutMdi%2A> method to set the <xref:System.Windows.Forms.MdiLayout> enumeration for the MDI parent form.</span></span> <span data-ttu-id="3f511-111">다음 예제에서는 MDI 부모 폼(<xref:System.Windows.Forms.MdiLayout.Cascade?displayProperty=nameWithType>)의 자식 창에 대해 `Form1` 열거형 값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3f511-111">The following example uses the <xref:System.Windows.Forms.MdiLayout.Cascade?displayProperty=nameWithType> enumeration value for the child windows of the MDI parent form (`Form1`).</span></span> <span data-ttu-id="3f511-112">열거형에 대 한 이벤트 처리기에서 코드에 사용 되는 <xref:System.Windows.Forms.Control.Click> 의 이벤트는 **계단식 창 배열** 메뉴 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="3f511-112">The enumeration is used in code during the event handler for the <xref:System.Windows.Forms.Control.Click> event of the **Cascade Windows** menu item.</span></span>  
  
    ```vb  
    Protected Sub CascadeWindows_Click(ByVal sender As System.Object, ByVal e As System.EventArgs)  
       Me.LayoutMdi(System.Windows.Forms.MdiLayout.Cascade)  
    End Sub  
    ```  
  
    ```csharp  
    protected void CascadeWindows_Click(object sender, System.EventArgs e){  
       this.LayoutMdi(System.Windows.Forms.MdiLayout.Cascade);  
    }  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="3f511-113">사용되는 <xref:System.Windows.Forms.MdiLayout> 열거형 값을 변경하여 창을 바둑판식으로 배열하고 아이콘으로 정렬할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f511-113">You can also tile windows and arranging windows as icons by changing the <xref:System.Windows.Forms.MdiLayout> enumeration value used.</span></span>  
  
2.  <span data-ttu-id="3f511-114">Visual C#을 사용하는 경우 폼 생성자에 다음 코드를 추가하여 이벤트 처리기를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="3f511-114">If you’re using Visual C#, place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="3f511-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3f511-115">See Also</span></span>  
 [<span data-ttu-id="3f511-116">MDI(다중 문서 인터페이스) 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="3f511-116">Multiple-Document Interface (MDI) Applications</span></span>](../../../../docs/framework/winforms/advanced/multiple-document-interface-mdi-applications.md)  
 [<span data-ttu-id="3f511-117">방법: MDI 상위 폼 만들기</span><span class="sxs-lookup"><span data-stu-id="3f511-117">How to: Create MDI Parent Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-mdi-parent-forms.md)  
 [<span data-ttu-id="3f511-118">방법: MDI 자식 폼 만들기</span><span class="sxs-lookup"><span data-stu-id="3f511-118">How to: Create MDI Child Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-mdi-child-forms.md)  
 [<span data-ttu-id="3f511-119">방법: 활성 MDI 자식 확인</span><span class="sxs-lookup"><span data-stu-id="3f511-119">How to: Determine the Active MDI Child</span></span>](../../../../docs/framework/winforms/advanced/how-to-determine-the-active-mdi-child.md)  
 [<span data-ttu-id="3f511-120">방법: 활성 MDI 자식으로 데이터 전송</span><span class="sxs-lookup"><span data-stu-id="3f511-120">How to: Send Data to the Active MDI Child</span></span>](../../../../docs/framework/winforms/advanced/how-to-send-data-to-the-active-mdi-child.md)
