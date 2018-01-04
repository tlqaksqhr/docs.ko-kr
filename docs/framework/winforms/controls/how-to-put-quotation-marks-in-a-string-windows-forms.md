---
title: "방법: 문자열에 인용 부호 넣기(Windows Forms)"
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
- quotation marks
- TextBox control [Windows Forms], displaying quotation marks
- quotation marks [Windows Forms], adding to strings in text boxes
ms.assetid: 68bdc3f3-4177-4eab-99cd-cac17a82b515
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 267a69b9470040dfc60f3c0b280b71e3f52dbc88
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-put-quotation-marks-in-a-string-windows-forms"></a><span data-ttu-id="b3d55-102">방법: 문자열에 인용 부호 넣기(Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="b3d55-102">How to: Put Quotation Marks in a String (Windows Forms)</span></span>
<span data-ttu-id="b3d55-103">경우에 따라 텍스트의 문자열에 따옴표(" ")를 배치하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3d55-103">Sometimes you might want to place quotation marks (" ") in a string of text.</span></span> <span data-ttu-id="b3d55-104">예:</span><span class="sxs-lookup"><span data-stu-id="b3d55-104">For example:</span></span>  
  
 <span data-ttu-id="b3d55-105">그녀는 "당신은 그럴 자격이 있어!"라고 말했습니다.</span><span class="sxs-lookup"><span data-stu-id="b3d55-105">She said, "You deserve a treat!"</span></span>  
  
 <span data-ttu-id="b3d55-106">대신 사용할 수도 있습니다는 <xref:Microsoft.VisualBasic.ControlChars.Quote> 필드는 상수입니다.</span><span class="sxs-lookup"><span data-stu-id="b3d55-106">As an alternative, you can also use the <xref:Microsoft.VisualBasic.ControlChars.Quote> field as a constant.</span></span>  
  
### <a name="to-place-quotation-marks-in-a-string-in-your-code"></a><span data-ttu-id="b3d55-107">코드의 문자열에 따옴표를 배치하려면</span><span class="sxs-lookup"><span data-stu-id="b3d55-107">To place quotation marks in a string in your code</span></span>  
  
1.  <span data-ttu-id="b3d55-108">[!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)]에서 행에서 두 개의 따옴표를 중첩된 따옴표로 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="b3d55-108">In [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)], insert two quotation marks in a row as an embedded quotation mark.</span></span> <span data-ttu-id="b3d55-109">[!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] 및 [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]에서 이스케이프 시퀀스 \\"을 중첩된 따옴표로 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="b3d55-109">In [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] and [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)], insert the escape sequence \\" as an embedded quotation mark.</span></span> <span data-ttu-id="b3d55-110">예를 들어 위의 문자열을 만들려면 다음 코드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b3d55-110">For example, to create the preceding string, use the following code.</span></span>  
  
    ```vb  
    Private Sub InsertQuote()  
       TextBox1.Text = "She said, ""You deserve a treat!"" "  
    End Sub  
    ```  
  
    ```csharp  
    private void InsertQuote(){  
       textBox1.Text = "She said, \"You deserve a treat!\" ";  
    }  
    ```  
  
    ```cpp  
    private:  
       void InsertQuote()  
       {  
          textBox1->Text = "She said, \"You deserve a treat!\" ";  
       }  
    ```  
  
     <span data-ttu-id="b3d55-111">또는</span><span class="sxs-lookup"><span data-stu-id="b3d55-111">-or-</span></span>  
  
