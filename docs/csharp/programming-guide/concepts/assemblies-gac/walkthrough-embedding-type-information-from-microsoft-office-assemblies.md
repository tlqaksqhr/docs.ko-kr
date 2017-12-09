---
title: "연습: Visual Studio에서 Microsoft Office 어셈블리의 형식 정보 포함(C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 3320e866-01f1-4b7f-8932-049a7b2d2a9b
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 45ec4521da08a9a1f4bdc3b433d3f8d765960526
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-embedding-type-information-from-microsoft-office-assemblies-in-visual-studio-c"></a><span data-ttu-id="d0875-102">연습: Visual Studio에서 Microsoft Office 어셈블리의 형식 정보 포함(C#)</span><span class="sxs-lookup"><span data-stu-id="d0875-102">Walkthrough: Embedding Type Information from Microsoft Office Assemblies in Visual Studio (C#)</span></span>
<span data-ttu-id="d0875-103">COM 개체를 참조하는 응용 프로그램에 형식 정보를 포함하면 PIA(Primary Interop Assembly)가 필요하지 않게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0875-103">If you embed type information in an application that references COM objects, you can eliminate the need for a primary interop assembly (PIA).</span></span> <span data-ttu-id="d0875-104">또한 포함된 형식 정보를 사용하면 응용 프로그램의 버전 독립성을 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0875-104">Additionally, the embedded type information enables you to achieve version independence for your application.</span></span> <span data-ttu-id="d0875-105">즉, 각 버전에 대해 특정 PIA를 요구하지 않고 COM 라이브러리의 여러 버전에서 형식을 사용하도록 프로그램을 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0875-105">That is, your program can be written to use types from multiple versions of a COM library without requiring a specific PIA for each version.</span></span> <span data-ttu-id="d0875-106">이는 Microsoft Office 라이브러리의 개체를 사용하는 응용 프로그램의 일반적인 시나리오입니다.</span><span class="sxs-lookup"><span data-stu-id="d0875-106">This is a common scenario for applications that use objects from Microsoft Office libraries.</span></span> <span data-ttu-id="d0875-107">형식 정보를 포함하면 각 Microsoft Office 버전용 프로그램 또는 PIA를 다시 배포하지 않고도 동일한 프로그램 빌드를 서로 다른 컴퓨터에 있는 다른 버전의 Microsoft Office에서 작동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0875-107">Embedding type information enables the same build of a program to work with different versions of Microsoft Office on different computers without the need to redeploy either the program or the PIA for each version of Microsoft Office.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="prerequisites"></a><span data-ttu-id="d0875-108">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="d0875-108">Prerequisites</span></span>  
 <span data-ttu-id="d0875-109">이 연습에서는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d0875-109">This walkthrough requires the following:</span></span>  
  
-   <span data-ttu-id="d0875-110">Visual Studio 및 Microsoft Excel이 설치된 컴퓨터</span><span class="sxs-lookup"><span data-stu-id="d0875-110">A computer on which Visual Studio and Microsoft Excel are installed.</span></span>  
  
-   <span data-ttu-id="d0875-111">.NET Framework 4 이상 및 Excel의 다른 버전이 설치된 두 번째 컴퓨터</span><span class="sxs-lookup"><span data-stu-id="d0875-111">A second computer on which the .NET Framework 4 or higher and a different version of Excel are installed.</span></span>  
  
##  <a name="BKMK_createapp"></a> <span data-ttu-id="d0875-112">여러 버전의 Microsoft Office와 함께 작동 하는 응용 프로그램을 만들려면</span><span class="sxs-lookup"><span data-stu-id="d0875-112">To create an application that works with multiple versions of Microsoft Office</span></span>  
  
1.  <span data-ttu-id="d0875-113">Excel이 설치되어 있는 컴퓨터에서 Visual Studio를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="d0875-113">Start Visual Studio on a computer on which Excel is installed.</span></span>  
  
2.  <span data-ttu-id="d0875-114">**파일** 메뉴에서 **새로 만들기**, **프로젝트**를 차례로 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d0875-114">On the **File** menu, choose **New**, **Project**.</span></span>  
  
