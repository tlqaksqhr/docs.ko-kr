---
title: "Walkthrough: Manipulating Files and Directories in Visual Basic | Microsoft Docs"
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
  - "files, reading text"
  - "reading files, text"
  - "I/O [Visual Basic], walkthroughs"
  - "text, writing to files"
  - "text, reading from files"
  - "reading text from files, walkthroughs"
  - "Visual Basic code, file access"
  - "files, writing text"
  - "I/O [Visual Basic], writing text to files"
  - "file access, walkthroughs"
  - "writing to files, walkthroughs"
  - "I/O [Visual Basic], reading text from files"
ms.assetid: cae77565-9f78-4e46-8e42-eb2f9f8e1ffd
caps.latest.revision: 49
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 49
---
# Walkthrough: Manipulating Files and Directories in Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

이 연습에서는 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]의 파일 I\/O와 관련된 기본 사항을 소개합니다.  디렉터리의 텍스트 파일을 나열하고 검사하는 작은 응용 프로그램을 만드는 방법도 설명합니다.  응용 프로그램에서는 선택한 각 텍스트 파일에 대한 파일 특성과 파일 내용의 첫 번째 줄을 제공합니다.  로그 파일에 정보를 쓰는 옵션도 있습니다.  
  
 이 연습에서는 `My.Computer.FileSystem Object`의 멤버를 사용하며, 이 멤버는 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]에서 제공됩니다.  자세한 내용은 <xref:Microsoft.VisualBasic.FileIO.FileSystem>을 참조하십시오.  연습의 마지막 부분에서는 <xref:System.IO> 네임스페이스의 클래스를 사용하는 해당 예제를 제공합니다.  
  
 [!INCLUDE[note_settings_general](../../../../csharp/language-reference/compiler-messages/includes/note-settings-general-md.md)]  
  
### 프로젝트를 만들려면  
  
1.  **파일** 메뉴에서 **새 프로젝트**를 클릭합니다.  
  
     **새 프로젝트** 대화 상자가 나타납니다.  
  
2.  **설치된 템플릿** 창에서 **Visual Basic**을 확장한 다음 **Windows**를 클릭합니다.  가운데의 **템플릿** 창에서 **Windows Forms 응용 프로그램**을 클릭합니다.  
  
3.  **이름** 상자에 `FileExplorer`를 입력하여 프로젝트 이름을 설정한 다음 **확인**을 클릭합니다.  
  
     [!INCLUDE[vsprvs](../../../../csharp/includes/vsprvs-md.md)]에서 **솔루션 탐색기**에 프로젝트가 추가되고 Windows Forms 디자이너가 열립니다.  
  
4.  다음 표에 나온 컨트롤을 폼에 추가하고 속성에 해당 값을 설정합니다.  
  
    |컨트롤|Property|값|  
    |---------|--------------|-------|  
    |**ListBox**|**Name**|`filesListBox`|  
    |**Button**|**Name**<br /><br /> **Text**|`browseButton`<br /><br /> Browse|  
    |**Button**|**Name**<br /><br /> **Text**|`examineButton`<br /><br /> Examine|  
    |**CheckBox**|**Name**<br /><br /> **Text**|`saveCheckBox`<br /><br /> Save Results|  
    |**FolderBrowserDialog**|**Name**|`FolderBrowserDialog1`|  
  
### 폴더를 선택하고 폴더의 파일을 나열하려면  
  
1.  폼에서 해당 컨트롤을 두 번 클릭하여 `browseButton`의 `Click` 이벤트 처리기를 만듭니다.  코드 편집기가 열립니다.  
  
