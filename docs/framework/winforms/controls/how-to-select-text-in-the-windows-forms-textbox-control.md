---
title: '방법: Windows Forms TextBox 컨트롤에서 텍스트 선택'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- TextBox control [Windows Forms], selecting text programmatically
- text boxes [Windows Forms], selecting text programmatically
- text [Windows Forms], selecting in text boxes programmatically
ms.assetid: 8c591546-6a01-45c7-8e03-f78431f903b1
ms.openlocfilehash: 8fd1cfb0764d16b86cd639d8266d1cceff874932
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33536696"
---
# <a name="how-to-select-text-in-the-windows-forms-textbox-control"></a><span data-ttu-id="d4735-102">방법: Windows Forms TextBox 컨트롤에서 텍스트 선택</span><span class="sxs-lookup"><span data-stu-id="d4735-102">How to: Select Text in the Windows Forms TextBox Control</span></span>
<span data-ttu-id="d4735-103">Windows Forms에서 프로그래밍 방식으로 텍스트를 선택할 수 있습니다 <xref:System.Windows.Forms.TextBox> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4735-103">You can select text programmatically in the Windows Forms <xref:System.Windows.Forms.TextBox> control.</span></span> <span data-ttu-id="d4735-104">예를 들어 특정 문자열에 대 한 텍스트를 검색 하는 함수를 만드는 경우에 텍스트를 시각적으로 알려줄 검색된 된 문자열의 위치를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4735-104">For example, if you create a function that searches text for a particular string, you can select the text to visually alert the reader of the found string's position.</span></span>  
  
### <a name="to-select-text-programmatically"></a><span data-ttu-id="d4735-105">프로그래밍 방식으로 텍스트를 선택 하려면</span><span class="sxs-lookup"><span data-stu-id="d4735-105">To select text programmatically</span></span>  
  
1.  <span data-ttu-id="d4735-106">설정의 <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> 선택 하려는 텍스트의 시작 부분에는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="d4735-106">Set the <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> property to the beginning of the text you want to select.</span></span>  
  
     <span data-ttu-id="d4735-107"><xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> 속성은 텍스트 문자열 내에서 커서를 나타내는 숫자, 0 임 맨 왼쪽 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="d4735-107">The <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> property is a number that indicates the insertion point within the string of text, with 0 being the left-most position.</span></span> <span data-ttu-id="d4735-108">경우는 <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> 속성 값을 문자 수보다 크거나 같은 텍스트 상자에, 삽입 지점을 마지막 문자 뒤에 배치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d4735-108">If the <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> property is set to a value equal to or greater than the number of characters in the text box, the insertion point is placed after the last character.</span></span>  
  
2.  <span data-ttu-id="d4735-109">설정의 <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> 속성을 선택 하려는 텍스트의 길이입니다.</span><span class="sxs-lookup"><span data-stu-id="d4735-109">Set the <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> property to the length of the text you want to select.</span></span>  
  
     <span data-ttu-id="d4735-110"><xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> 속성은 삽입 지점의 너비를 설정 하는 숫자 값입니다.</span><span class="sxs-lookup"><span data-stu-id="d4735-110">The <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> property is a numeric value that sets the width of the insertion point.</span></span> <span data-ttu-id="d4735-111">설정의 <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> 큰 숫자를 0으로 설정 하면 해당 선택할 문자 수를 보다에서 시작 현재 삽입 지점입니다.</span><span class="sxs-lookup"><span data-stu-id="d4735-111">Setting the <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> to a number greater than 0 causes that number of characters to be selected, starting from the current insertion point.</span></span>  
  
