---
title: "방법: Windows Forms ErrorProvider 구성 요소를 사용하여 폼 유효성에 대한 오류 아이콘 표시"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- errors [Windows Forms], displaying to users
- error icons
- ErrorProvider component [Windows Forms], displaying error icons
- error messages [Windows Forms], displaying icons
ms.assetid: 3b681a32-9db4-497b-a34b-34980eabee46
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 02638ab59c0ba1c0eb0f8090be118b3d5a9111f8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-display-error-icons-for-form-validation-with-the-windows-forms-errorprovider-component"></a><span data-ttu-id="771fa-102">방법: Windows Forms ErrorProvider 구성 요소를 사용하여 폼 유효성에 대한 오류 아이콘 표시</span><span class="sxs-lookup"><span data-stu-id="771fa-102">How to: Display Error Icons for Form Validation with the Windows Forms ErrorProvider Component</span></span>
<span data-ttu-id="771fa-103">Windows Forms를 사용 하 여 <xref:System.Windows.Forms.ErrorProvider> 구성 요소는 사용자가 잘못 된 데이터를 입력할 때 오류 아이콘을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="771fa-103">You can use a Windows Forms <xref:System.Windows.Forms.ErrorProvider> component to display an error icon when the user enters invalid data.</span></span> <span data-ttu-id="771fa-104">간에 이동 하 여 유효성 검사 코드를 호출할 폼에 두 개 이상의 컨트롤이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="771fa-104">You must have at least two controls on the form in order to tab between them and thereby invoke the validation code.</span></span>  
  
### <a name="to-display-an-error-icon-when-a-controls-value-is-invalid"></a><span data-ttu-id="771fa-105">컨트롤의 값에 유효 하지 않을 때 오류 아이콘을 표시 하려면</span><span class="sxs-lookup"><span data-stu-id="771fa-105">To display an error icon when a control's value is invalid</span></span>  
  
1.  <span data-ttu-id="771fa-106">두 개의 추가-예를 들어 텍스트 상자-Windows Form에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="771fa-106">Add two controls — for example, text boxes — to a Windows Form.</span></span>  
  
2.  <span data-ttu-id="771fa-107">추가 <xref:System.Windows.Forms.ErrorProvider> 폼에 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="771fa-107">Add an <xref:System.Windows.Forms.ErrorProvider> component to the form.</span></span>  
  
3.  <span data-ttu-id="771fa-108">첫 번째 컨트롤을 선택 하 고 코드를 추가 하는 <xref:System.Windows.Forms.Control.Validating> 이벤트 처리기입니다.</span><span class="sxs-lookup"><span data-stu-id="771fa-108">Select the first control and add code to its <xref:System.Windows.Forms.Control.Validating> event handler.</span></span> <span data-ttu-id="771fa-109">이 코드를 제대로 실행 되려면, 프로시저는 이벤트에 연결 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="771fa-109">In order for this code to run properly, the procedure must be connected to the event.</span></span> <span data-ttu-id="771fa-110">자세한 내용은 참조 [하는 방법: Windows Forms에 대 한 시간 실행에서 이벤트 처리기 만들기](../../../../docs/framework/winforms/how-to-create-event-handlers-at-run-time-for-windows-forms.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="771fa-110">For more information, see [How to: Create Event Handlers at Run Time for Windows Forms](../../../../docs/framework/winforms/how-to-create-event-handlers-at-run-time-for-windows-forms.md).</span></span>  
  
     <span data-ttu-id="771fa-111">다음 코드는 사용자가 입력 한; 데이터의 유효성 테스트 데이터가 유효 하지 않을 경우는 <xref:System.Windows.Forms.ErrorProvider.SetError%2A> 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="771fa-111">The following code tests the validity of the data the user has entered; if the data is invalid, the <xref:System.Windows.Forms.ErrorProvider.SetError%2A> method is called.</span></span> <span data-ttu-id="771fa-112">첫 번째 인수는 <xref:System.Windows.Forms.ErrorProvider.SetError%2A> 메서드 아이콘을 옆에 표시할 컨트롤을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="771fa-112">The first argument of the <xref:System.Windows.Forms.ErrorProvider.SetError%2A> method specifies which control to display the icon next to.</span></span> <span data-ttu-id="771fa-113">두 번째 인수가 오류 텍스트를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="771fa-113">The second argument is the error text to display.</span></span>  
  
    ```vb  
    Private Sub TextBox1_Validating(ByVal Sender As Object, _  
       ByVal e As System.ComponentModel.CancelEventArgs) Handles _  
       TextBox1.Validating  
          If Not IsNumeric(TextBox1.Text) Then  
             ErrorProvider1.SetError(TextBox1, "Not a numeric value.")  
          Else  
             ' Clear the error.  
             ErrorProvider1.SetError(TextBox1, "")  
          End If  
    End Sub  
    ```  
  
    ```csharp  
    protected void textBox1_Validating (object sender,  
       System.ComponentModel.CancelEventArgs e)  
    {  
       try  
       {  
          int x = Int32.Parse(textBox1.Text);  
          errorProvider1.SetError(textBox1, "");  
       }  
       catch (Exception ex)  
       {  
          errorProvider1.SetError(textBox1, "Not an integer value.");  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       System::Void textBox1_Validating(System::Object ^  sender,  
          System::ComponentModel::CancelEventArgs ^  e)  
       {  
          try  
          {  
             int x = Int32::Parse(textBox1->Text);  
             errorProvider1->SetError(textBox1, "");  
          }  
          catch (System::Exception ^ ex)  
          {  
             errorProvider1->SetError(textBox1, "Not an integer value.");  
          }  
       }  
    ```  
  
     <span data-ttu-id="771fa-114">([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) 폼 생성자에 다음 코드를 추가하여 이벤트 처리기를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="771fa-114">([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.textBox1.Validating += new  
    System.ComponentModel.CancelEventHandler(this.textBox1_Validating);  
    ```  
  
    ```cpp  
    this->textBox1->Validating += gcnew  
       System::ComponentModel::CancelEventHandler  
       (this, &Form1::textBox1_Validating);  
    ```  
  
4.  <span data-ttu-id="771fa-115">프로젝트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="771fa-115">Run the project.</span></span> <span data-ttu-id="771fa-116">첫 번째 컨트롤 변환한 다음 두 번째 컨트롤로 (이 예에서는 숫자가 아닌)에서 잘못 된 데이터를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="771fa-116">Type invalid (in this example, non-numeric) data into the first control, and then tab to the second.</span></span> <span data-ttu-id="771fa-117">오류 아이콘이 표시 되 면 가리키면 오류 텍스트를 마우스 포인터로 됩니다.</span><span class="sxs-lookup"><span data-stu-id="771fa-117">When the error icon is displayed, point at it with the mouse pointer to see the error text.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="771fa-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="771fa-118">See Also</span></span>  
 <xref:System.Windows.Forms.ErrorProvider.SetError%2A>  
 [<span data-ttu-id="771fa-119">ErrorProvider 구성 요소 개요</span><span class="sxs-lookup"><span data-stu-id="771fa-119">ErrorProvider Component Overview</span></span>](../../../../docs/framework/winforms/controls/errorprovider-component-overview-windows-forms.md)  
 [<span data-ttu-id="771fa-120">방법: Windows Forms ErrorProvider 구성 요소를 사용하여 데이터 집합에 있는 오류 보기</span><span class="sxs-lookup"><span data-stu-id="771fa-120">How to: View Errors Within a DataSet with the Windows Forms ErrorProvider Component</span></span>](../../../../docs/framework/winforms/controls/view-errors-within-a-dataset-with-wf-errorprovider-component.md)