3.  <span data-ttu-id="d0875-115">**새 프로젝트** 대화 상자의 **프로젝트 형식** 창에서 **Windows**가 선택되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="d0875-115">In the **New Project** dialog box, in the **Project Types** pane, make sure that **Windows** is selected.</span></span> <span data-ttu-id="d0875-116">**템플릿** 창에서 **콘솔 응용 프로그램**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d0875-116">Select **Console Application** in the **Templates** pane.</span></span> <span data-ttu-id="d0875-117">**이름** 상자에 `CreateExcelWorkbook`을 입력하고 **확인** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d0875-117">In the **Name** box, enter `CreateExcelWorkbook`, and then choose the **OK** button.</span></span> <span data-ttu-id="d0875-118">새 프로젝트가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="d0875-118">The new project is created.</span></span>  
  
4.  <span data-ttu-id="d0875-119">**솔루션 탐색기**에서 **References** 폴더의 바로 가기 메뉴를 열고 **참조 추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d0875-119">In **Solution Explorer**, open the shortcut menu for the **References** folder and then choose **Add Reference**.</span></span>  
  
5.  <span data-ttu-id="d0875-120">**.NET** 탭에서 `Microsoft.Office.Interop.Excel`의 최신 버전을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d0875-120">On the **.NET** tab, choose the most recent version of `Microsoft.Office.Interop.Excel`.</span></span> <span data-ttu-id="d0875-121">예를 들어 **Microsoft.Office.Interop.Excel 14.0.0.0**입니다.</span><span class="sxs-lookup"><span data-stu-id="d0875-121">For example, **Microsoft.Office.Interop.Excel 14.0.0.0**.</span></span> <span data-ttu-id="d0875-122">**확인** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d0875-122">Choose the **OK** button.</span></span>  
  
6.  <span data-ttu-id="d0875-123">**CreateExcelWorkbook** 프로젝트에 대한 참조 목록에서, 이전 단계에서 추가한 `Microsoft.Office.Interop.Excel`에 대한 참조를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d0875-123">In the list of references for the **CreateExcelWorkbook** project, select the reference for `Microsoft.Office.Interop.Excel` that you added in the previous step.</span></span> <span data-ttu-id="d0875-124">**속성** 창에서 `Embed Interop Types` 속성이 `True`로 설정되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="d0875-124">In the **Properties** window, make sure that the `Embed Interop Types` property is set to `True`.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d0875-125">이 연습에서 만든 응용 프로그램은 포함된 interop 형식 정보 때문에 서로 다른 버전의 Microsoft Office에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0875-125">The application created in this walkthrough runs with different versions of Microsoft Office because of the embedded interop type information.</span></span> <span data-ttu-id="d0875-126">`Embed Interop Types` 속성을 `False`로 설정한 경우 응용 프로그램을 실행할 각 Microsoft Office 버전용 PIA를 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0875-126">If the `Embed Interop Types` property is set to `False`, you must include a PIA for each version of Microsoft Office that the application will run with.</span></span>  
  
7.  <span data-ttu-id="d0875-127">**Program.cs** 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="d0875-127">Open the **Program.cs** file.</span></span> <span data-ttu-id="d0875-128">파일의 코드를 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="d0875-128">Replace the code in the file with the following code:</span></span>  
  
    ```csharp  
    using System;  
    using System.Collections.Generic;  
    using System.Linq;  
    using System.Text;  
    using System.IO;  
    using Excel = Microsoft.Office.Interop.Excel;  
  
    namespace CreateExcelWorkbook  
    {  
        class Program  
        {  
            static void Main(string[] args)  
            {  
                int[] values = {4, 6, 18, 2, 1, 76, 0, 3, 11};  
  
                CreateWorkbook(values, @"C:\SampleFolder\SampleWorkbook.xls");  
            }  
  
            static void CreateWorkbook(int[] values, string filePath)  
            {  
                Excel.Application excelApp = null;  
                Excel.Workbook wkbk;  
                Excel.Worksheet sheet;  
  
                try  
                {  
                        // Start Excel and create a workbook and worksheet.  
                        excelApp = new Excel.Application();  
                        wkbk = excelApp.Workbooks.Add();  
                        sheet = wkbk.Sheets.Add() as Excel.Worksheet;  
                        sheet.Name = "Sample Worksheet";  
  
                        // Write a column of values.  
                        // In the For loop, both the row index and array index start at 1.  
                        // Therefore the value of 4 at array index 0 is not included.  
                        for (int i = 1; i < values.Length; i++)  
                        {  
                            sheet.Cells[i, 1] = values[i];  
                        }  
  
                        // Suppress any alerts and save the file. Create the directory   
                        // if it does not exist. Overwrite the file if it exists.  
                        excelApp.DisplayAlerts = false;  
                        string folderPath = Path.GetDirectoryName(filePath);  
                        if (!Directory.Exists(folderPath))  
                        {  
                            Directory.CreateDirectory(folderPath);  
                        }  
                        wkbk.SaveAs(filePath);  
                }  
                catch  
                {  
                }  
                finally  
                {  
                    sheet = null;  
                    wkbk = null;  
  
                    // Close Excel.  
                    excelApp.Quit();  
                    excelApp = null;  
                }  
            }  
        }  
    }  
    ```  
  
