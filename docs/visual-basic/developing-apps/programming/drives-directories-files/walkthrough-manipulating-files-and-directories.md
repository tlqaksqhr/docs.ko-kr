---
title: "Visual Basic에서 파일과 디렉터리 조작"
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
author: dotnet-bot
ms.author: dotnetcontent
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 9e66d062df07fc23dfbd5d509e08ccd08813db15
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="walkthrough-manipulating-files-and-directories-in-visual-basic"></a><span data-ttu-id="00e7d-102">연습: Visual Basic에서 파일과 디렉터리 조작</span><span class="sxs-lookup"><span data-stu-id="00e7d-102">Walkthrough: Manipulating Files and Directories in Visual Basic</span></span>
<span data-ttu-id="00e7d-103">이 연습에서는 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]에서 파일 I/O의 기본 개념을 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="00e7d-103">This walkthrough provides an introduction to the fundamentals of file I/O in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span></span> <span data-ttu-id="00e7d-104">디렉터리에 텍스트 파일을 나열하고 검사하는 작은 응용 프로그램을 만드는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="00e7d-104">It describes how to create a small application that lists and examines text files in a directory.</span></span> <span data-ttu-id="00e7d-105">선택한 각 텍스트 파일에 대해 응용 프로그램은 파일 특성 및 내용의 첫 줄을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="00e7d-105">For each selected text file, the application provides file attributes and the first line of content.</span></span> <span data-ttu-id="00e7d-106">로그 파일에 정보를 기록하는 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00e7d-106">There is an option to write information to a log file.</span></span>  
  
 <span data-ttu-id="00e7d-107">이 연습에서는 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]에서 사용 가능한 `My.Computer.FileSystem Object`의 멤버를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="00e7d-107">This walkthrough uses members of the `My.Computer.FileSystem Object`, which are available in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span></span> <span data-ttu-id="00e7d-108">자세한 내용은 <xref:Microsoft.VisualBasic.FileIO.FileSystem>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="00e7d-108">See <xref:Microsoft.VisualBasic.FileIO.FileSystem> for more information.</span></span> <span data-ttu-id="00e7d-109">연습의 끝 부분에서 <xref:System.IO> 네임스페이스의 클래스를 사용하는 동등한 예제가 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="00e7d-109">At the end of the walkthrough, an equivalent example is provided that uses classes from the <xref:System.IO> namespace.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-the-project"></a><span data-ttu-id="00e7d-110">프로젝트를 만들려면</span><span class="sxs-lookup"><span data-stu-id="00e7d-110">To create the project</span></span>  
  
1.  <span data-ttu-id="00e7d-111">**파일** 메뉴에서 **새 프로젝트**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="00e7d-111">On the **File** menu, click **New Project**.</span></span>  
  
     <span data-ttu-id="00e7d-112">**새 프로젝트** 대화 상자가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="00e7d-112">The **New Project** dialog box appears.</span></span>  
  
2.  <span data-ttu-id="00e7d-113">**설치된 템플릿** 창에서 **Visual Basic**을 확장한 다음 **Windows**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="00e7d-113">In the **Installed Templates** pane, expand **Visual Basic**, and then click **Windows**.</span></span> <span data-ttu-id="00e7d-114">**템플릿** 창 가운데에서 **Windows Forms 응용 프로그램**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="00e7d-114">In the **Templates** pane in the middle, click **Windows Forms Application**.</span></span>  
  
3.  <span data-ttu-id="00e7d-115">**이름** 상자에 `FileExplorer`를 입력하여 프로젝트 이름을 설정한 다음 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="00e7d-115">In the **Name** box, type `FileExplorer` to set the project name, and then click **OK**.</span></span>  
  
     [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)]<span data-ttu-id="00e7d-116">에서 **솔루션 탐색기**에 프로젝트를 추가하면 Windows Forms 디자이너가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="00e7d-116"> adds the project to **Solution Explorer**, and the Windows Forms Designer opens.</span></span>  
  
