---
title: Visual Basic에서 파일과 디렉터리 조작
ms.date: 07/20/2015
helpviewer_keywords:
- files [Visual Basic], reading text
- reading files [Visual Basic], text
- I/O [Visual Basic], walkthroughs
- text, writing to files
- text, reading from files
- reading text from files [Visual Basic], walkthroughs
- Visual Basic code, file access
- files [Visual Basic], writing text
- I/O [Visual Basic], writing text to files
- file access, walkthroughs
- writing to files [Visual Basic], walkthroughs
- I/O [Visual Basic], reading text from files
ms.assetid: cae77565-9f78-4e46-8e42-eb2f9f8e1ffd
ms.openlocfilehash: ab1c119d2c5cd9bfa0ff725774144bc65817cad4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33592511"
---
# <a name="walkthrough-manipulating-files-and-directories-in-visual-basic"></a><span data-ttu-id="2e2e8-102">연습: Visual Basic에서 파일과 디렉터리 조작</span><span class="sxs-lookup"><span data-stu-id="2e2e8-102">Walkthrough: Manipulating Files and Directories in Visual Basic</span></span>
<span data-ttu-id="2e2e8-103">이 연습에서는 Visual Basic에서 파일 I/O의 기본 개념을 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="2e2e8-103">This walkthrough provides an introduction to the fundamentals of file I/O in Visual Basic.</span></span> <span data-ttu-id="2e2e8-104">디렉터리에 텍스트 파일을 나열하고 검사하는 작은 응용 프로그램을 만드는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2e2e8-104">It describes how to create a small application that lists and examines text files in a directory.</span></span> <span data-ttu-id="2e2e8-105">선택한 각 텍스트 파일에 대해 응용 프로그램은 파일 특성 및 내용의 첫 줄을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2e2e8-105">For each selected text file, the application provides file attributes and the first line of content.</span></span> <span data-ttu-id="2e2e8-106">로그 파일에 정보를 기록하는 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e2e8-106">There is an option to write information to a log file.</span></span>  
  
 <span data-ttu-id="2e2e8-107">이 연습에서는 Visual Basic에서 사용 가능한 `My.Computer.FileSystem Object`의 멤버를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2e2e8-107">This walkthrough uses members of the `My.Computer.FileSystem Object`, which are available in Visual Basic.</span></span> <span data-ttu-id="2e2e8-108">자세한 내용은 <xref:Microsoft.VisualBasic.FileIO.FileSystem>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2e2e8-108">See <xref:Microsoft.VisualBasic.FileIO.FileSystem> for more information.</span></span> <span data-ttu-id="2e2e8-109">연습의 끝 부분에서 <xref:System.IO> 네임스페이스의 클래스를 사용하는 동등한 예제가 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="2e2e8-109">At the end of the walkthrough, an equivalent example is provided that uses classes from the <xref:System.IO> namespace.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-the-project"></a><span data-ttu-id="2e2e8-110">프로젝트를 만들려면</span><span class="sxs-lookup"><span data-stu-id="2e2e8-110">To create the project</span></span>  
  
1.  <span data-ttu-id="2e2e8-111">**파일** 메뉴에서 **새 프로젝트**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="2e2e8-111">On the **File** menu, click **New Project**.</span></span>  
  
     <span data-ttu-id="2e2e8-112">**새 프로젝트** 대화 상자가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="2e2e8-112">The **New Project** dialog box appears.</span></span>  
  
2.  <span data-ttu-id="2e2e8-113">**설치된 템플릿** 창에서 **Visual Basic**을 확장한 다음 **Windows**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="2e2e8-113">In the **Installed Templates** pane, expand **Visual Basic**, and then click **Windows**.</span></span> <span data-ttu-id="2e2e8-114">**템플릿** 창 가운데에서 **Windows Forms 응용 프로그램**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="2e2e8-114">In the **Templates** pane in the middle, click **Windows Forms Application**.</span></span>  
  
