---
title: '방법: Windows Forms 패널의 배경 설정'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- background colors [Windows Forms], Windows Forms Panel controls
- background images [Windows Forms], Windows Forms Panel controls
- Panel control [Windows Forms], background
- colors [Windows Forms], Windows Forms Panel controls
ms.assetid: 096cbd8d-45cc-47b8-b1ef-a27f60ea8be0
ms.openlocfilehash: ff0c748cfb7b38c41b2ede211aed7bf6e6f68544
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-set-the-background-of-a-windows-forms-panel"></a>방법: Windows Forms 패널의 배경 설정
Windows Forms <xref:System.Windows.Forms.Panel> 컨트롤 배경 색과 배경 이미지를 표시할 수 있습니다. <xref:System.Windows.Forms.Control.BackColor%2A> 속성 라디오 단추 레이블 등 포함된 된 컨트롤에 대 한 배경색을 설정 합니다. 경우는 <xref:System.Windows.Forms.Control.BackgroundImage%2A> 속성이 설정 되어 있지는 <xref:System.Windows.Forms.Control.BackColor%2A> 선택에서 전체 패널을 채웁니다. 경우는 <xref:System.Windows.Forms.Control.BackgroundImage%2A> 속성이 설정 되어 있으면 포함 된 컨트롤 뒤 이미지에 표시 됩니다.  
  
### <a name="to-set-the-background-programmatically"></a>배경을 프로그래밍 방식으로 설정 하려면  
  
1.  패널의 설정 <xref:System.Windows.Forms.Control.BackColor%2A> 속성 형식의 값을 <xref:System.Drawing.Color?displayProperty=nameWithType>합니다.  
  
    ```vb  
    Panel1.BackColor = Color.AliceBlue  
    ```  
  
    ```csharp  
    panel1.BackColor = Color.AliceBlue;  
    ```  
  
    ```cpp  
    panel1->BackColor = Color::AliceBlue;  
    ```  
  
2.  패널의 설정 <xref:System.Windows.Forms.Control.BackgroundImage%2A> 사용 하 여 속성의 <xref:System.Drawing.Image.FromFile%2A> 의 메서드는 <xref:System.Drawing.Image?displayProperty=nameWithType> 클래스입니다.  
  
    ```vb  
    ' You should replace the bolded image   
    ' in the sample below with an image of your own choosing.  
    Panel1.BackgroundImage = Image.FromFile _  
        (System.Environment.GetFolderPath _  
        (System.Environment.SpecialFolder.Personal) _  
        & "\Image.gif")  
    ```  
  
    ```csharp  
    // You should replace the bolded image   
    // in the sample below with an image of your own choosing.  
    // Note the escape character used (@) when specifying the path.  
    panel1.BackgroundImage = Image.FromFile  
       (System.Environment.GetFolderPath  
       (System.Environment.SpecialFolder.Personal)  
       + @"\Image.gif");  
    ```  
  
    ```cpp  
    // You should replace the bolded image   
    // in the sample below with an image of your own choosing.  
    panel1->BackgroundImage = Image::FromFile(String::Concat(  
       System::Environment::GetFolderPath  
       (System::Environment::SpecialFolder::Personal),  
       "\\Image.gif"));  
    ```  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.Control.BackColor%2A>  
 <xref:System.Windows.Forms.Control.BackgroundImage%2A>  
 [Panel 컨트롤](../../../../docs/framework/winforms/controls/panel-control-windows-forms.md)  
 [Panel 컨트롤 개요](../../../../docs/framework/winforms/controls/panel-control-overview-windows-forms.md)
