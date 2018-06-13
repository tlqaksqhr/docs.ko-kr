---
title: '방법: Windows Forms에 컨트롤 추가'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms controls, adding to form
- controls [Windows Forms], adding
ms.assetid: 2af86001-9d62-4154-87fb-66db2c3cd9fd
ms.openlocfilehash: 2dd048fb074d1ec5bb7bc0a67f196d5d51281545
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33528479"
---
# <a name="how-to-add-controls-to-windows-forms"></a><span data-ttu-id="f8a01-102">방법: Windows Forms에 컨트롤 추가</span><span class="sxs-lookup"><span data-stu-id="f8a01-102">How to: Add Controls to Windows Forms</span></span>
<span data-ttu-id="f8a01-103">대부분의 폼은 폼의 화면에 컨트롤을 추가 하 여 사용자 인터페이스 (UI)를 정의 하도록 설계 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f8a01-103">Most forms are designed by adding controls to the surface of the form to define a user interface (UI).</span></span> <span data-ttu-id="f8a01-104">A *제어* 폼 정보를 표시 하거나 사용자 입력을 허용 하는 데에 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="f8a01-104">A *control* is a component on a form used to display information or accept user input.</span></span> <span data-ttu-id="f8a01-105">컨트롤에 대 한 자세한 내용은 참조 [Windows Forms 컨트롤](../../../../docs/framework/winforms/controls/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f8a01-105">For more information about controls, see [Windows Forms Controls](../../../../docs/framework/winforms/controls/index.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f8a01-106">표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8a01-106">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="f8a01-107">설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f8a01-107">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="f8a01-108">자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f8a01-108">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-draw-a-control-on-a-form"></a><span data-ttu-id="f8a01-109">폼에 컨트롤을 그리려면</span><span class="sxs-lookup"><span data-stu-id="f8a01-109">To draw a control on a form</span></span>  
  
1.  <span data-ttu-id="f8a01-110">폼을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="f8a01-110">Open the form.</span></span> <span data-ttu-id="f8a01-111">자세한 내용은 참조 [하는 방법: Windows Forms 디자이너에 표시](http://msdn.microsoft.com/library/bf3f1e5b-ea07-4529-85c6-6af3ded0cec5)합니다.</span><span class="sxs-lookup"><span data-stu-id="f8a01-111">For more information, see [How to: Display Windows Forms in the Designer](http://msdn.microsoft.com/library/bf3f1e5b-ea07-4529-85c6-6af3ded0cec5).</span></span>  
  
2.  <span data-ttu-id="f8a01-112">에 **도구 상자**를 폼에 추가 하려면 컨트롤을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8a01-112">In the **Toolbox**, click the control you want to add to your form.</span></span>  
  
3.  <span data-ttu-id="f8a01-113">폼에 위치할 컨트롤의 왼쪽 위 모퉁이 위치를 클릭 하 고 찾을 컨트롤의 오른쪽 아래 모서리를 끕니다.</span><span class="sxs-lookup"><span data-stu-id="f8a01-113">On the form, click where you want the upper-left corner of the control to be located, and drag to where you want the lower-right corner of the control to be located.</span></span>  
  
     <span data-ttu-id="f8a01-114">지정 된 위치와 크기와 폼에 컨트롤 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8a01-114">The control is added to the form with the specified location and size.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f8a01-115">각 컨트롤에 정의 된 기본 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="f8a01-115">Each control has a default size defined.</span></span> <span data-ttu-id="f8a01-116">끌어서 양식에 컨트롤의 기본 크기에는 컨트롤을 추가할 수 있습니다는 **도구 상자** 양식입니다.</span><span class="sxs-lookup"><span data-stu-id="f8a01-116">You can add a control to your form in the control's default size by dragging it from the **Toolbox** to the form.</span></span>  
  
### <a name="to-drag-a-control-to-a-form"></a><span data-ttu-id="f8a01-117">폼에 컨트롤을 끌어를</span><span class="sxs-lookup"><span data-stu-id="f8a01-117">To drag a control to a form</span></span>  
  
1.  <span data-ttu-id="f8a01-118">폼을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="f8a01-118">Open the form.</span></span> <span data-ttu-id="f8a01-119">자세한 내용은 참조 [하는 방법: Windows Forms 디자이너에 표시](http://msdn.microsoft.com/library/bf3f1e5b-ea07-4529-85c6-6af3ded0cec5)합니다.</span><span class="sxs-lookup"><span data-stu-id="f8a01-119">For more information, see [How to: Display Windows Forms in the Designer](http://msdn.microsoft.com/library/bf3f1e5b-ea07-4529-85c6-6af3ded0cec5).</span></span>  
  
2.  <span data-ttu-id="f8a01-120">에 **도구 상자**를 클릭 하는 컨트롤을 폼으로 끕니다.</span><span class="sxs-lookup"><span data-stu-id="f8a01-120">In the **Toolbox**, click the control you want and drag it to your form.</span></span>  
  
     <span data-ttu-id="f8a01-121">컨트롤의 기본 크기로 지정된 된 위치에서 형식에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8a01-121">The control is added to the form at the specified location in its default size.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f8a01-122">에 컨트롤을 두 번 클릭 수는 **도구 상자** 기본 크기의 폼의 왼쪽 위 모퉁이에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8a01-122">You can double-click a control in the **Toolbox** to add it to the upper-left corner of the form in its default size.</span></span>  
  
     <span data-ttu-id="f8a01-123">또한 컨트롤 추가할 수 있습니다 동적으로 폼에 런타임 시.</span><span class="sxs-lookup"><span data-stu-id="f8a01-123">You can also add controls dynamically to a form at run time.</span></span> <span data-ttu-id="f8a01-124">다음 코드 예제에서는 <xref:System.Windows.Forms.TextBox> 컨트롤이 폼에 추가 될 때는 <xref:System.Windows.Forms.Button> 컨트롤을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8a01-124">In the following code example, a <xref:System.Windows.Forms.TextBox> control will be added to the form when a <xref:System.Windows.Forms.Button> control is clicked.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f8a01-125">다음 절차에서 사용 하 여 폼은 **단추** 컨트롤 `Button1`, 이미 배치 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8a01-125">The following procedure requires the existence of a form with a **Button** control, `Button1`, already placed on it.</span></span>  
  
### <a name="to-add-a-control-to-a-form-programmatically"></a><span data-ttu-id="f8a01-126">프로그래밍 방식으로 폼에 컨트롤을 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="f8a01-126">To add a control to a form programmatically</span></span>  
  
1.  <span data-ttu-id="f8a01-127">에 단추를 처리 하는 방법에 `Click` 이벤트 insert와 유사한 코드를 다음 제어 변수에 대 한 참조를 추가 하려면 폼의 클래스 내에서 컨트롤의 설정 `Location`, 컨트롤을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8a01-127">In the method that handles the button's `Click` event within your form's class, insert code similar to the following to add a reference to your control variable, set the control's `Location`, and add the control.</span></span>  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
       Dim MyText As New TextBox()  
       MyText.Location = New Point(25, 25)  
       Me.Controls.Add(MyText)  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)   
    {  
       TextBox myText = new TextBox();  
       myText.Location = new Point(25,25);  
       this.Controls.Add (myText);  
    }  
    ```  
  
    ```cpp  
    private:  
      System::Void button1_Click(System::Object ^  sender,  
        System::EventArgs ^  e)  
      {  
        TextBox ^ myText = gcnew TextBox();  
        myText->Location = Point(25,25);  
        this->Controls->Add(myText);  
      }  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="f8a01-128">컨트롤의 다른 속성을 초기화 하는 코드를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8a01-128">You can also add code to initialize other properties of the control.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="f8a01-129">악성 참조 하 여 로컬 컴퓨터가 네트워크를 통해 보안 위험에 노출 될 수 있습니다 `UserControl`합니다.</span><span class="sxs-lookup"><span data-stu-id="f8a01-129">You might expose your local computer to a security risk through the network by referencing a malicious `UserControl`.</span></span> <span data-ttu-id="f8a01-130">악의적인 사용자가 실수로 프로젝트에 추가 하는 손상을 일으킬 수 있는 사용자 지정 컨트롤을 만드는 경우 문제가 것만.</span><span class="sxs-lookup"><span data-stu-id="f8a01-130">This would only be a concern in the case of a malicious person creating a damaging custom control, followed by you mistakenly adding it to your project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8a01-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f8a01-131">See Also</span></span>  
 [<span data-ttu-id="f8a01-132">Windows Forms 컨트롤</span><span class="sxs-lookup"><span data-stu-id="f8a01-132">Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/index.md)  
 [<span data-ttu-id="f8a01-133">Windows Forms에서 컨트롤 정렬</span><span class="sxs-lookup"><span data-stu-id="f8a01-133">Arranging Controls on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)  
 [<span data-ttu-id="f8a01-134">방법: Windows Forms에서 컨트롤 크기 조정</span><span class="sxs-lookup"><span data-stu-id="f8a01-134">How to: Resize Controls on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-resize-controls-on-windows-forms.md)  
 [<span data-ttu-id="f8a01-135">방법: Windows Forms 컨트롤에서 표시하는 텍스트 설정</span><span class="sxs-lookup"><span data-stu-id="f8a01-135">How to: Set the Text Displayed by a Windows Forms Control</span></span>](../../../../docs/framework/winforms/controls/how-to-set-the-text-displayed-by-a-windows-forms-control.md)  
 [<span data-ttu-id="f8a01-136">Windows Forms에 사용할 수 있는 컨트롤</span><span class="sxs-lookup"><span data-stu-id="f8a01-136">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)