3.  <span data-ttu-id="2e2e8-115">**이름** 상자에 `FileExplorer`를 입력하여 프로젝트 이름을 설정한 다음 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="2e2e8-115">In the **Name** box, type `FileExplorer` to set the project name, and then click **OK**.</span></span>  
  
     <span data-ttu-id="2e2e8-116">Visual Studio에서 **솔루션 탐색기**에 프로젝트를 추가합니다. 그러면 Windows Forms 디자이너가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="2e2e8-116">Visual Studio adds the project to **Solution Explorer**, and the Windows Forms Designer opens.</span></span>  
  
4.  <span data-ttu-id="2e2e8-117">다음 표의 컨트롤을 양식에 추가하고 속성의 해당 값을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="2e2e8-117">Add the controls in the following table to the form, and set the corresponding values for their properties.</span></span>  
  
    |<span data-ttu-id="2e2e8-118">Control</span><span class="sxs-lookup"><span data-stu-id="2e2e8-118">Control</span></span>|<span data-ttu-id="2e2e8-119">속성</span><span class="sxs-lookup"><span data-stu-id="2e2e8-119">Property</span></span>|<span data-ttu-id="2e2e8-120">값</span><span class="sxs-lookup"><span data-stu-id="2e2e8-120">Value</span></span>|  
    |-------------|--------------|-----------|  
    |<span data-ttu-id="2e2e8-121">**ListBox**</span><span class="sxs-lookup"><span data-stu-id="2e2e8-121">**ListBox**</span></span>|<span data-ttu-id="2e2e8-122">**이름**</span><span class="sxs-lookup"><span data-stu-id="2e2e8-122">**Name**</span></span>|`filesListBox`|  
    |<span data-ttu-id="2e2e8-123">**Button**</span><span class="sxs-lookup"><span data-stu-id="2e2e8-123">**Button**</span></span>|<span data-ttu-id="2e2e8-124">**이름**</span><span class="sxs-lookup"><span data-stu-id="2e2e8-124">**Name**</span></span><br /><br /> <span data-ttu-id="2e2e8-125">**텍스트**</span><span class="sxs-lookup"><span data-stu-id="2e2e8-125">**Text**</span></span>|`browseButton`<br /><br /> <span data-ttu-id="2e2e8-126">**찾아보기**</span><span class="sxs-lookup"><span data-stu-id="2e2e8-126">**Browse**</span></span>|  
    |<span data-ttu-id="2e2e8-127">**Button**</span><span class="sxs-lookup"><span data-stu-id="2e2e8-127">**Button**</span></span>|<span data-ttu-id="2e2e8-128">**이름**</span><span class="sxs-lookup"><span data-stu-id="2e2e8-128">**Name**</span></span><br /><br /> <span data-ttu-id="2e2e8-129">**텍스트**</span><span class="sxs-lookup"><span data-stu-id="2e2e8-129">**Text**</span></span>|`examineButton`<br /><br /> <span data-ttu-id="2e2e8-130">**검사**</span><span class="sxs-lookup"><span data-stu-id="2e2e8-130">**Examine**</span></span>|  
    |<span data-ttu-id="2e2e8-131">**CheckBox**</span><span class="sxs-lookup"><span data-stu-id="2e2e8-131">**CheckBox**</span></span>|<span data-ttu-id="2e2e8-132">**이름**</span><span class="sxs-lookup"><span data-stu-id="2e2e8-132">**Name**</span></span><br /><br /> <span data-ttu-id="2e2e8-133">**텍스트**</span><span class="sxs-lookup"><span data-stu-id="2e2e8-133">**Text**</span></span>|`saveCheckBox`<br /><br /> <span data-ttu-id="2e2e8-134">**결과 저장**</span><span class="sxs-lookup"><span data-stu-id="2e2e8-134">**Save Results**</span></span>|  
    |<span data-ttu-id="2e2e8-135">**FolderBrowserDialog**</span><span class="sxs-lookup"><span data-stu-id="2e2e8-135">**FolderBrowserDialog**</span></span>|<span data-ttu-id="2e2e8-136">**이름**</span><span class="sxs-lookup"><span data-stu-id="2e2e8-136">**Name**</span></span>|`FolderBrowserDialog1`|  
  