2.  <span data-ttu-id="b3d55-112">따옴표에 대한 ASCII 또는 유니코드 문자를 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="b3d55-112">Insert the ASCII or Unicode character for a quotation mark.</span></span> <span data-ttu-id="b3d55-113">[!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)]에서 ASCII 문자(34)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b3d55-113">In [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)], use the ASCII character (34).</span></span> <span data-ttu-id="b3d55-114">[!INCLUDE[csprcs](../../../../includes/csprcs-md.md)]에서 유니코드 문자(\u0022)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b3d55-114">In [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], use the Unicode character (\u0022).</span></span>  
  
    ```vb  
    Private Sub InsertAscii()  
       TextBox1.Text = "She said, " & Chr(34) & "You deserve a treat!" & Chr(34)  
    End Sub  
    ```  
  
    ```csharp  
    private void InsertAscii(){  
       textBox1.Text = "She said, " + '\u0022' + "You deserve a treat!" + '\u0022';  
    }  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="b3d55-115">이 예제에서는 기본 문자 집합에서 문자를 지정하는 범용 문자 이름을 사용할 수 없으므로 \u0022를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b3d55-115">In this example, you cannot use \u0022 because you cannot use a universal character name that designates a character in the basic character set.</span></span> <span data-ttu-id="b3d55-116">그렇지 않으면 C3851을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="b3d55-116">Otherwise, you produce C3851.</span></span> <span data-ttu-id="b3d55-117">자세한 내용은 [컴파일러 오류 C3851](/cpp/error-messages/compiler-errors-2/compiler-error-c3851)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b3d55-117">For more information, see [Compiler Error C3851](/cpp/error-messages/compiler-errors-2/compiler-error-c3851).</span></span>  
  
     <span data-ttu-id="b3d55-118">또는</span><span class="sxs-lookup"><span data-stu-id="b3d55-118">-or-</span></span>  
  
3.  <span data-ttu-id="b3d55-119">문자에 대한 상수를 정의하고 필요한 부분에 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3d55-119">You can also define a constant for the character, and use it where needed.</span></span>  
  
    ```vb  
    Const quote As String = """"  
    TextBox1.Text = "She said, " & quote & "You deserve a treat!" & quote  
    ```  
  
    ```csharp  
    const string quote = "\"";  
    textBox1.Text = "She said, " + quote +  "You deserve a treat!"+ quote ;  
    ```  
  
    ```cpp  
    const String^ quote = "\"";  
    textBox1->Text = String::Concat("She said, ",  
       const_cast<String^>(quote), "You deserve a treat!",  
       const_cast<String^>(quote));  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="b3d55-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b3d55-120">See Also</span></span>  
 <xref:System.Windows.Forms.TextBox>  
 <xref:Microsoft.VisualBasic.ControlChars.Quote>  
 [<span data-ttu-id="b3d55-121">TextBox 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="b3d55-121">TextBox Control Overview</span></span>](../../../../docs/framework/winforms/controls/textbox-control-overview-windows-forms.md)  
 [<span data-ttu-id="b3d55-122">방법: Windows Forms TextBox 컨트롤에서 삽입 지점 제어</span><span class="sxs-lookup"><span data-stu-id="b3d55-122">How to: Control the Insertion Point in a Windows Forms TextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)  
 [<span data-ttu-id="b3d55-123">방법: Windows Forms TextBox 컨트롤을 사용하여 암호 텍스트 상자 만들기</span><span class="sxs-lookup"><span data-stu-id="b3d55-123">How to: Create a Password Text Box with the Windows Forms TextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)  
 [<span data-ttu-id="b3d55-124">방법: 읽기 전용 텍스트 상자 만들기</span><span class="sxs-lookup"><span data-stu-id="b3d55-124">How to: Create a Read-Only Text Box</span></span>](../../../../docs/framework/winforms/controls/how-to-create-a-read-only-text-box-windows-forms.md)  
 [<span data-ttu-id="b3d55-125">방법: Windows Forms TextBox 컨트롤에서 텍스트 선택</span><span class="sxs-lookup"><span data-stu-id="b3d55-125">How to: Select Text in the Windows Forms TextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-select-text-in-the-windows-forms-textbox-control.md)  
 [<span data-ttu-id="b3d55-126">방법: Windows Forms TextBox 컨트롤에 여러 줄 표시</span><span class="sxs-lookup"><span data-stu-id="b3d55-126">How to: View Multiple Lines in the Windows Forms TextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)  
 [<span data-ttu-id="b3d55-127">TextBox 컨트롤</span><span class="sxs-lookup"><span data-stu-id="b3d55-127">TextBox Control</span></span>](../../../../docs/framework/winforms/controls/textbox-control-windows-forms.md)