4.  <span data-ttu-id="00e7d-117">다음 표의 컨트롤을 양식에 추가하고 속성의 해당 값을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="00e7d-117">Add the controls in the following table to the form, and set the corresponding values for their properties.</span></span>  
  
    |<span data-ttu-id="00e7d-118">컨트롤</span><span class="sxs-lookup"><span data-stu-id="00e7d-118">Control</span></span>|<span data-ttu-id="00e7d-119">속성</span><span class="sxs-lookup"><span data-stu-id="00e7d-119">Property</span></span>|<span data-ttu-id="00e7d-120">값</span><span class="sxs-lookup"><span data-stu-id="00e7d-120">Value</span></span>|  
    |-------------|--------------|-----------|  
    |<span data-ttu-id="00e7d-121">**ListBox**</span><span class="sxs-lookup"><span data-stu-id="00e7d-121">**ListBox**</span></span>|<span data-ttu-id="00e7d-122">**Name**</span><span class="sxs-lookup"><span data-stu-id="00e7d-122">**Name**</span></span>|`filesListBox`|  
    |<span data-ttu-id="00e7d-123">**Button**</span><span class="sxs-lookup"><span data-stu-id="00e7d-123">**Button**</span></span>|<span data-ttu-id="00e7d-124">**Name**</span><span class="sxs-lookup"><span data-stu-id="00e7d-124">**Name**</span></span><br /><br /> <span data-ttu-id="00e7d-125">**Text**</span><span class="sxs-lookup"><span data-stu-id="00e7d-125">**Text**</span></span>|`browseButton`<br /><br /> <span data-ttu-id="00e7d-126">**찾아보기**</span><span class="sxs-lookup"><span data-stu-id="00e7d-126">**Browse**</span></span>|  
    |<span data-ttu-id="00e7d-127">**Button**</span><span class="sxs-lookup"><span data-stu-id="00e7d-127">**Button**</span></span>|<span data-ttu-id="00e7d-128">**Name**</span><span class="sxs-lookup"><span data-stu-id="00e7d-128">**Name**</span></span><br /><br /> <span data-ttu-id="00e7d-129">**Text**</span><span class="sxs-lookup"><span data-stu-id="00e7d-129">**Text**</span></span>|`examineButton`<br /><br /> <span data-ttu-id="00e7d-130">**검사**</span><span class="sxs-lookup"><span data-stu-id="00e7d-130">**Examine**</span></span>|  
    |<span data-ttu-id="00e7d-131">**CheckBox**</span><span class="sxs-lookup"><span data-stu-id="00e7d-131">**CheckBox**</span></span>|<span data-ttu-id="00e7d-132">**Name**</span><span class="sxs-lookup"><span data-stu-id="00e7d-132">**Name**</span></span><br /><br /> <span data-ttu-id="00e7d-133">**Text**</span><span class="sxs-lookup"><span data-stu-id="00e7d-133">**Text**</span></span>|`saveCheckBox`<br /><br /> <span data-ttu-id="00e7d-134">**결과 저장**</span><span class="sxs-lookup"><span data-stu-id="00e7d-134">**Save Results**</span></span>|  
    |<span data-ttu-id="00e7d-135">**FolderBrowserDialog**</span><span class="sxs-lookup"><span data-stu-id="00e7d-135">**FolderBrowserDialog**</span></span>|<span data-ttu-id="00e7d-136">**Name**</span><span class="sxs-lookup"><span data-stu-id="00e7d-136">**Name**</span></span>|`FolderBrowserDialog1`|  
  
### <a name="to-select-a-folder-and-list-files-in-a-folder"></a><span data-ttu-id="00e7d-137">폴더를 선택하고 폴더에 파일을 나열하려면</span><span class="sxs-lookup"><span data-stu-id="00e7d-137">To select a folder, and list files in a folder</span></span>  
  
1.  <span data-ttu-id="00e7d-138">양식의 컨트롤을 두 번 클릭하여 `browseButton`에 대한 `Click` 이벤트 처리기를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="00e7d-138">Create a `Click` event handler for `browseButton` by double-clicking the control on the form.</span></span> <span data-ttu-id="00e7d-139">코드 편집기가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="00e7d-139">The Code Editor opens.</span></span>  
  