### <a name="to-select-a-folder-and-list-files-in-a-folder"></a><span data-ttu-id="2e2e8-137">폴더를 선택하고 폴더에 파일을 나열하려면</span><span class="sxs-lookup"><span data-stu-id="2e2e8-137">To select a folder, and list files in a folder</span></span>  
  
1.  <span data-ttu-id="2e2e8-138">양식의 컨트롤을 두 번 클릭하여 `browseButton`에 대한 `Click` 이벤트 처리기를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2e2e8-138">Create a `Click` event handler for `browseButton` by double-clicking the control on the form.</span></span> <span data-ttu-id="2e2e8-139">코드 편집기가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="2e2e8-139">The Code Editor opens.</span></span>  
  
2.  <span data-ttu-id="2e2e8-140">다음 코드를 `Click` 이벤트 처리기에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2e2e8-140">Add the following code to the `Click` event handler.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#103](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-and-directories_1.vb)]  
  
     <span data-ttu-id="2e2e8-141">`FolderBrowserDialog1.ShowDialog` 호출은 **폴더 찾아보기** 대화 상자를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="2e2e8-141">The `FolderBrowserDialog1.ShowDialog` call opens the **Browse For Folder** dialog box.</span></span> <span data-ttu-id="2e2e8-142">사용자가 **확인**을 클릭하면 <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> 속성이 `ListFiles` 메서드로 인수에 전송됩니다. 다음 단계에서 이 메서드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2e2e8-142">After the user clicks **OK**, the <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> property is sent as an argument to the `ListFiles` method, which is added in the next step.</span></span>  
  
3.  <span data-ttu-id="2e2e8-143">다음 `ListFiles` 메서드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2e2e8-143">Add the following `ListFiles` method.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#104](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-and-directories_2.vb)]  
  
     <span data-ttu-id="2e2e8-144">이 코드는 먼저 **ListBox**를 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="2e2e8-144">This code first clears the **ListBox**.</span></span>  
  
     <span data-ttu-id="2e2e8-145"><xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFiles%2A> 메서드는 디렉터리에 있는 각 파일에 대해 나하씩 문자열 컬렉션을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="2e2e8-145">The <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFiles%2A> method then retrieves a collection of strings, one for each file in the directory.</span></span> <span data-ttu-id="2e2e8-146">`GetFiles` 메서드는 특정 패턴과 일치하는 파일을 검색하기 위해 패턴 인수를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="2e2e8-146">The `GetFiles` method accepts a search pattern argument to retrieve files that match a particular pattern.</span></span> <span data-ttu-id="2e2e8-147">이 예제에서는 확장명이 .txt인 파일만 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="2e2e8-147">In this example, only files that have the extension .txt are returned.</span></span>  
  
     <span data-ttu-id="2e2e8-148">`GetFiles` 메서드에 의해 반환되는 문자열은 **ListBox**에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="2e2e8-148">The strings that are returned by the `GetFiles` method are then added to the **ListBox**.</span></span>  
  
4.  <span data-ttu-id="2e2e8-149">응용 프로그램을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2e2e8-149">Run the application.</span></span> <span data-ttu-id="2e2e8-150">**찾아보기** 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="2e2e8-150">Click the **Browse** button.</span></span> <span data-ttu-id="2e2e8-151">**폴더 찾아보기** 대화 상자에서 .txt 파일이 있는 폴더로 이동하여 폴더를 선택하고 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="2e2e8-151">In the **Browse For Folder** dialog box, browse to a folder that contains .txt files, and then select the folder and click **OK**.</span></span>  
  
     <span data-ttu-id="2e2e8-152">`ListBox`에는 선택한 폴더에 있는 .txt 파일의 목록이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e2e8-152">The `ListBox` contains a list of .txt files in the selected folder.</span></span>  
  
5.  <span data-ttu-id="2e2e8-153">응용 프로그램 실행을 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="2e2e8-153">Stop running the application.</span></span>  
  
