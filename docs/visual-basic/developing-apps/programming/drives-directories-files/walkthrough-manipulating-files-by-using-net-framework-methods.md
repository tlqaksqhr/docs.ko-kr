---
title: "Walkthrough: Manipulating Files by Using .NET Framework Methods (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "I/O [Visual Basic], walkthroughs"
  - "text files, writing to"
  - "reading text files"
  - "text, writing to files"
  - "files, searching"
  - "StreamReader class, walkthroughs"
  - "files, accessing"
  - "I/O [Visual Basic], writing text to files"
  - "writing to files, walkthroughs"
  - "StreamWriter class, walkthroughs"
  - "text files, reading"
  - "I/O [Visual Basic], reading text from files"
ms.assetid: 7d2109eb-f98a-4389-b43d-30f384aaa7d5
caps.latest.revision: 18
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 18
---
# Walkthrough: Manipulating Files by Using .NET Framework Methods (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

이 연습에서는 <xref:System.IO.StreamReader> 클래스를 사용하여 파일을 열어서 읽고, 파일 액세스 여부를 확인하고, <xref:System.IO.StreamReader> 클래스의 인스턴스로 파일 읽기 권한 내에서 문자열을 검색하고, <xref:System.IO.StreamWriter> 클래스를 사용하여 파일에 쓰는 방법을 보여 줍니다.  
  
 [!INCLUDE[note_settings_general](../../../../csharp/language-reference/compiler-messages/includes/note-settings-general-md.md)]  
  
## 응용 프로그램 만들기  
 [!INCLUDE[vsprvs](../../../../csharp/includes/vsprvs-md.md)]를 시작하고 사용자가 지정된 파일에 쓰는 데 사용할 수 있는 폼을 만들어 프로젝트를 시작합니다.  
  
#### 프로젝트를 만들려면  
  
1.  **파일** 메뉴에서 **새 프로젝트**를 선택합니다.  
  
2.  **새 프로젝트** 창에서 **Windows 응용 프로그램**을 클릭합니다.  
  
3.  **이름** 상자에 `MyDiary`를 입력하고 **확인**을 클릭합니다.  
  
     프로젝트가 [!INCLUDE[vsprvs](../../../../csharp/includes/vsprvs-md.md)] **솔루션 탐색기**에 추가되고 **Windows Forms 디자이너**가 열립니다.  
  
4.  다음 표에 나온 컨트롤을 폼에 추가하고 속성에 해당 값을 설정합니다.  
  
||||  
|-|-|-|  
|**개체**|**속성**|**값**|  
|<xref:System.Windows.Forms.Button>|**Name**<br /><br /> **Text**|`Submit`<br /><br /> Submit Entry|  
|<xref:System.Windows.Forms.Button>|**Name**<br /><br /> **Text**|`Clear`<br /><br /> Clear Entry|  
|<xref:System.Windows.Forms.TextBox>|**Name**<br /><br /> **Text**<br /><br /> **Multiline**|`Entry`<br /><br /> Please enter something.<br /><br /> `False`|  
  
## 파일에 쓰기  
 응용 프로그램을 통해 파일에 쓰는 기능을 추가하려면 <xref:System.IO.StreamWriter> 클래스를 사용합니다.  <xref:System.IO.StreamWriter>는 문자를 특정 인코딩으로 출력하기 위한 것이고 <xref:System.IO.Stream> 클래스는 바이트를 입력 및 출력하기 위한 것입니다.  표준 텍스트 파일에 여러 줄의 정보를 쓰려는 경우에는 <xref:System.IO.StreamWriter>를 사용합니다.  <xref:System.IO.StreamWriter> 클래스에 대한 자세한 내용은 <xref:System.IO.StreamWriter>를 참조하십시오.  
  
#### 쓰기 기능을 추가하려면  
  
1.  **보기** 메뉴에서 **코드**를 선택하여 코드 편집기를 엽니다.  
  