2.  `Click` 이벤트 처리기에 다음 코드를 추가합니다.  
  
     [!code-vb[VbVbcnMyFileSystem#103](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/visualbasic/walkthrough-manipulating_0_1.vb)]  
  
     `FolderBrowserDialog1.ShowDialog` 호출을 통해 **폴더 찾아보기** 대화 상자가 열립니다.  사용자가 **확인**을 클릭하면 <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> 속성이 `ListFiles` 메서드에 인수로 보내지며, 이 속성은 다음 단계에서 추가됩니다.  
  
3.  다음 `ListFiles` 메서드를 추가합니다.  
  
     [!code-vb[VbVbcnMyFileSystem#104](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/visualbasic/walkthrough-manipulating_0_2.vb)]  
  
     이 코드는 먼저 **ListBox**를 지웁니다.  
  
     그런 다음 <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFiles%2A> 메서드가 디렉터리의 각 파일마다 하나씩 문자열 컬렉션을 검색합니다.  `GetFiles` 메서드는 검색 패턴 인수를 허용하여 특정 패턴과 일치하는 파일을 검색합니다.  이 예제에서는 확장명이 .txt인 파일만 반환됩니다.  
  
     `GetFiles` 메서드에서 반환된 문자열이 **ListBox**에 추가됩니다.  
  
4.  응용 프로그램을 실행합니다.  **찾아보기** 단추를 클릭합니다.  **폴더 찾아보기** 대화 상자에서 .txt 파일이 들어 있는 폴더를 찾은 다음 폴더를 선택하고 **확인**을 클릭합니다.  
  
     선택한 폴더에 있는 .txt 파일 목록이 `ListBox`에 포함됩니다.  
  
5.  응용 프로그램 실행을 중지합니다.  
  
### 파일의 특성과 텍스트 파일의 내용을 가져오려면  
  
1.  폼에서 해당 컨트롤을 두 번 클릭하여 `examineButton`의 `Click` 이벤트 처리기를 만듭니다.  
  
2.  `Click` 이벤트 처리기에 다음 코드를 추가합니다.  
  
     [!code-vb[VbVbcnMyFileSystem#105](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/visualbasic/walkthrough-manipulating_0_3.vb)]  
  
     이 코드는 `ListBox`에서 항목이 선택되어 있는지 확인합니다.  그런 다음 `ListBox`에서 파일 경로 항목을 가져옵니다.  <xref:Microsoft.VisualBasic.FileIO.FileSystem.FileExists%2A> 메서드를 사용하여 파일이 여전히 존재하는지 여부를 확인합니다.  
  
     파일 경로가 `GetTextForOutput` 메서드에 인수로 보내지며, 이 경로는 다음 단계에서 추가됩니다.  이 메서드에서는 파일 정보가 들어 있는 문자열을 반환합니다.  **MessageBox**에 파일 정보가 나타납니다.  
  
3.  다음 `GetTextForOutput` 메서드를 추가합니다.  
  
     [!code-vb[VbVbcnMyFileSystem#107](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/visualbasic/walkthrough-manipulating_0_4.vb)]  
  
     이 코드는 <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFileInfo%2A> 메서드를 사용하여 파일 매개 변수를 가져옵니다.  파일 매개 변수가 <xref:System.Text.StringBuilder>에 추가됩니다.  
  
     <xref:Microsoft.VisualBasic.FileIO.FileSystem.OpenTextFileReader%2A> 메서드는 파일 내용을 <xref:System.IO.StreamReader>로 읽어 들입니다.  `StreamReader`에서 파일 내용의 첫 번째 줄을 가져와 `StringBuilder`에 추가합니다.  
  
4.  응용 프로그램을 실행합니다.  **찾아보기**를 클릭하고 .txt 파일이 들어 있는 폴더를 찾습니다.  **확인**을 클릭합니다.  
  
     `ListBox`에서 파일을 선택한 다음 **검사**를 클릭합니다.  `MessageBox`에서 파일 변환을 보여 줍니다.  
  
5.  응용 프로그램 실행을 중지합니다.  
  
### 로그 엔트리를 추가하려면  
  
1.  다음 코드를 `examineButton_Click` 이벤트 처리기의 끝에 추가합니다.  
  
     [!code-vb[VbVbcnMyFileSystem#106](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/visualbasic/walkthrough-manipulating_0_5.vb)]  
  
     해당 코드는 로그 파일을 선택한 파일의 디렉터리와 동일한 디렉터리에 두도록 로그 파일 경로를 설정합니다.  로그 엔트리의 텍스트는 현재 날짜 및 시간과 함께 파일 정보로 설정됩니다.  
  
     `append` 인수가 `True`로 설정된 <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A> 메서드를 사용하여 로그 엔트리를 만듭니다.  
  
2.  응용 프로그램을 실행합니다.  텍스트 파일을 찾아 `ListBox`에서 선택하고 **결과 저장** 확인란을 선택한 다음 **검사**를 클릭합니다.  로그 엔트리가 `log.txt` 파일에 기록되어 있는지 확인합니다.  
  
3.  응용 프로그램 실행을 중지합니다.  
  
### 현재 디렉터리를 사용하려면  
  
1.  폼을 두 번 클릭하여 `Form1_Load`의 이벤트 처리기를 만듭니다.  
  
2.  이벤트 처리기에 다음 코드를 추가합니다.  
  
     [!code-vb[VbVbcnMyFileSystem#102](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/visualbasic/walkthrough-manipulating_0_6.vb)]  
  
     이 코드는 폴더 브라우저의 기본 디렉터리를 현재 디렉터리로 설정합니다.  
  
3.  응용 프로그램을 실행합니다.  **찾아보기**를 처음 클릭하면 **폴더 찾아보기** 대화 상자가 열리고 현재 디렉터리가 표시됩니다.  
  
4.  응용 프로그램 실행을 중지합니다.  
  
### 선택적으로 컨트롤을 사용하도록 설정하려면  
  
1.  다음 `SetEnabled` 메서드를 추가합니다.  
  
     [!code-vb[VbVbcnMyFileSystem#108](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/visualbasic/walkthrough-manipulating_0_7.vb)]  
  
     `SetEnabled` 메서드는 `ListBox`에서 항목이 선택되어 있는지 여부에 따라 컨트롤을 사용하거나 사용하지 않도록 설정합니다.  
  
2.  폼에서 `ListBox` 컨트롤을 두 번 클릭하여 `filesListBox`의 `SelectedIndexChanged` 이벤트 처리기를 만듭니다.  
  
3.  새 `filesListBox_SelectedIndexChanged` 이벤트 처리기에서 `SetEnabled`에 대한 호출을 추가합니다.  
  
4.  `SetEnabled`에 대한 호출을 `browseButton_Click` 이벤트 처리기의 끝에 추가합니다.  
  
5.  `SetEnabled`에 대한 호출을 `Form1_Load` 이벤트 처리기의 끝에 추가합니다.  
  
6.  응용 프로그램을 실행합니다.  `ListBox`에서 항목이 선택되어 있지 않으면 **결과 저장** 확인란과 **검사** 단추를 사용할 수 없습니다.  
  
## My.Computer.FileSystem을 사용하는 전체 예제  
 다음은 전체 예제입니다.  
  
 [!code-vb[VbVbcnMyFileSystem#101](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/visualbasic/walkthrough-manipulating_0_8.vb)]  
  
## System.IO를 사용하는 전체 예제  
 다음과 같은 예제에서는 `My.Computer.FileSystem` 개체를 사용하는 대신 <xref:System.IO> 네임스페이스의 클래스를 사용합니다.  
  
 [!code-vb[VbVbcnMyFileSystem#111](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/visualbasic/walkthrough-manipulating_0_9.vb)]  
  
## 참고 항목  
 <xref:System.IO>   
 <xref:Microsoft.VisualBasic.FileIO.FileSystem>   
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.CurrentDirectory%2A>   
 [Walkthrough: Manipulating Files by Using .NET Framework Methods](../../../../visual-basic/developing-apps/programming/drives-directories-files/walkthrough-manipulating-files-by-using-net-framework-methods.md)