---
title: "연습: Visual Studio (Visual Basic)에서 Microsoft Office 어셈블리의 형식 정보를 포함 | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 26b44286-5066-4ad4-8e6a-c24902be347c
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 31905a37f09db5f5192123f0118252fbe8b02eff
ms.openlocfilehash: c527941d6eae56d66cbede92ced3f66d24937354
ms.contentlocale: ko-kr
ms.lasthandoff: 05/26/2017

---
# <a name="walkthrough-embedding-type-information-from-microsoft-office-assemblies-in-visual-studio-visual-basic"></a><span data-ttu-id="38171-102">연습: Visual Studio (Visual Basic)에서 Microsoft Office 어셈블리의 형식 정보 포함</span><span class="sxs-lookup"><span data-stu-id="38171-102">Walkthrough: Embedding Type Information from Microsoft Office Assemblies in Visual Studio (Visual Basic)</span></span>
<span data-ttu-id="38171-103">COM 개체를 참조 하는 응용 프로그램에서 형식 정보를 포함 하는 경우에 주 interop 어셈블리 (PIA)에 대 한 필요성을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38171-103">If you embed type information in an application that references COM objects, you can eliminate the need for a primary interop assembly (PIA).</span></span> <span data-ttu-id="38171-104">또한, 포함된 된 형식 정보를 사용 하면 응용 프로그램에 대 한 버전 독립성을 달성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38171-104">Additionally, the embedded type information enables you to achieve version independence for your application.</span></span> <span data-ttu-id="38171-105">즉, 각 버전에 대 한 특정 PIA를 요구 하지 않고 COM 라이브러리의 여러 버전의 형식을 사용 하 여 프로그램을 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38171-105">That is, your program can be written to use types from multiple versions of a COM library without requiring a specific PIA for each version.</span></span> <span data-ttu-id="38171-106">Microsoft Office 라이브러리에서 개체를 사용 하는 응용 프로그램에 대 한 일반적인 시나리오입니다.</span><span class="sxs-lookup"><span data-stu-id="38171-106">This is a common scenario for applications that use objects from Microsoft Office libraries.</span></span> <span data-ttu-id="38171-107">형식 정보를 포함 하는 프로그램이 나 각 버전의 Microsoft Office PIA를 다시 배포 하지 않아도 서로 다른 컴퓨터에 다른 버전의 Microsoft Office를 사용 하는 프로그램의 동일한 빌드 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38171-107">Embedding type information enables the same build of a program to work with different versions of Microsoft Office on different computers without the need to redeploy either the program or the PIA for each version of Microsoft Office.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="prerequisites"></a><span data-ttu-id="38171-108">필수 조건</span><span class="sxs-lookup"><span data-stu-id="38171-108">Prerequisites</span></span>  
 <span data-ttu-id="38171-109">이 연습에서는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="38171-109">This walkthrough requires the following:</span></span>  
  
-   <span data-ttu-id="38171-110">Visual Studio 및 Microsoft Excel의 설치 된 컴퓨터입니다.</span><span class="sxs-lookup"><span data-stu-id="38171-110">A computer on which Visual Studio and Microsoft Excel are installed.</span></span>  
  
-   <span data-ttu-id="38171-111">.NET Framework 4 이상 및 Excel의 다른 버전의 설치 된 두 번째 컴퓨터.</span><span class="sxs-lookup"><span data-stu-id="38171-111">A second computer on which the .NET Framework 4 or higher and a different version of Excel are installed.</span></span>  
  
##  <span data-ttu-id="38171-112"><a name="BKMK_createapp"></a>여러 버전의 Microsoft Office와 함께 작동 하는 응용 프로그램을 만들려면</span><span class="sxs-lookup"><span data-stu-id="38171-112"><a name="BKMK_createapp"></a> To create an application that works with multiple versions of Microsoft Office</span></span>  
  
1.  <span data-ttu-id="38171-113">Excel이 설치 되어 있는 컴퓨터에 Visual Studio를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="38171-113">Start Visual Studio on a computer on which Excel is installed.</span></span>  
  
