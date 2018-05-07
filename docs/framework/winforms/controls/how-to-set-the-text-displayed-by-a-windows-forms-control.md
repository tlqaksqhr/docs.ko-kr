---
title: '방법: Windows Forms 컨트롤에서 표시하는 텍스트 설정'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms, captions
- Button control [Windows Forms], button text
- StdFont object and CommandButton caption
- captions [Windows Forms], Windows Forms controls
- Text property [Windows Forms], Windows Forms control
- Button control [Windows Forms], text display
- labels [Windows Forms], adding to CommandButton control
- buttons [Windows Forms], text
- captions [Windows Forms], setting
- text
- examples [Windows Forms], controls
- text [Windows Forms], Windows Forms controls
- controls [Windows Forms], captions
- forms [Windows Forms], captions
ms.assetid: 36b95bff-8780-479d-b86a-f1a0673653aa
ms.openlocfilehash: d39b0b7ccf95f0da22086a72aa2cee424d7ea8ae
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-set-the-text-displayed-by-a-windows-forms-control"></a>방법: Windows Forms 컨트롤에서 표시하는 텍스트 설정
Windows Forms 컨트롤은 일반적으로 컨트롤의 기본 기능과 관련된 일부 텍스트를 표시합니다. 예를 들어 <xref:System.Windows.Forms.Button> 컨트롤은 일반적으로 단추를 클릭할 때 수행되는 동작을 나타내는 캡션을 표시합니다. 모든 컨트롤에 대해 <xref:System.Windows.Forms.Control.Text%2A> 속성을 사용하여 텍스트를 설정하거나 반환할 수 있습니다. <xref:System.Windows.Forms.Control.Font%2A> 속성을 사용하여 글꼴을 변경할 수 있습니다. 디자이너를 사용하여 텍스트를 설정할 수도 있습니다.  참조도 [하는 방법: 액세스 키에 대 한 Windows Forms 컨트롤 사용 하 여 작성 디자이너](http://msdn.microsoft.com/library/ms233673\(v=vs.110\)), [하는 방법: 디자이너를 사용 하 여 Windows Forms 컨트롤에서 텍스트 표시 설정](http://msdn.microsoft.com/library/ms233665\(v=vs.110\)), [하는 방법: 이미지 설정 표시 하 여 Windows Forms 디자이너를 사용 하 여 컨트롤](http://msdn.microsoft.com/library/ms233656\(v=vs.110\))합니다.  
  
### <a name="to-set-the-text-displayed-by-a-control-programmatically"></a>프로그래밍 방식으로 컨트롤에 표시되는 텍스트를 설정하려면  
  
1.  <xref:System.Windows.Forms.Control.Text%2A> 속성을 문자열로 설정합니다.  
  
     밑줄이 그어진 액세스 키를 만들려면 액세스 키로 사용할 문자 앞에 앰퍼샌드(&)를 포함합니다.  
  
2.  <xref:System.Windows.Forms.Control.Font%2A> 속성을 <xref:System.Drawing.Font> 형식의 개체로 설정합니다.  
  
    ```vb  
    Button1.Text = "Click here to save changes"  
    Button1.Font = New Font("Arial", 10, FontStyle.Bold, GraphicsUnit.Point)  
    ```  
  
    ```csharp  
    button1.Text = "Click here to save changes";  
    button1.Font = new Font("Arial", 10, FontStyle.Bold,  
       GraphicsUnit.Point);  
    ```  
  
    ```cpp  
    button1->Text = "Click here to save changes";  
    button1->Font = new System::Drawing::Font("Arial",  
       10, FontStyle::Bold, GraphicsUnit::Point);  
    ```  
  
    > [!NOTE]
    >  이스케이프 문자를 사용하여 일반적으로 다르게 해석하는 메뉴 항목과 같은 사용자 인터페이스 요소에 특수 문자를 표시할 수 있습니다. 예를 들어 다음 코드 줄에서는 메뉴 항목의 텍스트를 "& Now For Something Completely Different"로 설정합니다.  
  
    ```vb  
    MPMenuItem.Text = "&& Now For Something Completely Different"  
    ```  
  
    ```csharp  
    mpMenuItem.Text = "&& Now For Something Completely Different";  
    ```  
  
    ```cpp  
    mpMenuItem->Text = "&& Now For Something Completely Different";  
    ```  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.Control.Text%2A?displayProperty=nameWithType>  
 [방법: Windows Forms 컨트롤에 대한 선택키 만들기](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md)  
 [방법: Windows Forms 단추 클릭에 응답](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)
