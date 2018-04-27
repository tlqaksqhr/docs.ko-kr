---
title: '방법: Windows Forms RichTextBox 컨트롤에 파일 로드'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- text boxes [Windows Forms], displaying files
- examples [Windows Forms], text boxes
- .rtf files [Windows Forms], opening in RichTextBox control
- RTF files [Windows Forms], opening in RichTextBox control
- text files [Windows Forms], displaying in RichTextBox control
- .rtf files [Windows Forms], displaying in RichTextBox control
- RichTextBox control [Windows Forms], opening files
- RTF files [Windows Forms], displaying in RichTextBox control
ms.assetid: c03451be-f285-4428-a71a-c41e002cc919
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 27ddc78c16b04f067e83f799e8ccb275cebdeb14
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-load-files-into-the-windows-forms-richtextbox-control"></a><span data-ttu-id="a4f65-102">방법: Windows Forms RichTextBox 컨트롤에 파일 로드</span><span class="sxs-lookup"><span data-stu-id="a4f65-102">How to: Load Files into the Windows Forms RichTextBox Control</span></span>
<span data-ttu-id="a4f65-103">Windows Forms <xref:System.Windows.Forms.RichTextBox> 컨트롤은 일반 텍스트, 유니코드 일반 텍스트 또는 RTF(서식 있는 텍스트) 파일을 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4f65-103">The Windows Forms <xref:System.Windows.Forms.RichTextBox> control can display a plain-text, Unicode plain-text, or Rich-Text-Format (RTF) file.</span></span> <span data-ttu-id="a4f65-104">이렇게 하려면 <xref:System.Windows.Forms.RichTextBox.LoadFile%2A> 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="a4f65-104">To do so, call the <xref:System.Windows.Forms.RichTextBox.LoadFile%2A> method.</span></span> <span data-ttu-id="a4f65-105">스트림에서 데이터를 로드하려면 <xref:System.Windows.Forms.RichTextBox.LoadFile%2A> 메서드를 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4f65-105">You can also use the <xref:System.Windows.Forms.RichTextBox.LoadFile%2A> method to load data from a stream.</span></span> <span data-ttu-id="a4f65-106">자세한 내용은 <xref:System.Windows.Forms.RichTextBox.LoadFile%28System.IO.Stream%2CSystem.Windows.Forms.RichTextBoxStreamType%29>을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="a4f65-106">For more information, see <xref:System.Windows.Forms.RichTextBox.LoadFile%28System.IO.Stream%2CSystem.Windows.Forms.RichTextBoxStreamType%29>.</span></span>  
  
### <a name="to-load-a-file-into-the-richtextbox-control"></a><span data-ttu-id="a4f65-107">RichTextBox 컨트롤에 파일을 로드하려면</span><span class="sxs-lookup"><span data-stu-id="a4f65-107">To load a file into the RichTextBox control</span></span>  
  
1.  <span data-ttu-id="a4f65-108"><xref:System.Windows.Forms.OpenFileDialog> 구성 요소를 사용하여 열 파일의 경로를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a4f65-108">Determine the path of the file to be opened using the <xref:System.Windows.Forms.OpenFileDialog> component.</span></span> <span data-ttu-id="a4f65-109">에 대 한 개요 [OpenFileDialog 구성 요소 개요](../../../../docs/framework/winforms/controls/openfiledialog-component-overview-windows-forms.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a4f65-109">For an overview, see [OpenFileDialog Component Overview](../../../../docs/framework/winforms/controls/openfiledialog-component-overview-windows-forms.md).</span></span>  
  