2.  응용 프로그램에서는 <xref:System.IO> 네임스페이스를 참조하므로 코드 맨 앞에서 `Public Class Form1`로 시작하는 폼 클래스 정의 앞에 다음 문을 추가합니다.  
  
     [!code-vb[VbVbcnMyFileSystem#35](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-by-using-net-framework-methods_1.vb)]  
  
     파일에 쓰기 전에 <xref:System.IO.StreamWriter> 클래스의 인스턴스를 만들어야 합니다.  
  
3.  **보기** 메뉴에서 **디자이너**를 선택하여 **Windows Forms 디자이너**로 돌아갑니다.  `Submit` 단추를 두 번 클릭하여 단추에 대한 <xref:System.Windows.Forms.Control.Click> 이벤트 처리기를 만든 후 다음 코드를 추가합니다.  
  
     [!code-vb[VbVbcnMyFileSystem#36](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-by-using-net-framework-methods_2.vb)]  
  
> [!NOTE]
>  Visual Studio IDE\(통합 개발 환경\)는 코드 편집기로 되돌아가고 삽입 지점은 코드를 추가할 이벤트 처리기 내에 놓이게 됩니다.  
  
1.  파일에 쓰려면 <xref:System.IO.StreamWriter> 클래스의 <xref:System.IO.StreamWriter.Write%2A> 메서드를 사용합니다.  `Dim fw As StreamWriter` 바로 뒤에 다음 코드를 추가합니다.  파일이 아직 없으면 자동으로 만들어지므로 파일이 없을 경우 예외가 throw될 것을 걱정할 필요는 없습니다.  
  
     [!code-vb[VbVbcnMyFileSystem#37](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-by-using-net-framework-methods_3.vb)]  
  
2.  사용자가 빈 항목을 전송할 수 없도록 `Dim ReadString As String` 바로 뒤에 다음 코드를 추가합니다.  
  
     [!code-vb[VbVbcnMyFileSystem#38](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-by-using-net-framework-methods_4.vb)]  
  
3.  이 파일은 일기이므로 사용자는 각 항목에 날짜를 지정하고자 할 것입니다.  `fw = New StreamWriter("C:\MyDiary.txt", True)` 뒤에 다음 코드를 삽입하여 변수 `Today`를 현재 날짜로 설정합니다.  
  
     [!code-vb[VbVbcnMyFileSystem#39](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-by-using-net-framework-methods_5.vb)]  
  
4.  마지막으로 <xref:System.Windows.Forms.TextBox>를 지우는 코드를 추가합니다.  다음 코드를 `Clear` 단추의 <xref:System.Windows.Forms.Control.Click> 이벤트에 추가합니다.  
  
     [!code-vb[VbVbcnMyFileSystem#40](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-by-using-net-framework-methods_6.vb)]  
  
## 일기에 표시 기능 추가  
 이 단원에서는 최근 항목을 `DisplayEntry` <xref:System.Windows.Forms.TextBox>에 표시하는 기능을 추가합니다.  다양한 항목을 표시하여 사용자가 `DisplayEntry` <xref:System.Windows.Forms.TextBox>에 표시할 항목을 선택할 수 있도록 하는 <xref:System.Windows.Forms.ComboBox>를 추가할 수도 있습니다.  <xref:System.IO.StreamReader> 클래스의 인스턴스는 `MyDiary.txt`를 읽습니다.  <xref:System.IO.StreamWriter> 클래스와 마찬가지로 <xref:System.IO.StreamReader>는 텍스트 파일에 사용하기 위한 것입니다.  
  
 이 연습 단원에서는 다음 표에 있는 컨트롤을 폼에 추가하고 속성에 해당 값을 설정합니다.  
  
|컨트롤|속성|값|  
|---------|--------|-------|  
|<xref:System.Windows.Forms.TextBox>|**Name**<br /><br /> **Visible**<br /><br /> **크기**<br /><br /> **Multiline**|`DisplayEntry`<br /><br /> `False`<br /><br /> `120,60`<br /><br /> `True`|  
|<xref:System.Windows.Forms.Button>|**Name**<br /><br /> **Text**|`표시`<br /><br /> 표시|  
|<xref:System.Windows.Forms.Button>|**Name**<br /><br /> **Text**|`GetEntries`<br /><br /> Get Entries|  
|<xref:System.Windows.Forms.ComboBox>|**Name**<br /><br /> **Text**<br /><br /> **Enabled**|`PickEntries`<br /><br /> Select an Entry<br /><br /> `False`|  
  
#### 콤보 상자를 채우려면  
  
1.  `PickEntries` <xref:System.Windows.Forms.ComboBox>는 사용자가 각 항목을 전송한 날자를 표시하는 데 사용되므로 사용자는 특정 날짜에서 항목을 선택할 수 있습니다.  `GetEntries` 단추에 대한 <xref:System.Windows.Forms.Control.Click> 이벤트 처리기를 만들고 다음 코드를 추가합니다.  
  
     [!code-vb[VbVbcnMyFileSystem#41](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-by-using-net-framework-methods_7.vb)]  
  
2.  코드를 테스트하려면 F5 키를 눌러 응용 프로그램을 컴파일한 다음 **Get Entries**를 클릭합니다.  <xref:System.Windows.Forms.ComboBox>의 드롭다운 화살표를 클릭하여 항목 날짜를 표시합니다.  
  
#### 개별 항목을 선택하여 표시하려면  
  
1.  `Display` 단추에 대한 <xref:System.Windows.Forms.Control.Click> 이벤트 처리기를 만들고 다음 코드를 추가합니다.  
  
     [!code-vb[VbVbcnMyFileSystem#42](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-by-using-net-framework-methods_8.vb)]  
  
2.  코드를 테스트하려면 F5 키를 눌러 응용 프로그램을 컴파일한 후 항목을 전송합니다.  **Get Entries**를 클릭하고 <xref:System.Windows.Forms.ComboBox>에서 항목을 선택한 다음 **Display**를 클릭합니다.  선택한 항목의 내용이 `DisplayEntry` <xref:System.Windows.Forms.TextBox>에 나타납니다.  
  
## 사용자가 항목을 삭제하거나 수정할 수 있도록 만들기  
 마지막으로, `DeleteEntry` 및 `EditEntry` 단추를 사용하여 사용자가 항목을 삭제하거나 수정할 수 있는 기능을 추가할 수 있습니다.  항목이 표시되어 있지 않으면 두 단추 모두 사용할 수 없습니다.  
  
 다음 표에 나온 컨트롤을 폼에 추가하고 속성에 해당 값을 설정합니다.  
  
|컨트롤|속성|값|  
|---------|--------|-------|  
|<xref:System.Windows.Forms.Button>|**Name**<br /><br /> **Text**<br /><br /> **Enabled**|`DeleteEntry`<br /><br /> Delete Entry<br /><br /> `False`|  
|<xref:System.Windows.Forms.Button>|**Name**<br /><br /> **Text**<br /><br /> **Enabled**|`EditEntry`<br /><br /> Edit Entry<br /><br /> `False`|  
|<xref:System.Windows.Forms.Button>|**Name**<br /><br /> **Text**<br /><br /> **Enabled**|`SubmitEdit`<br /><br /> Submit Edit<br /><br /> `False`|  
  
#### 항목의 삭제와 수정을 가능하게 하려면  
  
1.  다음 코드를 `Display` 단추의 <xref:System.Windows.Forms.Control.Click> 이벤트에서 `DisplayEntry.Text = ReadString` 바로 다음에 추가합니다.  
  
     [!code-vb[VbVbcnMyFileSystem#43](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-by-using-net-framework-methods_9.vb)]  
  
2.  `DeleteEntry` 단추에 대한 <xref:System.Windows.Forms.Control.Click> 이벤트 처리기를 만들고 다음 코드를 추가합니다.  
  
     [!code-vb[VbVbcnMyFileSystem#44](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-by-using-net-framework-methods_10.vb)]  
  
3.  사용자가 항목을 표시하면 `EditEntry` 단추를 사용할 수 있게 됩니다.  다음 코드를 `Display` 단추의 <xref:System.Windows.Forms.Control.Click> 이벤트에서 `DisplayEntry.Text = ReadString` 바로 다음에 추가합니다.  
  
     [!code-vb[VbVbcnMyFileSystem#45](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-by-using-net-framework-methods_11.vb)]  
  
4.  `EditEntry` 단추에 대한 <xref:System.Windows.Forms.Control.Click> 이벤트 처리기를 만들고 다음 코드를 추가합니다.  
  
     [!code-vb[VbVbcnMyFileSystem#46](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-by-using-net-framework-methods_12.vb)]  
  
5.  `SubmitEdit` 단추에 대한 <xref:System.Windows.Forms.Control.Click> 이벤트 처리기를 만들고 다음 코드를 추가합니다.  
  
     [!code-vb[VbVbcnMyFileSystem#47](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-by-using-net-framework-methods_13.vb)]  
  
 코드를 테스트하려면 F5 키를 눌러 응용 프로그램을 컴파일합니다.  **Get Entries**를 클릭하고 항목을 선택한 다음 **Display**를 클릭합니다.  `DisplayEntry` <xref:System.Windows.Forms.TextBox>에 항목이 나타납니다.  **Edit Entry**를 클릭합니다.  `Entry` <xref:System.Windows.Forms.TextBox>에 항목이 나타납니다.  `Entry` <xref:System.Windows.Forms.TextBox>의 항목을 편집하고 **Submit Edit**를 클릭합니다.  `MyDiary.txt` 파일을 열어 수정한 내용을 확인합니다.  이제 항목을 선택하고 **Delete Entry**를 클릭합니다.  <xref:System.Windows.Forms.MessageBox>에서 확인을 요청하면 **OK**를 클릭합니다.  응용 프로그램을 닫고 `MyDiary.txt`를 열어 해당 항목이 삭제되었는지 확인합니다.  
  
## 참고 항목  
 <xref:System.IO.StreamReader>   
 <xref:System.IO.StreamWriter>   
 [Walkthroughs](../../../../visual-basic/walkthroughs.md)