3.  <span data-ttu-id="d4735-112">(선택 사항) 선택한 텍스트를 통해 액세스는 <xref:System.Windows.Forms.TextBoxBase.SelectedText%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="d4735-112">(Optional) Access the selected text through the <xref:System.Windows.Forms.TextBoxBase.SelectedText%2A> property.</span></span>  
  
     <span data-ttu-id="d4735-113">가 선택 되어 다음 코드는 텍스트의 내용을 상자 컨트롤의 <xref:System.Windows.Forms.Control.Enter> 이벤트가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4735-113">The code below selects the contents of a text box when the control's <xref:System.Windows.Forms.Control.Enter> event occurs.</span></span> <span data-ttu-id="d4735-114">텍스트 상자에 대 한 값에 있는지 확인 하는이 예제는 <xref:System.Windows.Forms.TextBox.Text%2A> 하지 않은 속성에 `null` 또는 빈 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="d4735-114">This example checks if the text box has a value for the <xref:System.Windows.Forms.TextBox.Text%2A> property that is not `null` or an empty string.</span></span> <span data-ttu-id="d4735-115">텍스트 상자에 포커스를 받으면 텍스트 상자에 현재 텍스트 선택 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d4735-115">When the text box receives the focus, the current text in the text box is selected.</span></span> <span data-ttu-id="d4735-116">`TextBox1_Enter` 이벤트 처리기 참조 하십시오; 자세한 내용은 컨트롤에 바인딩할 수 해야 [하는 방법: Windows Forms에 대 한 시간 실행에서 이벤트 처리기 만들기](../../../../docs/framework/winforms/how-to-create-event-handlers-at-run-time-for-windows-forms.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d4735-116">The `TextBox1_Enter` event handler must be bound to the control; for more information, see [How to: Create Event Handlers at Run Time for Windows Forms](../../../../docs/framework/winforms/how-to-create-event-handlers-at-run-time-for-windows-forms.md).</span></span>  
  
     <span data-ttu-id="d4735-117">이 예제를 테스트 하려면 텍스트 상자에 포커스가 때까지 Tab 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="d4735-117">To test this example, press the Tab key until the text box has the focus.</span></span> <span data-ttu-id="d4735-118">텍스트 상자를 클릭 하는 경우 텍스트 선택이 취소 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d4735-118">If you click in the text box, the text is unselected.</span></span>  
  
    ```vb  
    Private Sub TextBox1_Enter(ByVal sender As Object, ByVal e As System.EventArgs) Handles TextBox1.Enter  
       If (Not String.IsNullOrEmpty(TextBox1.Text)) Then  
          TextBox1.SelectionStart = 0  
          TextBox1.SelectionLength = TextBox1.Text.Length  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void textBox1_Enter(object sender, System.EventArgs e){  
       if (!String.IsNullOrEmpty(textBox1.Text))  
       {  
          textBox1.SelectionStart = 0;  
          textBox1.SelectionLength = textBox1.Text.Length;  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void textBox1_Enter(System::Object ^ sender,  
          System::EventArgs ^ e) {  
       if (!System::String::IsNullOrEmpty(textBox1->Text))  
       {  
          textBox1->SelectionStart = 0;  
          textBox1->SelectionLength = textBox1->Text->Length;  
       }  
    }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="d4735-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d4735-119">See Also</span></span>  
 <xref:System.Windows.Forms.TextBox>  
 [<span data-ttu-id="d4735-120">TextBox 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="d4735-120">TextBox Control Overview</span></span>](../../../../docs/framework/winforms/controls/textbox-control-overview-windows-forms.md)  
 [<span data-ttu-id="d4735-121">방법: Windows Forms TextBox 컨트롤에서 삽입 지점 제어</span><span class="sxs-lookup"><span data-stu-id="d4735-121">How to: Control the Insertion Point in a Windows Forms TextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)  
 [<span data-ttu-id="d4735-122">방법: Windows Forms TextBox 컨트롤을 사용하여 암호 텍스트 상자 만들기</span><span class="sxs-lookup"><span data-stu-id="d4735-122">How to: Create a Password Text Box with the Windows Forms TextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)  
 [<span data-ttu-id="d4735-123">방법: 읽기 전용 텍스트 상자 만들기</span><span class="sxs-lookup"><span data-stu-id="d4735-123">How to: Create a Read-Only Text Box</span></span>](../../../../docs/framework/winforms/controls/how-to-create-a-read-only-text-box-windows-forms.md)  
 [<span data-ttu-id="d4735-124">방법: 문자열에 인용 부호 넣기</span><span class="sxs-lookup"><span data-stu-id="d4735-124">How to: Put Quotation Marks in a String</span></span>](../../../../docs/framework/winforms/controls/how-to-put-quotation-marks-in-a-string-windows-forms.md)  
 [<span data-ttu-id="d4735-125">방법: Windows Forms TextBox 컨트롤에 여러 줄 표시</span><span class="sxs-lookup"><span data-stu-id="d4735-125">How to: View Multiple Lines in the Windows Forms TextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)  
 [<span data-ttu-id="d4735-126">TextBox 컨트롤</span><span class="sxs-lookup"><span data-stu-id="d4735-126">TextBox Control</span></span>](../../../../docs/framework/winforms/controls/textbox-control-windows-forms.md)