### <a name="to-obtain-attributes-of-a-file-and-content-from-a-text-file"></a><span data-ttu-id="2e2e8-154">파일의 특성을 및 텍스트 파일의 내용을 가져오려면</span><span class="sxs-lookup"><span data-stu-id="2e2e8-154">To obtain attributes of a file, and content from a text file</span></span>  
  
1.  <span data-ttu-id="2e2e8-155">양식의 컨트롤을 두 번 클릭하여 `examineButton`에 대한 `Click` 이벤트 처리기를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2e2e8-155">Create a `Click` event handler for `examineButton` by double-clicking the control on the form.</span></span>  
  
2.  <span data-ttu-id="2e2e8-156">다음 코드를 `Click` 이벤트 처리기에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2e2e8-156">Add the following code to the `Click` event handler.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#105](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-and-directories_3.vb)]  
  
     <span data-ttu-id="2e2e8-157">이 코드는 항목이 `ListBox`에서 선택되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="2e2e8-157">The code verifies that an item is selected in the `ListBox`.</span></span> <span data-ttu-id="2e2e8-158">그런 다음 `ListBox`에서 파일 경로 항목을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="2e2e8-158">It then obtains the file path entry from the `ListBox`.</span></span> <span data-ttu-id="2e2e8-159"><xref:Microsoft.VisualBasic.FileIO.FileSystem.FileExists%2A> 메서드는 파일이 아직 있는지를 확인하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2e2e8-159">The <xref:Microsoft.VisualBasic.FileIO.FileSystem.FileExists%2A> method is used to check whether the file still exists.</span></span>  
  
     <span data-ttu-id="2e2e8-160">파일 경로가 인수로서 `GetTextForOutput` 메서드로 전송됩니다. 이 메서드는 다음 단계에서 추가되어,</span><span class="sxs-lookup"><span data-stu-id="2e2e8-160">The file path is sent as an argument to the `GetTextForOutput` method, which is added in the next step.</span></span> <span data-ttu-id="2e2e8-161">파일 정보를 포함하는 문자열을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="2e2e8-161">This method returns a string that contains file information.</span></span> <span data-ttu-id="2e2e8-162">파일 정보는 **MessageBox**에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="2e2e8-162">The file information appears in a **MessageBox**.</span></span>  
  
3.  <span data-ttu-id="2e2e8-163">다음 `GetTextForOutput` 메서드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2e2e8-163">Add the following `GetTextForOutput` method.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#107](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-and-directories_4.vb)]  
  
     <span data-ttu-id="2e2e8-164">이 코드는 <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFileInfo%2A> 메서드를 사용하여 파일 매개 변수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="2e2e8-164">The code uses the <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFileInfo%2A> method to obtain file parameters.</span></span> <span data-ttu-id="2e2e8-165">파일 매개 변수는 <xref:System.Text.StringBuilder>에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="2e2e8-165">The file parameters are added to a <xref:System.Text.StringBuilder>.</span></span>  
  
     <span data-ttu-id="2e2e8-166"><xref:Microsoft.VisualBasic.FileIO.FileSystem.OpenTextFileReader%2A> 메서드는 파일 내용을 <xref:System.IO.StreamReader>로 읽어들입니다.</span><span class="sxs-lookup"><span data-stu-id="2e2e8-166">The <xref:Microsoft.VisualBasic.FileIO.FileSystem.OpenTextFileReader%2A> method reads the file contents into a <xref:System.IO.StreamReader>.</span></span> <span data-ttu-id="2e2e8-167">내용의 첫 번째 줄을 `StreamReader`에서 가져와 `StringBuilder`에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2e2e8-167">The first line of the contents is obtained from the `StreamReader` and is added to the `StringBuilder`.</span></span>  
  
4.  <span data-ttu-id="2e2e8-168">응용 프로그램을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2e2e8-168">Run the application.</span></span> <span data-ttu-id="2e2e8-169">**찾아보기**를 클릭하고 .txt 파일이 포함된 폴더로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="2e2e8-169">Click **Browse**, and browse to a folder that contains .txt files.</span></span> <span data-ttu-id="2e2e8-170">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="2e2e8-170">Click **OK**.</span></span>  
  
     <span data-ttu-id="2e2e8-171">`ListBox`에서 파일을 선택하고 **검사**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="2e2e8-171">Select a file in the `ListBox`, and then click **Examine**.</span></span> <span data-ttu-id="2e2e8-172">`MessageBox`에 파일 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2e2e8-172">A `MessageBox` shows the file information.</span></span>  
  
