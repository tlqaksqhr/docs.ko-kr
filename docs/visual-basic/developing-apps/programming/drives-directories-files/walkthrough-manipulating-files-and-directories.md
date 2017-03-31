---
title: "연습: Visual Basic에서 파일과 디렉터리 조작 | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- files, reading text
- reading files, text
- I/O [Visual Basic], walkthroughs
- text, writing to files
- text, reading from files
- reading text from files, walkthroughs
- Visual Basic code, file access
- files, writing text
- I/O [Visual Basic], writing text to files
- file access, walkthroughs
- writing to files, walkthroughs
- I/O [Visual Basic], reading text from files
ms.assetid: cae77565-9f78-4e46-8e42-eb2f9f8e1ffd
caps.latest.revision: 49
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 89137b3c927a7ac8ed126f2be3695c4aa72a85fb
ms.lasthandoff: 03/13/2017

---
# <a name="walkthrough-manipulating-files-and-directories-in-visual-basic"></a>연습: Visual Basic에서 파일과 디렉터리 조작
이 연습에서는 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]에서 파일 I/O의 기본 개념을 소개합니다. 디렉터리에 텍스트 파일을 나열하고 검사하는 작은 응용 프로그램을 만드는 방법을 설명합니다. 선택한 각 텍스트 파일에 대해 응용 프로그램은 파일 특성 및 내용의 첫 줄을 제공합니다. 로그 파일에 정보를 기록하는 옵션이 있습니다.  
  
 이 연습에서는 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]에서 사용 가능한 `My.Computer.FileSystem Object`의 멤버를 사용합니다. 자세한 내용은 <xref:Microsoft.VisualBasic.FileIO.FileSystem>을 참조하세요. 연습의 끝 부분에서 <xref:System.IO> 네임스페이스의 클래스를 사용하는 동등한 예제가 제공됩니다.  
  