2.  <span data-ttu-id="38171-114">**파일** 메뉴에서 **새로 만들기**, **프로젝트**를 차례로 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="38171-114">On the **File** menu, choose **New**, **Project**.</span></span>  
  
3.  <span data-ttu-id="38171-115">**새 프로젝트** 대화 상자는 **프로젝트 형식** 창에서 다음 사항을 확인 **Windows** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="38171-115">In the **New Project** dialog box, in the **Project Types** pane, make sure that **Windows** is selected.</span></span> <span data-ttu-id="38171-116">선택 **콘솔 응용 프로그램** 에 **템플릿** 창입니다.</span><span class="sxs-lookup"><span data-stu-id="38171-116">Select **Console Application** in the **Templates** pane.</span></span> <span data-ttu-id="38171-117">에 **이름** 상자에 입력 합니다 `CreateExcelWorkbook`를 선택한 다음는 **확인** 단추입니다.</span><span class="sxs-lookup"><span data-stu-id="38171-117">In the **Name** box, enter `CreateExcelWorkbook`, and then choose the **OK** button.</span></span> <span data-ttu-id="38171-118">새 프로젝트가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="38171-118">The new project is created.</span></span>  
  
4.  <span data-ttu-id="38171-119">CreateExcelWorkbook 프로젝트에 대 한 바로 가기 메뉴를 열고 **속성**합니다.</span><span class="sxs-lookup"><span data-stu-id="38171-119">Open the shortcut menu for the CreateExcelWorkbook project and then choose **Properties**.</span></span> <span data-ttu-id="38171-120">선택 된 **참조** 탭 합니다.</span><span class="sxs-lookup"><span data-stu-id="38171-120">Choose the **References** tab.</span></span> <span data-ttu-id="38171-121">**추가** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="38171-121">Choose the **Add** button.</span></span>  
  
5.  <span data-ttu-id="38171-122">에 **.NET** 탭에서 가장 최신 버전의 선택 `Microsoft.Office.Interop.Excel`합니다.</span><span class="sxs-lookup"><span data-stu-id="38171-122">On the **.NET** tab, choose the most recent version of `Microsoft.Office.Interop.Excel`.</span></span> <span data-ttu-id="38171-123">예를 들어 **Microsoft.Office.Interop.Excel 14.0.0.0**합니다.</span><span class="sxs-lookup"><span data-stu-id="38171-123">For example, **Microsoft.Office.Interop.Excel 14.0.0.0**.</span></span> <span data-ttu-id="38171-124">**확인** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="38171-124">Choose the **OK** button.</span></span>  
  
6.  <span data-ttu-id="38171-125">에 대 한 참조 목록에는 **CreateExcelWorkbook** 프로젝트에 대 한 참조를 선택 합니다 `Microsoft.Office.Interop.Excel` 이전 단계에서 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="38171-125">In the list of references for the **CreateExcelWorkbook** project, select the reference for `Microsoft.Office.Interop.Excel` that you added in the previous step.</span></span> <span data-ttu-id="38171-126">에 **속성** 창 있는지 확인는 `Embed Interop Types` 속성이 `True`합니다.</span><span class="sxs-lookup"><span data-stu-id="38171-126">In the **Properties** window, make sure that the `Embed Interop Types` property is set to `True`.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="38171-127">이 연습에서 만든 응용 프로그램이 포함 된 interop 형식 정보가 있기 때문에 Microsoft Office의 서로 다른 버전으로 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="38171-127">The application created in this walkthrough runs with different versions of Microsoft Office because of the embedded interop type information.</span></span> <span data-ttu-id="38171-128">하는 경우는 `Embed Interop Types` 속성이 `False`, 각 버전의 응용 프로그램으로 실행 되는 Microsoft Office PIA를 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38171-128">If the `Embed Interop Types` property is set to `False`, you must include a PIA for each version of Microsoft Office that the application will run with.</span></span>  
  