5.  <span data-ttu-id="2e2e8-173">응용 프로그램 실행을 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="2e2e8-173">Stop running the application.</span></span>  
  
### <a name="to-add-a-log-entry"></a><span data-ttu-id="2e2e8-174">로그 항목을 추가하려면</span><span class="sxs-lookup"><span data-stu-id="2e2e8-174">To add a log entry</span></span>  
  
1.  <span data-ttu-id="2e2e8-175">다음 코드를 `examineButton_Click` 이벤트 처리기의 끝에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2e2e8-175">Add the following code to the end of the `examineButton_Click` event handler.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#106](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-and-directories_5.vb)]  
  
     <span data-ttu-id="2e2e8-176">이 코드는 선택한 파일과 동일한 디렉터리에 로그 파일을 저장하도록 로그 파일 경로를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="2e2e8-176">The code sets the log file path to put the log file in the same directory as that of the selected file.</span></span> <span data-ttu-id="2e2e8-177">로그 항목의 텍스트는 파일 정보 뒤에 현재 날짜 및 시간으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="2e2e8-177">The text of the log entry is set to the current date and time followed by the file information.</span></span>  
  
     <span data-ttu-id="2e2e8-178">`append` 인수가 `True`로 설정된 <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A> 메서드를 사용하여 로그 항목을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2e2e8-178">The <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A> method, with the `append` argument set to `True`, is used to create the log entry.</span></span>  
  
2.  <span data-ttu-id="2e2e8-179">응용 프로그램을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2e2e8-179">Run the application.</span></span> <span data-ttu-id="2e2e8-180">텍스트 파일로 이동하고, `ListBox`에서 선택하고, **결과 저장** 확인란을 선택한 다음 **검사**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="2e2e8-180">Browse to a text file, select it in the `ListBox`, select the **Save Results** check box, and then click **Examine**.</span></span> <span data-ttu-id="2e2e8-181">로그 항목이 `log.txt` 파일에 기록되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="2e2e8-181">Verify that the log entry is written to the `log.txt` file.</span></span>  
  
3.  <span data-ttu-id="2e2e8-182">응용 프로그램 실행을 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="2e2e8-182">Stop running the application.</span></span>  
  
### <a name="to-use-the-current-directory"></a><span data-ttu-id="2e2e8-183">현재 디렉터리를 사용하려면</span><span class="sxs-lookup"><span data-stu-id="2e2e8-183">To use the current directory</span></span>  
  
1.  <span data-ttu-id="2e2e8-184">양식을 두 번 클릭하여 `Form1_Load`에 대한 이벤트 처리기를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2e2e8-184">Create an event handler for `Form1_Load` by double-clicking the form.</span></span>  
  
2.  <span data-ttu-id="2e2e8-185">다음 코드를 이벤트 처리기에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2e2e8-185">Add the following code to the event handler.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#102](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-and-directories_6.vb)]  
  
     <span data-ttu-id="2e2e8-186">이 코드는 폴더 브라우저의 기본 디렉터리를 현재 디렉터리로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="2e2e8-186">This code sets the default directory of the folder browser to the current directory.</span></span>  
  
3.  <span data-ttu-id="2e2e8-187">응용 프로그램을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2e2e8-187">Run the application.</span></span> <span data-ttu-id="2e2e8-188">**찾아보기**를 처음 클릭하면 **폴더 찾아보기** 대화 상자가 현재 디렉터리로 열립니다.</span><span class="sxs-lookup"><span data-stu-id="2e2e8-188">When you click **Browse** the first time, the **Browse For Folder** dialog box opens to the current directory.</span></span>  
  
4.  <span data-ttu-id="2e2e8-189">응용 프로그램 실행을 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="2e2e8-189">Stop running the application.</span></span>  
  