2.  <span data-ttu-id="00e7d-140">다음 코드를 `Click` 이벤트 처리기에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="00e7d-140">Add the following code to the `Click` event handler.</span></span>  
  
     <span data-ttu-id="00e7d-141">[!code-vb[VbVbcnMyFileSystem#103](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-and-directories_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="00e7d-141">[!code-vb[VbVbcnMyFileSystem#103](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-and-directories_1.vb)]</span></span>  
  
     <span data-ttu-id="00e7d-142">`FolderBrowserDialog1.ShowDialog` 호출은 **폴더 찾아보기** 대화 상자를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="00e7d-142">The `FolderBrowserDialog1.ShowDialog` call opens the **Browse For Folder** dialog box.</span></span> <span data-ttu-id="00e7d-143">사용자가 **확인**을 클릭하면 <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> 속성이 `ListFiles` 메서드로 인수에 전송됩니다. 다음 단계에서 이 메서드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="00e7d-143">After the user clicks **OK**, the <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> property is sent as an argument to the `ListFiles` method, which is added in the next step.</span></span>  
  
3.  <span data-ttu-id="00e7d-144">다음 `ListFiles` 메서드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="00e7d-144">Add the following `ListFiles` method.</span></span>  
  
     <span data-ttu-id="00e7d-145">[!code-vb[VbVbcnMyFileSystem#104](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-and-directories_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="00e7d-145">[!code-vb[VbVbcnMyFileSystem#104](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-and-directories_2.vb)]</span></span>  
  
     <span data-ttu-id="00e7d-146">이 코드는 먼저 **ListBox**를 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="00e7d-146">This code first clears the **ListBox**.</span></span>  
  
     <span data-ttu-id="00e7d-147"><xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFiles%2A> 메서드는 디렉터리에 있는 각 파일에 대해 나하씩 문자열 컬렉션을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="00e7d-147">The <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFiles%2A> method then retrieves a collection of strings, one for each file in the directory.</span></span> <span data-ttu-id="00e7d-148">`GetFiles` 메서드는 특정 패턴과 일치하는 파일을 검색하기 위해 패턴 인수를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="00e7d-148">The `GetFiles` method accepts a search pattern argument to retrieve files that match a particular pattern.</span></span> <span data-ttu-id="00e7d-149">이 예제에서는 확장명이 .txt인 파일만 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="00e7d-149">In this example, only files that have the extension .txt are returned.</span></span>  
  
     <span data-ttu-id="00e7d-150">`GetFiles` 메서드에 의해 반환되는 문자열은 **ListBox**에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="00e7d-150">The strings that are returned by the `GetFiles` method are then added to the **ListBox**.</span></span>  
  
4.  <span data-ttu-id="00e7d-151">응용 프로그램을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="00e7d-151">Run the application.</span></span> <span data-ttu-id="00e7d-152">**찾아보기** 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="00e7d-152">Click the **Browse** button.</span></span> <span data-ttu-id="00e7d-153">**폴더 찾아보기** 대화 상자에서 .txt 파일이 있는 폴더로 이동하여 폴더를 선택하고 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="00e7d-153">In the **Browse For Folder** dialog box, browse to a folder that contains .txt files, and then select the folder and click **OK**.</span></span>  
  
     <span data-ttu-id="00e7d-154">`ListBox`에는 선택한 폴더에 있는 .txt 파일의 목록이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00e7d-154">The `ListBox` contains a list of .txt files in the selected folder.</span></span>  
  
5.  <span data-ttu-id="00e7d-155">응용 프로그램 실행을 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="00e7d-155">Stop running the application.</span></span>  
  
### <a name="to-obtain-attributes-of-a-file-and-content-from-a-text-file"></a><span data-ttu-id="00e7d-156">파일의 특성을 및 텍스트 파일의 내용을 가져오려면</span><span class="sxs-lookup"><span data-stu-id="00e7d-156">To obtain attributes of a file, and content from a text file</span></span>  
  
1.  <span data-ttu-id="00e7d-157">양식의 컨트롤을 두 번 클릭하여 `examineButton`에 대한 `Click` 이벤트 처리기를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="00e7d-157">Create a `Click` event handler for `examineButton` by double-clicking the control on the form.</span></span>  
  
2.  <span data-ttu-id="00e7d-158">다음 코드를 `Click` 이벤트 처리기에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="00e7d-158">Add the following code to the `Click` event handler.</span></span>  
  
     <span data-ttu-id="00e7d-159">[!code-vb[VbVbcnMyFileSystem#105](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-and-directories_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="00e7d-159">[!code-vb[VbVbcnMyFileSystem#105](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-and-directories_3.vb)]</span></span>  
  
     <span data-ttu-id="00e7d-160">이 코드는 항목이 `ListBox`에서 선택되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="00e7d-160">The code verifies that an item is selected in the `ListBox`.</span></span> <span data-ttu-id="00e7d-161">그런 다음 `ListBox`에서 파일 경로 항목을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="00e7d-161">It then obtains the file path entry from the `ListBox`.</span></span> <span data-ttu-id="00e7d-162"><xref:Microsoft.VisualBasic.FileIO.FileSystem.FileExists%2A> 메서드는 파일이 아직 있는지를 확인하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="00e7d-162">The <xref:Microsoft.VisualBasic.FileIO.FileSystem.FileExists%2A> method is used to check whether the file still exists.</span></span>  
  
     <span data-ttu-id="00e7d-163">파일 경로가 인수로서 `GetTextForOutput` 메서드로 전송됩니다. 이 메서드는 다음 단계에서 추가되어,</span><span class="sxs-lookup"><span data-stu-id="00e7d-163">The file path is sent as an argument to the `GetTextForOutput` method, which is added in the next step.</span></span> <span data-ttu-id="00e7d-164">파일 정보를 포함하는 문자열을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="00e7d-164">This method returns a string that contains file information.</span></span> <span data-ttu-id="00e7d-165">파일 정보는 **MessageBox**에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="00e7d-165">The file information appears in a **MessageBox**.</span></span>  
  
3.  <span data-ttu-id="00e7d-166">다음 `GetTextForOutput` 메서드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="00e7d-166">Add the following `GetTextForOutput` method.</span></span>  
  
     <span data-ttu-id="00e7d-167">[!code-vb[VbVbcnMyFileSystem#107](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-and-directories_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="00e7d-167">[!code-vb[VbVbcnMyFileSystem#107](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-and-directories_4.vb)]</span></span>  
  
     <span data-ttu-id="00e7d-168">이 코드는 <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFileInfo%2A> 메서드를 사용하여 파일 매개 변수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="00e7d-168">The code uses the <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFileInfo%2A> method to obtain file parameters.</span></span> <span data-ttu-id="00e7d-169">파일 매개 변수는 <xref:System.Text.StringBuilder>에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="00e7d-169">The file parameters are added to a <xref:System.Text.StringBuilder>.</span></span>  
  
     <span data-ttu-id="00e7d-170"><xref:Microsoft.VisualBasic.FileIO.FileSystem.OpenTextFileReader%2A> 메서드는 파일 내용을 <xref:System.IO.StreamReader>로 읽어들입니다.</span><span class="sxs-lookup"><span data-stu-id="00e7d-170">The <xref:Microsoft.VisualBasic.FileIO.FileSystem.OpenTextFileReader%2A> method reads the file contents into a <xref:System.IO.StreamReader>.</span></span> <span data-ttu-id="00e7d-171">내용의 첫 번째 줄을 `StreamReader`에서 가져와 `StringBuilder`에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="00e7d-171">The first line of the contents is obtained from the `StreamReader` and is added to the `StringBuilder`.</span></span>  
  
4.  <span data-ttu-id="00e7d-172">응용 프로그램을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="00e7d-172">Run the application.</span></span> <span data-ttu-id="00e7d-173">**찾아보기**를 클릭하고 .txt 파일이 포함된 폴더로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="00e7d-173">Click **Browse**, and browse to a folder that contains .txt files.</span></span> <span data-ttu-id="00e7d-174">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="00e7d-174">Click **OK**.</span></span>  
  
     <span data-ttu-id="00e7d-175">`ListBox`에서 파일을 선택하고 **검사**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="00e7d-175">Select a file in the `ListBox`, and then click **Examine**.</span></span> <span data-ttu-id="00e7d-176">`MessageBox`에 파일 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="00e7d-176">A `MessageBox` shows the file information.</span></span>  
  
5.  <span data-ttu-id="00e7d-177">응용 프로그램 실행을 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="00e7d-177">Stop running the application.</span></span>  
  
### <a name="to-add-a-log-entry"></a><span data-ttu-id="00e7d-178">로그 항목을 추가하려면</span><span class="sxs-lookup"><span data-stu-id="00e7d-178">To add a log entry</span></span>  
  
1.  <span data-ttu-id="00e7d-179">다음 코드를 `examineButton_Click` 이벤트 처리기의 끝에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="00e7d-179">Add the following code to the end of the `examineButton_Click` event handler.</span></span>  
  
     <span data-ttu-id="00e7d-180">[!code-vb[VbVbcnMyFileSystem#106](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-and-directories_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="00e7d-180">[!code-vb[VbVbcnMyFileSystem#106](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-and-directories_5.vb)]</span></span>  
  
     <span data-ttu-id="00e7d-181">이 코드는 선택한 파일과 동일한 디렉터리에 로그 파일을 저장하도록 로그 파일 경로를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="00e7d-181">The code sets the log file path to put the log file in the same directory as that of the selected file.</span></span> <span data-ttu-id="00e7d-182">로그 항목의 텍스트는 파일 정보 뒤에 현재 날짜 및 시간으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="00e7d-182">The text of the log entry is set to the current date and time followed by the file information.</span></span>  
  
     <span data-ttu-id="00e7d-183">`append` 인수가 `True`로 설정된 <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A> 메서드를 사용하여 로그 항목을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="00e7d-183">The <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A> method, with the `append` argument set to `True`, is used to create the log entry.</span></span>  
  
2.  <span data-ttu-id="00e7d-184">응용 프로그램을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="00e7d-184">Run the application.</span></span> <span data-ttu-id="00e7d-185">텍스트 파일로 이동하고, `ListBox`에서 선택하고, **결과 저장** 확인란을 선택한 다음 **검사**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="00e7d-185">Browse to a text file, select it in the `ListBox`, select the **Save Results** check box, and then click **Examine**.</span></span> <span data-ttu-id="00e7d-186">로그 항목이 `log.txt` 파일에 기록되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="00e7d-186">Verify that the log entry is written to the `log.txt` file.</span></span>  
  
3.  <span data-ttu-id="00e7d-187">응용 프로그램 실행을 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="00e7d-187">Stop running the application.</span></span>  
  
### <a name="to-use-the-current-directory"></a><span data-ttu-id="00e7d-188">현재 디렉터리를 사용하려면</span><span class="sxs-lookup"><span data-stu-id="00e7d-188">To use the current directory</span></span>  
  
1.  <span data-ttu-id="00e7d-189">양식을 두 번 클릭하여 `Form1_Load`에 대한 이벤트 처리기를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="00e7d-189">Create an event handler for `Form1_Load` by double-clicking the form.</span></span>  
  
2.  <span data-ttu-id="00e7d-190">다음 코드를 이벤트 처리기에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="00e7d-190">Add the following code to the event handler.</span></span>  
  
     <span data-ttu-id="00e7d-191">[!code-vb[VbVbcnMyFileSystem#102](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-and-directories_6.vb)]</span><span class="sxs-lookup"><span data-stu-id="00e7d-191">[!code-vb[VbVbcnMyFileSystem#102](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-and-directories_6.vb)]</span></span>  
  
     <span data-ttu-id="00e7d-192">이 코드는 폴더 브라우저의 기본 디렉터리를 현재 디렉터리로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="00e7d-192">This code sets the default directory of the folder browser to the current directory.</span></span>  
  
3.  <span data-ttu-id="00e7d-193">응용 프로그램을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="00e7d-193">Run the application.</span></span> <span data-ttu-id="00e7d-194">**찾아보기**를 처음 클릭하면 **폴더 찾아보기** 대화 상자가 현재 디렉터리로 열립니다.</span><span class="sxs-lookup"><span data-stu-id="00e7d-194">When you click **Browse** the first time, the **Browse For Folder** dialog box opens to the current directory.</span></span>  
  
4.  <span data-ttu-id="00e7d-195">응용 프로그램 실행을 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="00e7d-195">Stop running the application.</span></span>  
  
### <a name="to-selectively-enable-controls"></a><span data-ttu-id="00e7d-196">선택적으로 컨트롤을 사용하도록 설정하려면</span><span class="sxs-lookup"><span data-stu-id="00e7d-196">To selectively enable controls</span></span>  
  
1.  <span data-ttu-id="00e7d-197">다음 `SetEnabled` 메서드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="00e7d-197">Add the following `SetEnabled` method.</span></span>  
  
     <span data-ttu-id="00e7d-198">[!code-vb[VbVbcnMyFileSystem#108](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-and-directories_7.vb)]</span><span class="sxs-lookup"><span data-stu-id="00e7d-198">[!code-vb[VbVbcnMyFileSystem#108](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-and-directories_7.vb)]</span></span>  
  
     <span data-ttu-id="00e7d-199">`ListBox`에서 항목이 선택되었는지에 따라 `SetEnabled` 메서드는 컨트롤의 사용 여부를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="00e7d-199">The `SetEnabled` method enables or disables controls depending on whether an item is selected in the `ListBox`.</span></span>  
  
2.  <span data-ttu-id="00e7d-200">양식의 `ListBox` 컨트롤을 두 번 클릭하여 `filesListBox`에 대한 `SelectedIndexChanged` 이벤트 처리기를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="00e7d-200">Create a `SelectedIndexChanged` event handler for `filesListBox` by double-clicking the `ListBox` control on the form.</span></span>  
  
3.  <span data-ttu-id="00e7d-201">새 `filesListBox_SelectedIndexChanged` 이벤트 처리기에서 `SetEnabled`에 호출을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="00e7d-201">Add a call to `SetEnabled` in the new `filesListBox_SelectedIndexChanged` event handler.</span></span>  
  
4.  <span data-ttu-id="00e7d-202">`browseButton_Click` 이벤트 처리기의 끝에서 `SetEnabled`에 호출을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="00e7d-202">Add a call to `SetEnabled` at the end of the `browseButton_Click` event handler.</span></span>  
  
5.  <span data-ttu-id="00e7d-203">`Form1_Load` 이벤트 처리기의 끝에서 `SetEnabled`에 호출을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="00e7d-203">Add a call to `SetEnabled` at the end of the `Form1_Load` event handler.</span></span>  
  
6.  <span data-ttu-id="00e7d-204">응용 프로그램을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="00e7d-204">Run the application.</span></span> <span data-ttu-id="00e7d-205">`ListBox`에서 항목을 선택하지 않으면 **결과 저장** 확인란 및 **검사** 단추가 활성화되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="00e7d-205">The **Save Results** check box and the **Examine** button are disabled if an item is not selected in the `ListBox`.</span></span>  
  
## <a name="full-example-using-mycomputerfilesystem"></a><span data-ttu-id="00e7d-206">My.Computer.FileSystem을 사용하는 전체 예제</span><span class="sxs-lookup"><span data-stu-id="00e7d-206">Full example using My.Computer.FileSystem</span></span>  
 <span data-ttu-id="00e7d-207">다음은 전체 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="00e7d-207">Following is the complete example.</span></span>  
  
 <span data-ttu-id="00e7d-208">[!code-vb[VbVbcnMyFileSystem#101](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-and-directories_8.vb)]</span><span class="sxs-lookup"><span data-stu-id="00e7d-208">[!code-vb[VbVbcnMyFileSystem#101](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-and-directories_8.vb)]</span></span>  
  
## <a name="full-example-using-systemio"></a><span data-ttu-id="00e7d-209">System.IO를 사용하는 전체 예제</span><span class="sxs-lookup"><span data-stu-id="00e7d-209">Full example using System.IO</span></span>  
 <span data-ttu-id="00e7d-210">동등한 다음 예제에서는 `My.Computer.FileSystem` 개체를 사용하는 대신 <xref:System.IO> 네임스페이스의 클래스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="00e7d-210">The following equivalent example uses classes from the <xref:System.IO> namespace instead of using `My.Computer.FileSystem` objects.</span></span>  
  
 <span data-ttu-id="00e7d-211">[!code-vb[VbVbcnMyFileSystem#111](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-and-directories_9.vb)]</span><span class="sxs-lookup"><span data-stu-id="00e7d-211">[!code-vb[VbVbcnMyFileSystem#111](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-and-directories_9.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00e7d-212">참고 항목</span><span class="sxs-lookup"><span data-stu-id="00e7d-212">See Also</span></span>  
 <span data-ttu-id="00e7d-213"><xref:System.IO></span><span class="sxs-lookup"><span data-stu-id="00e7d-213"><xref:System.IO></span></span>   
 <span data-ttu-id="00e7d-214"><xref:Microsoft.VisualBasic.FileIO.FileSystem></span><span class="sxs-lookup"><span data-stu-id="00e7d-214"><xref:Microsoft.VisualBasic.FileIO.FileSystem></span></span>   
 <span data-ttu-id="00e7d-215"><xref:Microsoft.VisualBasic.FileIO.FileSystem.CurrentDirectory%2A></span><span class="sxs-lookup"><span data-stu-id="00e7d-215"><xref:Microsoft.VisualBasic.FileIO.FileSystem.CurrentDirectory%2A></span></span>   
 [<span data-ttu-id="00e7d-216">연습: .NET Framework 메서드를 사용하여 파일 조작</span><span class="sxs-lookup"><span data-stu-id="00e7d-216">Walkthrough: Manipulating Files by Using .NET Framework Methods</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/walkthrough-manipulating-files-by-using-net-framework-methods.md)

