---
title: "연습: Visual Studio (Visual Basic)에서 Microsoft Office 어셈블리의 형식 정보 포함"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 26b44286-5066-4ad4-8e6a-c24902be347c
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 26e6fee5147e8477c64f7eaf0dc2aeb928c13e15
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-embedding-type-information-from-microsoft-office-assemblies-in-visual-studio-visual-basic"></a>연습: Visual Studio (Visual Basic)에서 Microsoft Office 어셈블리의 형식 정보 포함
COM 개체를 참조하는 응용 프로그램에 형식 정보를 포함하면 PIA(Primary Interop Assembly)가 필요하지 않게 됩니다. 또한 포함된 형식 정보를 사용하면 응용 프로그램의 버전 독립성을 구현할 수 있습니다. 즉, 각 버전에 대해 특정 PIA를 요구하지 않고 COM 라이브러리의 여러 버전에서 형식을 사용하도록 프로그램을 작성할 수 있습니다. 이는 Microsoft Office 라이브러리의 개체를 사용하는 응용 프로그램의 일반적인 시나리오입니다. 형식 정보를 포함하면 각 Microsoft Office 버전용 프로그램 또는 PIA를 다시 배포하지 않고도 동일한 프로그램 빌드를 서로 다른 컴퓨터에 있는 다른 버전의 Microsoft Office에서 작동할 수 있습니다.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="prerequisites"></a>필수 구성 요소  
 이 연습에서는 다음 사항이 필요합니다.  
  
-   Visual Studio 및 Microsoft Excel이 설치된 컴퓨터  
  
-   .NET Framework 4 이상 및 Excel의 다른 버전이 설치된 두 번째 컴퓨터  
  
##  <a name="BKMK_createapp"></a> 여러 버전의 Microsoft Office와 함께 작동 하는 응용 프로그램을 만들려면  
  
1.  Excel이 설치되어 있는 컴퓨터에서 Visual Studio를 시작합니다.  
  
2.  **파일** 메뉴에서 **새로 만들기**, **프로젝트**를 차례로 선택합니다.  
  
3.  **새 프로젝트** 대화 상자의 **프로젝트 형식** 창에서 **Windows**가 선택되었는지 확인합니다. **템플릿** 창에서 **콘솔 응용 프로그램**을 선택합니다. **이름** 상자에 `CreateExcelWorkbook`을 입력하고 **확인** 단추를 선택합니다. 새 프로젝트가 만들어집니다.  
  
4.  CreateExcelWorkbook 프로젝트에 대 한 바로 가기 메뉴를 연 다음 선택 **속성**합니다. 선택 된 **참조** 탭 합니다. **추가** 단추를 선택합니다.  
  
5.  **.NET** 탭에서 `Microsoft.Office.Interop.Excel`의 최신 버전을 선택합니다. 예를 들어 **Microsoft.Office.Interop.Excel 14.0.0.0**입니다. **확인** 단추를 선택합니다.  
  
6.  **CreateExcelWorkbook** 프로젝트에 대한 참조 목록에서, 이전 단계에서 추가한 `Microsoft.Office.Interop.Excel`에 대한 참조를 선택합니다. **속성** 창에서 `Embed Interop Types` 속성이 `True`로 설정되어 있는지 확인합니다.  
  
    > [!NOTE]
    >  이 연습에서 만든 응용 프로그램은 포함된 interop 형식 정보 때문에 서로 다른 버전의 Microsoft Office에서 실행됩니다. `Embed Interop Types` 속성을 `False`로 설정한 경우 응용 프로그램을 실행할 각 Microsoft Office 버전용 PIA를 포함해야 합니다.  
  
7.  Module1.vb 파일을 엽니다. 파일의 코드를 다음 코드로 바꿉니다.  
  
    ```vb  
    Imports Excel = Microsoft.Office.Interop.Excel  
  
    Module Module1  
  
        Sub Main()  
            Dim values = {4, 6, 18, 2, 1, 76, 0, 3, 11}  
  
            CreateWorkbook(values, "C:\SampleFolder\SampleWorkbook.xls")  
        End Sub  
  
        Sub CreateWorkbook(ByVal values As Integer(), ByVal filePath As String)  
            Dim excelApp As Excel.Application = Nothing  
            Dim wkbk As Excel.Workbook  
            Dim sheet As Excel.Worksheet  
  
            Try  
                ' Start Excel and create a workbook and worksheet.  
                excelApp = New Excel.Application  
                wkbk = excelApp.Workbooks.Add()  
                sheet = CType(wkbk.Sheets.Add(), Excel.Worksheet)  
                sheet.Name = "Sample Worksheet"  
  
                ' Write a column of values.  
                ' In the For loop, both the row index and array index start at 1.  
                ' Therefore the value of 4 at array index 0 is not included.  
                For i = 1 To values.Length - 1  
                    sheet.Cells(i, 1) = values(i)  
                Next  
  
                ' Suppress any alerts and save the file. Create the directory   
                ' if it does not exist. Overwrite the file if it exists.  
                excelApp.DisplayAlerts = False  
                Dim folderPath = My.Computer.FileSystem.GetParentPath(filePath)  
                If Not My.Computer.FileSystem.DirectoryExists(folderPath) Then  
                    My.Computer.FileSystem.CreateDirectory(folderPath)  
                End If  
                wkbk.SaveAs(filePath)  
        Catch  
  
            Finally  
                sheet = Nothing  
                wkbk = Nothing  
  
                ' Close Excel.  
                excelApp.Quit()  
                excelApp = Nothing  
            End Try  
  
        End Sub  
    End Module  
    ```  
  
8.  프로젝트를 저장합니다.  
  
9. Ctrl+F5를 눌러 프로젝트를 빌드하고 실행합니다. 예제 코드에서 지정한 위치에 Excel 통합 문서가 만들어졌는지 확인합니다(C:\SampleFolder\SampleWorkbook.xls).  
  
##  <a name="BKMK_publishapp"></a> 다른 버전의 Microsoft Office가 설치된 컴퓨터에 응용 프로그램을 게시하려면  
  
1.  이 연습에서 만든 프로젝트를 Visual Studio에서 엽니다.  
  
2.  **빌드** 메뉴에서 **CreateExcelWorkbook 게시**를 선택합니다. 게시 마법사의 단계에 따라 응용 프로그램의 설치 가능한 버전을 만듭니다. 자세한 내용은 [게시 마법사(Visual Studio에서 Office 개발)](https://msdn.microsoft.com/library/bb625071)를 참조하세요.  
  
3.  .NET Framework 4 이상 및 Excel의 다른 버전이 설치된 두 번째 컴퓨터에 응용 프로그램을 설치합니다.  
  
4.  설치가 완료되면 설치된 프로그램을 실행합니다.  
  
5.  Excel 통합 문서가 샘플 코드에서 지정한 위치에 만들어졌는지 확인합니다(C:\SampleFolder\SampleWorkbook.xls).  
  
## <a name="see-also"></a>참고 항목  
 [연습: Visual Studio (Visual Basic)에서 관리 되는 어셈블리의 형식 포함](../../../../visual-basic/programming-guide/concepts/assemblies-gac/walkthrough-embedding-types-from-managed-assemblies-in-vs.md)  
 [/link(Visual Basic)](../../../../visual-basic/reference/command-line-compiler/link.md)