8.  <span data-ttu-id="d0875-129">프로젝트를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="d0875-129">Save the project.</span></span>  
  
9. <span data-ttu-id="d0875-130">Ctrl+F5를 눌러 프로젝트를 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d0875-130">Press CTRL+F5 to build and run the project.</span></span> <span data-ttu-id="d0875-131">예제 코드에서 지정한 위치에 Excel 통합 문서가 만들어졌는지 확인합니다(C:\SampleFolder\SampleWorkbook.xls).</span><span class="sxs-lookup"><span data-stu-id="d0875-131">Verify that an Excel workbook has been created at the location specified in the example code: C:\SampleFolder\SampleWorkbook.xls.</span></span>  
  
##  <a name="BKMK_publishapp"></a> <span data-ttu-id="d0875-132">다른 버전의 Microsoft Office가 설치된 컴퓨터에 응용 프로그램을 게시하려면</span><span class="sxs-lookup"><span data-stu-id="d0875-132">To publish the application to a computer on which a different version of Microsoft Office is installed</span></span>  
  
1.  <span data-ttu-id="d0875-133">이 연습에서 만든 프로젝트를 Visual Studio에서 엽니다.</span><span class="sxs-lookup"><span data-stu-id="d0875-133">Open the project created by this walkthrough in Visual Studio.</span></span>  
  
2.  <span data-ttu-id="d0875-134">**빌드** 메뉴에서 **CreateExcelWorkbook 게시**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d0875-134">On the **Build** menu, choose **Publish CreateExcelWorkbook**.</span></span> <span data-ttu-id="d0875-135">게시 마법사의 단계에 따라 응용 프로그램의 설치 가능한 버전을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d0875-135">Follow the steps of the Publish Wizard to create an installable version of the application.</span></span> <span data-ttu-id="d0875-136">자세한 내용은 [게시 마법사(Visual Studio에서 Office 개발)](https://msdn.microsoft.com/library/bb625071)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d0875-136">For more information, see [Publish Wizard (Office Development in Visual Studio)](https://msdn.microsoft.com/library/bb625071).</span></span>  
  
3.  <span data-ttu-id="d0875-137">.NET Framework 4 이상 및 Excel의 다른 버전이 설치된 두 번째 컴퓨터에 응용 프로그램을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="d0875-137">Install the application on a computer on which the .NET Framework 4 or higher and a different version of Excel are installed.</span></span>  
  
4.  <span data-ttu-id="d0875-138">설치가 완료되면 설치된 프로그램을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d0875-138">When the installation is finished, run the installed program.</span></span>  
  
5.  <span data-ttu-id="d0875-139">Excel 통합 문서가 샘플 코드에서 지정한 위치에 만들어졌는지 확인합니다(C:\SampleFolder\SampleWorkbook.xls).</span><span class="sxs-lookup"><span data-stu-id="d0875-139">Verify that an Excel workbook has been created at the location specified in the sample code: C:\SampleFolder\SampleWorkbook.xls.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0875-140">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d0875-140">See Also</span></span>  
 [<span data-ttu-id="d0875-141">연습: Visual Studio (C#)에서 관리 되는 어셈블리의 형식 포함</span><span class="sxs-lookup"><span data-stu-id="d0875-141">Walkthrough: Embedding Types from Managed Assemblies in Visual Studio (C#)</span></span>](../../../../csharp/programming-guide/concepts/assemblies-gac/walkthrough-embedding-types-from-managed-assemblies-in-visual-studio.md)  
 [<span data-ttu-id="d0875-142">/link(C# 컴파일러 옵션)</span><span class="sxs-lookup"><span data-stu-id="d0875-142">/link (C# Compiler Options)</span></span>](../../../../csharp/language-reference/compiler-options/link-compiler-option.md)