7.  <span data-ttu-id="38171-129">Module1.vb 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="38171-129">Open the Module1.vb file.</span></span> <span data-ttu-id="38171-130">파일의 코드를 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="38171-130">Replace the code in the file with the following code:</span></span>  
  
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
  
8.  <span data-ttu-id="38171-131">프로젝트를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="38171-131">Save the project.</span></span>  
  
9. <span data-ttu-id="38171-132">빌드하고 프로젝트를 실행 하려면 CTRL + f&5;를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="38171-132">Press CTRL+F5 to build and run the project.</span></span> <span data-ttu-id="38171-133">Excel 통합 문서 예제 코드에 지정 된 위치에 만들어졌는지 확인: C:\SampleFolder\SampleWorkbook.xls 합니다.</span><span class="sxs-lookup"><span data-stu-id="38171-133">Verify that an Excel workbook has been created at the location specified in the example code: C:\SampleFolder\SampleWorkbook.xls.</span></span>  
  
##  <span data-ttu-id="38171-134"><a name="BKMK_publishapp"></a>다른 버전의 Microsoft Office가 설치 된 컴퓨터에 응용 프로그램을 게시 하려면</span><span class="sxs-lookup"><span data-stu-id="38171-134"><a name="BKMK_publishapp"></a> To publish the application to a computer on which a different version of Microsoft Office is installed</span></span>  
  
1.  <span data-ttu-id="38171-135">Visual Studio에서이 연습에서 만든 프로젝트를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="38171-135">Open the project created by this walkthrough in Visual Studio.</span></span>  
  
2.  <span data-ttu-id="38171-136">에 **빌드** 메뉴 선택 **게시 CreateExcelWorkbook**합니다.</span><span class="sxs-lookup"><span data-stu-id="38171-136">On the **Build** menu, choose **Publish CreateExcelWorkbook**.</span></span> <span data-ttu-id="38171-137">응용 프로그램의 설치 가능한 버전을 만들어 게시 마법사의 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="38171-137">Follow the steps of the Publish Wizard to create an installable version of the application.</span></span> <span data-ttu-id="38171-138">자세한 내용은 참조 [게시 마법사 (Visual Studio에서 Office 개발)](https://msdn.microsoft.com/library/bb625071)합니다.</span><span class="sxs-lookup"><span data-stu-id="38171-138">For more information, see [Publish Wizard (Office Development in Visual Studio)](https://msdn.microsoft.com/library/bb625071).</span></span>  
  
3.  <span data-ttu-id="38171-139">.NET Framework 4 이상 및 Excel의 다른 버전의 설치 된 컴퓨터에서 응용 프로그램을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="38171-139">Install the application on a computer on which the .NET Framework 4 or higher and a different version of Excel are installed.</span></span>  
  
4.  <span data-ttu-id="38171-140">설치가 완료 되 면 설치 프로그램을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="38171-140">When the installation is finished, run the installed program.</span></span>  
  
5.  <span data-ttu-id="38171-141">Excel 통합 문서에는 샘플 코드에 지정 된 위치에 만들어졌는지 확인: C:\SampleFolder\SampleWorkbook.xls 합니다.</span><span class="sxs-lookup"><span data-stu-id="38171-141">Verify that an Excel workbook has been created at the location specified in the sample code: C:\SampleFolder\SampleWorkbook.xls.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38171-142">참고 항목</span><span class="sxs-lookup"><span data-stu-id="38171-142">See Also</span></span>  
 <span data-ttu-id="38171-143">[연습: Visual Studio (Visual Basic)에서 관리 되는 어셈블리의 형식 포함](../../../../visual-basic/programming-guide/concepts/assemblies-gac/walkthrough-embedding-types-from-managed-assemblies-in-vs.md) </span><span class="sxs-lookup"><span data-stu-id="38171-143">[Walkthrough: Embedding Types from Managed Assemblies in Visual Studio (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/walkthrough-embedding-types-from-managed-assemblies-in-vs.md) </span></span>  
<span data-ttu-id="38171-144"> [/link (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/link.md)</span><span class="sxs-lookup"><span data-stu-id="38171-144"> [/link (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/link.md)</span></span>

