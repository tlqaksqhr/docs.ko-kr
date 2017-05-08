---
title: "방법: Windows Forms RichTextBox 컨트롤을 사용하여 파일 저장 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - ".rtf 파일, RichTextBox 컨트롤에서 저장"
  - "예제[Windows Forms], 텍스트 상자"
  - "파일, RichTextBox 컨트롤을 사용하여 저장"
  - "RichTextBox 컨트롤[Windows Forms], 파일 저장"
  - "RTF 파일, RichTextBox 컨트롤에서 저장"
  - "파일 저장"
  - "파일 저장, RichTextBox 컨트롤"
  - "텍스트 파일, RichTextBox 컨트롤에서 저장"
ms.assetid: 4a58ec19-84d1-4383-9110-298c06adcfca
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# 방법: Windows Forms RichTextBox 컨트롤을 사용하여 파일 저장
Windows Forms <xref:System.Windows.Forms.RichTextBox> 컨트롤을 사용하면 표시되는 정보를 다음과 같은 여러 가지 형식 중 하나로 쓸 수 있습니다.  
  
-   일반 텍스트  
  
-   유니코드 일반 텍스트  
  
-   RTF\(서식있는 텍스트\)  
  
-   OLE 개체를 공백으로 표시하는 RTF  
  
-   OLE 개체를 텍스트로 표시하는 일반 텍스트  
  
 파일을 저장하려면 <xref:System.Windows.Forms.RichTextBox.SaveFile%2A> 메서드를 호출합니다.  **SaveFile** 메서드를 사용하여 데이터를 스트림에 저장할 수도 있습니다.  자세한 내용은 <xref:System.Windows.Forms.RichTextBox.SaveFile%28System.IO.Stream%2CSystem.Windows.Forms.RichTextBoxStreamType%29>을 참조하십시오.  
  
### 컨트롤의 내용을 파일에 저장하려면  
  
1.  저장할 파일의 경로를 지정합니다.  
  
     일반적으로 실제 응용 프로그램에서는 <xref:System.Windows.Forms.SaveFileDialog> 구성 요소를 사용합니다.  전체적인 개요를 보려면 [SaveFileDialog 구성 요소 개요](../../../../docs/framework/winforms/controls/savefiledialog-component-overview-windows-forms.md)를 참조하십시오.  
  
2.  저장할 파일 및 선택적으로 파일 형식을 지정하여 <xref:System.Windows.Forms.RichTextBox> 컨트롤의 <xref:System.Windows.Forms.RichTextBox.SaveFile%2A> 메서드를 호출합니다.  이 메서드를 호출할 때 파일 이름만 인수로 지정하면 해당 파일이 RTF로 저장됩니다.  다른 파일 형식을 지정하려면 메서드를 호출할 때 <xref:System.Windows.Forms.RichTextBoxStreamType> 열거형의 값을 두 번째 인수로 지정합니다.  
  
     아래 예제에서는 **내 문서** 폴더가 서식있는 텍스트 파일의 위치로 설정되었습니다.  Windows 운영 체제가 실행되는 대부분의 컴퓨터에는 내 문서  폴더가 포함되어 있으므로 이 위치를 사용합니다.  또한 내 문서 폴더를 선택하면 사용자는 최소한의 시스템 액세스 수준을 갖고 응용 프로그램을 안전하게 실행할 수 있습니다.  아래 예제에서는 폼에 <xref:System.Windows.Forms.RichTextBox> 컨트롤이 이미 추가되어 있다고 가정합니다.  
  
    ```vb  
    Public Sub SaveFile()  
       ' You should replace the bold file name in the   
       ' sample below with a file name of your own choosing.  
       RichTextBox1.SaveFile(System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       & "\Testdoc.rtf", _  
          RichTextBoxStreamType.RichNoOleObjs)  
    End Sub  
  
    ```  
  
    ```csharp  
    public void SaveFile()  
    {  
       // You should replace the bold file name in the   
       // sample below with a file name of your own choosing.  
       // Note the escape character used (@) when specifying the path.  
       richTextBox1.SaveFile(System.Environment.GetFolderPath  
       (System.Environment.SpecialFolder.Personal)  
       + @"\Testdoc.rtf",  
          RichTextBoxStreamType.RichNoOleObjs);  
    }  
  
    ```  
  
    ```cpp  
    public:  
       void SaveFile()  
       {  
          // You should replace the bold file name in the   
          // sample below with a file name of your own choosing.  
          richTextBox1->SaveFile(String::Concat  
             (System::Environment::GetFolderPath  
             (System::Environment::SpecialFolder::Personal),  
             "\\Testdoc.rtf"), RichTextBoxStreamType::RichNoOleObjs);  
       }  
    ```  
  
    > [!IMPORTANT]
    >  이 예제에서는 파일이 없는 경우 새 파일을 만듭니다.  응용 프로그램에서 파일을 만들어야 하는 경우 해당 응용 프로그램에는 폴더에 대한 Create 권한이 필요합니다.  사용 권한은 액세스 제어 목록을 사용하여 설정됩니다.  해당 파일이 이미 있으면 더 낮은 수준인 Write 권한만 있으면 됩니다.  가능하면 배포하는 동안 파일을 만들고 폴더에 대한 Create 권한 대신 파일 하나에 대한 Read 권한만 부여하는 것이 안전합니다.  또한 루트 폴더나 Program Files 폴더보다 사용자 폴더에 데이터를 쓰는 것이 안전합니다.  
  
## 참고 항목  
 <xref:System.Windows.Forms.RichTextBox.SaveFile%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.RichTextBox>   
 [RichTextBox 컨트롤](../../../../docs/framework/winforms/controls/richtextbox-control-windows-forms.md)   
 [Windows Forms에 사용할 수 있는 컨트롤](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)