[!INCLUDE[note_settings_general](../../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
### <a name="to-create-the-project"></a>프로젝트를 만들려면  
  
1.  **파일** 메뉴에서 **새 프로젝트**를 클릭합니다.  
  
     **새 프로젝트** 대화 상자가 나타납니다.  
  
2.  **설치된 템플릿** 창에서 **Visual Basic**을 확장한 다음 **Windows**를 클릭합니다. **템플릿** 창 가운데에서 **Windows Forms 응용 프로그램**을 클릭합니다.  
  
3.  **이름** 상자에 `FileExplorer`를 입력하여 프로젝트 이름을 설정한 다음 **확인**을 클릭합니다.  
  
     [!INCLUDE[vsprvs](../../../../csharp/includes/vsprvs_md.md)]에서 **솔루션 탐색기**에 프로젝트를 추가하면 Windows Forms 디자이너가 열립니다.  
  
4.  다음 표의 컨트롤을 양식에 추가하고 속성의 해당 값을 설정합니다.  
  
    |컨트롤|속성|값|  
    |-------------|--------------|-----------|  
    |**ListBox**|**Name**|`filesListBox`|  
    |**Button**|**Name**<br /><br /> **Text**|`browseButton`<br /><br /> **찾아보기**|  
    |**Button**|**Name**<br /><br /> **Text**|`examineButton`<br /><br /> **검사**|  
    |**CheckBox**|**Name**<br /><br /> **Text**|`saveCheckBox`<br /><br /> **결과 저장**|  
    |**FolderBrowserDialog**|**Name**|`FolderBrowserDialog1`|  
  
### <a name="to-select-a-folder-and-list-files-in-a-folder"></a>폴더를 선택하고 폴더에 파일을 나열하려면  
  
1.  양식의 컨트롤을 두 번 클릭하여 `browseButton`에 대한 `Click` 이벤트 처리기를 만듭니다. 코드 편집기가 열립니다.  
  
2.  다음 코드를 `Click` 이벤트 처리기에 추가합니다.  
  
     [!code-vb[VbVbcnMyFileSystem#103](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-and-directories_1.vb)]  
  
     `FolderBrowserDialog1.ShowDialog` 호출은 **폴더 찾아보기** 대화 상자를 엽니다. 사용자가 **확인**을 클릭하면 <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> 속성이 인수로서 `ListFiles` 메서드로 전송됩니다. 이 메서드는 다음 단계에서 추가됩니다.  
  
3.  다음 `ListFiles` 메서드를 추가합니다.  
  
     [!code-vb[VbVbcnMyFileSystem#104](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-and-directories_2.vb)]  
  
     이 코드는 먼저 **ListBox**를 지웁니다.  
  
     그런 다음 <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFiles%2A> 메서드는 디렉터리의 각 파일에 대해 하나씩 문자열의 컬렉션을 검색합니다. `GetFiles` 메서드는 특정 패턴과 일치하는 파일을 검색하기 위해 패턴 인수를 허용합니다. 이 예제에서는 확장명이 .txt인 파일만 반환됩니다.  
  
     `GetFiles` 메서드에 의해 반환되는 문자열은 **ListBox**에 추가됩니다.  
  
4.  응용 프로그램을 실행합니다. **찾아보기** 단추를 클릭합니다. **폴더 찾아보기** 대화 상자에서 .txt 파일이 있는 폴더로 이동하여 폴더를 선택하고 **확인**을 클릭합니다.  
  
     `ListBox`에는 선택한 폴더에 있는 .txt 파일의 목록이 포함되어 있습니다.  
  
5.  응용 프로그램 실행을 중지합니다.  
  
### <a name="to-obtain-attributes-of-a-file-and-content-from-a-text-file"></a>파일의 특성을 및 텍스트 파일의 내용을 가져오려면  
  
1.  양식의 컨트롤을 두 번 클릭하여 `examineButton`에 대한 `Click` 이벤트 처리기를 만듭니다.  
  
2.  다음 코드를 `Click` 이벤트 처리기에 추가합니다.  
  
     [!code-vb[VbVbcnMyFileSystem#105](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-and-directories_3.vb)]  
  
     이 코드는 항목이 `ListBox`에서 선택되었는지 확인합니다. 그런 다음 `ListBox`에서 파일 경로 항목을 가져옵니다. 파일이 아직 있는지 확인하기 위해 <xref:Microsoft.VisualBasic.FileIO.FileSystem.FileExists%2A> 메서드가 사용됩니다.  
  
     파일 경로가 인수로서 `GetTextForOutput` 메서드로 전송됩니다. 이 메서드는 다음 단계에서 추가되어, 파일 정보를 포함하는 문자열을 반환합니다. 파일 정보는 **MessageBox**에 나타납니다.  
  
3.  다음 `GetTextForOutput` 메서드를 추가합니다.  
  
     [!code-vb[VbVbcnMyFileSystem#107](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-and-directories_4.vb)]  
  
     이 코드는 <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFileInfo%2A> 메서드를 사용하여 파일 매개 변수를 가져옵니다. 파일 매개 변수는 <xref:System.Text.StringBuilder>에 추가됩니다.  
  
     <xref:Microsoft.VisualBasic.FileIO.FileSystem.OpenTextFileReader%2A> 메서드는 <xref:System.IO.StreamReader>로 파일 내용을 읽어옵니다. 내용의 첫 번째 줄을 `StreamReader`에서 가져와 `StringBuilder`에 추가합니다.  
  
4.  응용 프로그램을 실행합니다. **찾아보기**를 클릭하고 .txt 파일이 포함된 폴더로 이동합니다. **확인**을 클릭합니다.  
  
     `ListBox`에서 파일을 선택하고 **검사**를 클릭합니다. `MessageBox`에 파일 정보가 표시됩니다.  
  
5.  응용 프로그램 실행을 중지합니다.  
  
### <a name="to-add-a-log-entry"></a>로그 항목을 추가하려면  
  
1.  다음 코드를 `examineButton_Click` 이벤트 처리기의 끝에 추가합니다.  
  
     [!code-vb[VbVbcnMyFileSystem#106](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-and-directories_5.vb)]  
  
     이 코드는 선택한 파일과 동일한 디렉터리에 로그 파일을 저장하도록 로그 파일 경로를 설정합니다. 로그 항목의 텍스트는 파일 정보 뒤에 현재 날짜 및 시간으로 설정됩니다.  
  
     `append` 인수가 `True`로 설정된 <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A> 메서드가 로그 항목을 만드는 데 사용됩니다.  
  
2.  응용 프로그램을 실행합니다. 텍스트 파일로 이동하고, `ListBox`에서 선택하고, **결과 저장** 확인란을 선택한 다음 **검사**를 클릭합니다. 로그 항목이 `log.txt` 파일에 기록되었는지 확인합니다.  
  
3.  응용 프로그램 실행을 중지합니다.  
  
### <a name="to-use-the-current-directory"></a>현재 디렉터리를 사용하려면  
  
1.  양식을 두 번 클릭하여 `Form1_Load`에 대한 이벤트 처리기를 만듭니다.  
  
2.  다음 코드를 이벤트 처리기에 추가합니다.  
  
     [!code-vb[VbVbcnMyFileSystem#102](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-and-directories_6.vb)]  
  
     이 코드는 폴더 브라우저의 기본 디렉터리를 현재 디렉터리로 설정합니다.  
  
3.  응용 프로그램을 실행합니다. **찾아보기**를 처음 클릭하면 **폴더 찾아보기** 대화 상자가 현재 디렉터리로 열립니다.  
  
4.  응용 프로그램 실행을 중지합니다.  
  
### <a name="to-selectively-enable-controls"></a>선택적으로 컨트롤을 사용하도록 설정하려면  
  
1.  다음 `SetEnabled` 메서드를 추가합니다.  
  
     [!code-vb[VbVbcnMyFileSystem#108](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-and-directories_7.vb)]  
  
     `ListBox`에서 항목이 선택되었는지에 따라 `SetEnabled` 메서드는 컨트롤의 사용 여부를 설정합니다.  
  
2.  양식의 `ListBox` 컨트롤을 두 번 클릭하여 `filesListBox`에 대한 `SelectedIndexChanged` 이벤트 처리기를 만듭니다.  
  
3.  새 `filesListBox_SelectedIndexChanged` 이벤트 처리기에서 `SetEnabled`에 호출을 추가합니다.  
  
4.  `browseButton_Click` 이벤트 처리기의 끝에서 `SetEnabled`에 호출을 추가합니다.  
  
5.  `Form1_Load` 이벤트 처리기의 끝에서 `SetEnabled`에 호출을 추가합니다.  
  
6.  응용 프로그램을 실행합니다. `ListBox`에서 항목을 선택하지 않으면 **결과 저장** 확인란 및 **검사** 단추가 활성화되지 않습니다.  
  
## <a name="full-example-using-mycomputerfilesystem"></a>My.Computer.FileSystem을 사용하는 전체 예제  
 다음은 전체 예제입니다.  
  
 [!code-vb[VbVbcnMyFileSystem#101](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-and-directories_8.vb)]  
  
## <a name="full-example-using-systemio"></a>System.IO를 사용하는 전체 예제  
 동등한 다음 예제에서는 `My.Computer.FileSystem` 개체를 사용하는 대신 <xref:System.IO> 네임스페이스의 클래스를 사용합니다.  
  
 [!code-vb[VbVbcnMyFileSystem#111](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-and-directories_9.vb)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.IO>   
 <xref:Microsoft.VisualBasic.FileIO.FileSystem>   
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.CurrentDirectory%2A>   
 [연습: .NET Framework 메서드를 사용하여 파일 조작](../../../../visual-basic/developing-apps/programming/drives-directories-files/walkthrough-manipulating-files-by-using-net-framework-methods.md)