### <a name="to-selectively-enable-controls"></a><span data-ttu-id="2e2e8-190">선택적으로 컨트롤을 사용하도록 설정하려면</span><span class="sxs-lookup"><span data-stu-id="2e2e8-190">To selectively enable controls</span></span>  
  
1.  <span data-ttu-id="2e2e8-191">다음 `SetEnabled` 메서드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2e2e8-191">Add the following `SetEnabled` method.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#108](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-and-directories_7.vb)]  
  
     <span data-ttu-id="2e2e8-192">`ListBox`에서 항목이 선택되었는지에 따라 `SetEnabled` 메서드는 컨트롤의 사용 여부를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="2e2e8-192">The `SetEnabled` method enables or disables controls depending on whether an item is selected in the `ListBox`.</span></span>  
  
2.  <span data-ttu-id="2e2e8-193">양식의 `ListBox` 컨트롤을 두 번 클릭하여 `filesListBox`에 대한 `SelectedIndexChanged` 이벤트 처리기를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2e2e8-193">Create a `SelectedIndexChanged` event handler for `filesListBox` by double-clicking the `ListBox` control on the form.</span></span>  
  
3.  <span data-ttu-id="2e2e8-194">새 `filesListBox_SelectedIndexChanged` 이벤트 처리기에서 `SetEnabled`에 호출을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2e2e8-194">Add a call to `SetEnabled` in the new `filesListBox_SelectedIndexChanged` event handler.</span></span>  
  
4.  <span data-ttu-id="2e2e8-195">`browseButton_Click` 이벤트 처리기의 끝에서 `SetEnabled`에 호출을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2e2e8-195">Add a call to `SetEnabled` at the end of the `browseButton_Click` event handler.</span></span>  
  
5.  <span data-ttu-id="2e2e8-196">`Form1_Load` 이벤트 처리기의 끝에서 `SetEnabled`에 호출을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2e2e8-196">Add a call to `SetEnabled` at the end of the `Form1_Load` event handler.</span></span>  
  
6.  <span data-ttu-id="2e2e8-197">응용 프로그램을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2e2e8-197">Run the application.</span></span> <span data-ttu-id="2e2e8-198">`ListBox`에서 항목을 선택하지 않으면 **결과 저장** 확인란 및 **검사** 단추가 활성화되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2e2e8-198">The **Save Results** check box and the **Examine** button are disabled if an item is not selected in the `ListBox`.</span></span>  
  
## <a name="full-example-using-mycomputerfilesystem"></a><span data-ttu-id="2e2e8-199">My.Computer.FileSystem을 사용하는 전체 예제</span><span class="sxs-lookup"><span data-stu-id="2e2e8-199">Full example using My.Computer.FileSystem</span></span>  
 <span data-ttu-id="2e2e8-200">다음은 전체 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="2e2e8-200">Following is the complete example.</span></span>  
  
 [!code-vb[VbVbcnMyFileSystem#101](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-and-directories_8.vb)]  
  
## <a name="full-example-using-systemio"></a><span data-ttu-id="2e2e8-201">System.IO를 사용하는 전체 예제</span><span class="sxs-lookup"><span data-stu-id="2e2e8-201">Full example using System.IO</span></span>  
 <span data-ttu-id="2e2e8-202">동등한 다음 예제에서는 `My.Computer.FileSystem` 개체를 사용하는 대신 <xref:System.IO> 네임스페이스의 클래스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2e2e8-202">The following equivalent example uses classes from the <xref:System.IO> namespace instead of using `My.Computer.FileSystem` objects.</span></span>  
  
 [!code-vb[VbVbcnMyFileSystem#111](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-and-directories_9.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="2e2e8-203">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2e2e8-203">See Also</span></span>  
 <xref:System.IO>  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem>  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.CurrentDirectory%2A>  
 [<span data-ttu-id="2e2e8-204">연습: .NET Framework 메서드를 사용하여 파일 조작</span><span class="sxs-lookup"><span data-stu-id="2e2e8-204">Walkthrough: Manipulating Files by Using .NET Framework Methods</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/walkthrough-manipulating-files-by-using-net-framework-methods.md)