2.  <span data-ttu-id="a4f65-110"><xref:System.Windows.Forms.RichTextBox.LoadFile%2A> 컨트롤의 <xref:System.Windows.Forms.RichTextBox> 메서드를 호출하여 로드할 파일 및 선택적으로 파일 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a4f65-110">Call the <xref:System.Windows.Forms.RichTextBox.LoadFile%2A> method of the <xref:System.Windows.Forms.RichTextBox> control, specifying the file to load and optionally a file type.</span></span> <span data-ttu-id="a4f65-111">아래 예제에서는 로드할 파일을 <xref:System.Windows.Forms.OpenFileDialog> 구성 요소의 <xref:System.Windows.Forms.FileDialog.FileName%2A> 속성에서 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a4f65-111">In the example below, the file to load is taken from the <xref:System.Windows.Forms.OpenFileDialog> component's <xref:System.Windows.Forms.FileDialog.FileName%2A> property.</span></span> <span data-ttu-id="a4f65-112">파일 이름을 유일한 인수로 사용하여 메서드를 호출하면 파일 형식은 RTF로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4f65-112">If you call the method with a file name as its only argument, the file type will be assumed to be RTF.</span></span> <span data-ttu-id="a4f65-113">다른 파일 형식을 지정하려면 <xref:System.Windows.Forms.RichTextBoxStreamType> 열거형의 값을 두 번째 인수로 사용하여 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="a4f65-113">To specify another file type, call the method with a value of the <xref:System.Windows.Forms.RichTextBoxStreamType> enumeration as its second argument.</span></span>  
  
     <span data-ttu-id="a4f65-114">다음 예제에서는 단추를 클릭할 때 <xref:System.Windows.Forms.OpenFileDialog> 구성 요소가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4f65-114">In the example below, the <xref:System.Windows.Forms.OpenFileDialog> component is shown when a button is clicked.</span></span> <span data-ttu-id="a4f65-115">선택한 파일은 <xref:System.Windows.Forms.RichTextBox> 컨트롤에서 열리고 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4f65-115">The file selected is then opened and displayed in the <xref:System.Windows.Forms.RichTextBox> control.</span></span> <span data-ttu-id="a4f65-116">이 예에서는 폼에 단추(`btnOpenFile`)가 있다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="a4f65-116">This example assumes a form has a button,`btnOpenFile`.</span></span>  
  
    ```vb  
    Private Sub btnOpenFile_Click(ByVal sender As System.Object, _  
       ByVal e As System.EventArgs) Handles btnOpenFile.Click  
         If OpenFileDialog1.ShowDialog() = DialogResult.OK Then  
           RichTextBox1.LoadFile(OpenFileDialog1.FileName, _  
              RichTextBoxStreamType.RichText)  
          End If  
    End Sub  
    ```  
  
    ```csharp  
    private void btnOpenFile_Click(object sender, System.EventArgs e)  
    {  
       if(openFileDialog1.ShowDialog() == DialogResult.OK)  
       {  
         richTextBox1.LoadFile(openFileDialog1.FileName, RichTextBoxStreamType.RichText);  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void btnOpenFile_Click(System::Object ^  sender,  
          System::EventArgs ^  e)  
       {  
          if(openFileDialog1->ShowDialog() == DialogResult::OK)  
          {  
             richTextBox1->LoadFile(openFileDialog1->FileName,  
                RichTextBoxStreamType::RichText);  
          }  
       }  
    ```  
  
     <span data-ttu-id="a4f65-117">(Visual C# [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) 이벤트 처리기를 등록 하려면 폼의 생성자에 다음 코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4f65-117">(Visual C#, [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.btnOpenFile.Click += new System.EventHandler(this. btnOpenFile_Click);  
    ```  
  
    ```cpp  
    this->btnOpenFile->Click += gcnew   
       System::EventHandler(this, &Form1::btnOpenFile_Click);  
    ```  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="a4f65-118">이 프로세스를 실행하려면 어셈블리에 <xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType> 클래스에서 부여한 권한 수준이 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4f65-118">To run this process, your assembly may require a privilege level granted by the <xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="a4f65-119">부분 신뢰 컨텍스트에서 실행하는 경우 프로세스가 권한 부족으로 인해 예외를 throw할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4f65-119">If you are running in a partial-trust context, the process might throw an exception because of insufficient privileges.</span></span> <span data-ttu-id="a4f65-120">자세한 내용은 [코드 액세스 보안 기본 사항](../../../../docs/framework/misc/code-access-security-basics.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a4f65-120">For more information, see [Code Access Security Basics](../../../../docs/framework/misc/code-access-security-basics.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4f65-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a4f65-121">See Also</span></span>  
 <xref:System.Windows.Forms.RichTextBox.LoadFile%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.RichTextBox>  
 [<span data-ttu-id="a4f65-122">RichTextBox 컨트롤</span><span class="sxs-lookup"><span data-stu-id="a4f65-122">RichTextBox Control</span></span>](../../../../docs/framework/winforms/controls/richtextbox-control-windows-forms.md)  
 [<span data-ttu-id="a4f65-123">Windows Forms에 사용할 수 있는 컨트롤</span><span class="sxs-lookup"><span data-stu-id="a4f65-123">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)
