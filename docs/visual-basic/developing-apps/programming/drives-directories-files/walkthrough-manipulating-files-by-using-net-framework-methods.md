---
title: ".NET Framework 메서드를 사용하여 파일 조작(Visual Basic)"
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
- I/O [Visual Basic], walkthroughs
- text files, writing to
- reading text files
- text, writing to files
- files, searching
- StreamReader class, walkthroughs
- files, accessing
- I/O [Visual Basic], writing text to files
- writing to files, walkthroughs
- StreamWriter class, walkthroughs
- text files, reading
- I/O [Visual Basic], reading text from files
ms.assetid: 7d2109eb-f98a-4389-b43d-30f384aaa7d5
caps.latest.revision: 18
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
ms.openlocfilehash: eab8ebe0f1e6f3e86b9c4aa7c3b24a2763a27ffc
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="walkthrough-manipulating-files-by-using-net-framework-methods-visual-basic"></a><span data-ttu-id="f808d-102">연습: .NET Framework 메서드를 사용하여 파일 조작(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f808d-102">Walkthrough: Manipulating Files by Using .NET Framework Methods (Visual Basic)</span></span>
<span data-ttu-id="f808d-103">이 연습에서는 <xref:System.IO.StreamReader> 클래스를 사용하여 파일을 열고 읽는 방법, 파일이 액세스되고 있는지 확인하는 방법, <xref:System.IO.StreamReader> 클래스의 인스턴스로 파일 읽기 내에서 문자열을 검색하는 방법, <xref:System.IO.StreamWriter> 클래스를 사용하여 파일에 쓰는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f808d-103">This walkthrough demonstrates how to open and read a file using the <xref:System.IO.StreamReader> class, check to see if a file is being accessed, search for a string within a file read with an instance of the <xref:System.IO.StreamReader> class, and write to a file using the <xref:System.IO.StreamWriter> class.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="creating-the-application"></a><span data-ttu-id="f808d-104">응용 프로그램 작성</span><span class="sxs-lookup"><span data-stu-id="f808d-104">Creating the Application</span></span>  
 <span data-ttu-id="f808d-105">[!INCLUDE[vsprvs](~/includes/vsprvs-md.md)]를 시작하고 사용자가 지정된 파일에 기록하기 위해 사용할 수 있는 양식을 만들어 프로젝트를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="f808d-105">Start [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] and begin the project by creating a form that the user can use to write to the designated file.</span></span>  
  
#### <a name="to-create-the-project"></a><span data-ttu-id="f808d-106">프로젝트를 만들려면</span><span class="sxs-lookup"><span data-stu-id="f808d-106">To create the project</span></span>  
  
1.  <span data-ttu-id="f808d-107">**파일** 메뉴에서 **새 프로젝트**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f808d-107">On the **File** menu, select **New Project**.</span></span>  
  
2.  <span data-ttu-id="f808d-108">**새 프로젝트** 창에서 **Windows 응용 프로그램**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f808d-108">In the **New Project** pane, click **Windows Application**.</span></span>  
  
3.  <span data-ttu-id="f808d-109">**이름** 상자에 `MyDiary`를 입력한 다음 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f808d-109">In the **Name** box type `MyDiary` and click **OK**.</span></span>  
  
     [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)]<span data-ttu-id="f808d-110">에서 **솔루션 탐색기**에 프로젝트를 추가하면 **Windows Forms 디자이너**가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="f808d-110"> adds the project to **Solution Explorer**, and the **Windows Forms Designer** opens.</span></span>  
  
4.  <span data-ttu-id="f808d-111">다음 표의 컨트롤을 양식에 추가하고 속성의 해당 값을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f808d-111">Add the controls in the following table to the form and set the corresponding values for their properties.</span></span>  
  
|<span data-ttu-id="f808d-112">**개체**</span><span class="sxs-lookup"><span data-stu-id="f808d-112">**Object**</span></span>|<span data-ttu-id="f808d-113">**속성**</span><span class="sxs-lookup"><span data-stu-id="f808d-113">**Properties**</span></span>|<span data-ttu-id="f808d-114">**Value**</span><span class="sxs-lookup"><span data-stu-id="f808d-114">**Value**</span></span>|  
|---|---|---|   
|<xref:System.Windows.Forms.Button>|<span data-ttu-id="f808d-115">**Name**</span><span class="sxs-lookup"><span data-stu-id="f808d-115">**Name**</span></span><br /><br /> <span data-ttu-id="f808d-116">**Text**</span><span class="sxs-lookup"><span data-stu-id="f808d-116">**Text**</span></span>|`Submit`<br /><br /> <span data-ttu-id="f808d-117">**항목 제출**</span><span class="sxs-lookup"><span data-stu-id="f808d-117">**Submit Entry**</span></span>|  
|<xref:System.Windows.Forms.Button>|<span data-ttu-id="f808d-118">**Name**</span><span class="sxs-lookup"><span data-stu-id="f808d-118">**Name**</span></span><br /><br /> <span data-ttu-id="f808d-119">**Text**</span><span class="sxs-lookup"><span data-stu-id="f808d-119">**Text**</span></span>|`Clear`<br /><br /> <span data-ttu-id="f808d-120">**항목 지우기**</span><span class="sxs-lookup"><span data-stu-id="f808d-120">**Clear Entry**</span></span>|  
|<xref:System.Windows.Forms.TextBox>|<span data-ttu-id="f808d-121">**Name**</span><span class="sxs-lookup"><span data-stu-id="f808d-121">**Name**</span></span><br /><br /> <span data-ttu-id="f808d-122">**Text**</span><span class="sxs-lookup"><span data-stu-id="f808d-122">**Text**</span></span><br /><br /> <span data-ttu-id="f808d-123">**Multiline**</span><span class="sxs-lookup"><span data-stu-id="f808d-123">**Multiline**</span></span>|`Entry`<br /><br /> <span data-ttu-id="f808d-124">**내용을 입력하세요.**</span><span class="sxs-lookup"><span data-stu-id="f808d-124">**Please enter something.**</span></span><br /><br /> `False`|  
  
## <a name="writing-to-the-file"></a><span data-ttu-id="f808d-125">파일에 쓰기</span><span class="sxs-lookup"><span data-stu-id="f808d-125">Writing to the File</span></span>  
 <span data-ttu-id="f808d-126">응용 프로그램을 통해 파일에 쓰는 기능을 추가하려면 <xref:System.IO.StreamWriter> 클래스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f808d-126">To add the ability to write to a file via the application, use the <xref:System.IO.StreamWriter> class.</span></span> <span data-ttu-id="f808d-127"><xref:System.IO.StreamWriter>는 특정 인코딩에서 문자 출력용으로 설계된 반면, <xref:System.IO.Stream> 클래스는 바이트 입력 및 출력용으로 설계되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f808d-127"><xref:System.IO.StreamWriter> is designed for character output in a particular encoding, whereas the <xref:System.IO.Stream> class is designed for byte input and output.</span></span> <span data-ttu-id="f808d-128">표준 텍스트 파일에 정보의 줄을 쓰려면 <xref:System.IO.StreamWriter>를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f808d-128">Use <xref:System.IO.StreamWriter> for writing lines of information to a standard text file.</span></span> <span data-ttu-id="f808d-129"><xref:System.IO.StreamWriter> 클래스에 대한 자세한 내용은 <xref:System.IO.StreamWriter>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f808d-129">For more information on the <xref:System.IO.StreamWriter> class, see <xref:System.IO.StreamWriter>.</span></span>  
  
#### <a name="to-add-writing-functionality"></a><span data-ttu-id="f808d-130">쓰기 기능을 추가하려면</span><span class="sxs-lookup"><span data-stu-id="f808d-130">To add writing functionality</span></span>  
  
1.  <span data-ttu-id="f808d-131">**보기** 메뉴에서 **코드**를 선택하여 코드 편집기를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="f808d-131">From the **View** menu, choose **Code** to open the Code Editor.</span></span>  
  
2.  <span data-ttu-id="f808d-132">응용 프로그램은 <xref:System.IO> 네임스페이스를 참조하므로 다음 문을 코드의 시작 부분(`Public Class Form1`을 시작하는 양식에 대한 클래스 선언 전)에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f808d-132">Because the application references the <xref:System.IO> namespace, add the following statements at the very beginning of your code, before the class declaration for the form, which begins `Public Class Form1`.</span></span>  
  
     <span data-ttu-id="f808d-133">[!code-vb[VbVbcnMyFileSystem#35](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-by-using-net-framework-methods_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="f808d-133">[!code-vb[VbVbcnMyFileSystem#35](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-by-using-net-framework-methods_1.vb)]</span></span>  
  
     <span data-ttu-id="f808d-134">파일에 쓰기 전에 <xref:System.IO.StreamWriter> 클래스의 인스턴스를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f808d-134">Before writing to the file, you must create an instance of a <xref:System.IO.StreamWriter> class.</span></span>  
  
3.  <span data-ttu-id="f808d-135">**보기** 메뉴에서 **디자이너**를 선택하여 **Windows Forms 디자이너**로 돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="f808d-135">From the **View** menu, choose **Designer** to return to the **Windows Forms Designer**.</span></span> <span data-ttu-id="f808d-136">`Submit` 단추를 두 번 클릭하여 단추에 대한 <xref:System.Windows.Forms.Control.Click> 이벤트 처리기를 만들고 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f808d-136">Double-click the `Submit` button to create a <xref:System.Windows.Forms.Control.Click> event handler for the button, and then add the following code.</span></span>  
  
     <span data-ttu-id="f808d-137">[!code-vb[VbVbcnMyFileSystem#36](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-by-using-net-framework-methods_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="f808d-137">[!code-vb[VbVbcnMyFileSystem#36](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-by-using-net-framework-methods_2.vb)]</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f808d-138">Visual Studio IDE(통합 개발 환경)는 코드 편집기로 돌아가서, 코드를 추가해야 하는 이벤트 처리기 내부에 삽입점을 둡니다.</span><span class="sxs-lookup"><span data-stu-id="f808d-138">The Visual Studio Integrated Development Environment (IDE) will return to the Code Editor and position the insertion point within the event handler where you should add the code.</span></span>  
  
1.  <span data-ttu-id="f808d-139">파일에 쓰려면 <xref:System.IO.StreamWriter> 클래스의 <xref:System.IO.StreamWriter.Write%2A> 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f808d-139">To write to the file, use the <xref:System.IO.StreamWriter.Write%2A> method of the <xref:System.IO.StreamWriter> class.</span></span> <span data-ttu-id="f808d-140">`Dim fw As StreamWriter` 직후에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f808d-140">Add the following code directly after `Dim fw As StreamWriter`.</span></span> <span data-ttu-id="f808d-141">파일이 없으면 만들어지기 때문에 파일이 없을 경우 예외가 throw될 것을 우려하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f808d-141">You do not need to worry that an exception will be thrown if the file is not found, because it will be created if it does not already exist.</span></span>  
  
     <span data-ttu-id="f808d-142">[!code-vb[VbVbcnMyFileSystem#37](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-by-using-net-framework-methods_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="f808d-142">[!code-vb[VbVbcnMyFileSystem#37](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-by-using-net-framework-methods_3.vb)]</span></span>  
  
2.  <span data-ttu-id="f808d-143">`Dim ReadString As String` 직후에 다음 코드를 추가하여 사용자가 빈 항목을 제출할 수 없도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f808d-143">Make sure that the user cannot submit a blank entry by adding the following code directly after `Dim ReadString As String`.</span></span>  
  
     <span data-ttu-id="f808d-144">[!code-vb[VbVbcnMyFileSystem#38](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-by-using-net-framework-methods_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="f808d-144">[!code-vb[VbVbcnMyFileSystem#38](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-by-using-net-framework-methods_4.vb)]</span></span>  
  
3.  <span data-ttu-id="f808d-145">이것은 일기이므로 사용자는 각 항목에 날짜를 할당하고자 할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f808d-145">Because this is a diary, the user will want to assign a date to each entry.</span></span> <span data-ttu-id="f808d-146">`fw = New StreamWriter("C:\MyDiary.txt", True)` 뒤에 다음 코드를 삽입하여 `Today` 변수를 현재 날짜로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f808d-146">Insert the following code after `fw = New StreamWriter("C:\MyDiary.txt", True)` to set the variable `Today` to the current date.</span></span>  
  
     <span data-ttu-id="f808d-147">[!code-vb[VbVbcnMyFileSystem#39](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-by-using-net-framework-methods_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="f808d-147">[!code-vb[VbVbcnMyFileSystem#39](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-by-using-net-framework-methods_5.vb)]</span></span>  
  
4.  <span data-ttu-id="f808d-148">마지막으로 <xref:System.Windows.Forms.TextBox>를 지우는 코드를 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="f808d-148">Finally, attach code to clear the <xref:System.Windows.Forms.TextBox>.</span></span> <span data-ttu-id="f808d-149">다음 코드를 `Clear` 단추의 <xref:System.Windows.Forms.Control.Click> 이벤트에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f808d-149">Add the following code to the `Clear` button's <xref:System.Windows.Forms.Control.Click> event.</span></span>  
  
     <span data-ttu-id="f808d-150">[!code-vb[VbVbcnMyFileSystem#40](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-by-using-net-framework-methods_6.vb)]</span><span class="sxs-lookup"><span data-stu-id="f808d-150">[!code-vb[VbVbcnMyFileSystem#40](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-by-using-net-framework-methods_6.vb)]</span></span>  
  
## <a name="adding-display-features-to-the-diary"></a><span data-ttu-id="f808d-151">일기에 표시 기능 추가</span><span class="sxs-lookup"><span data-stu-id="f808d-151">Adding Display Features to the Diary</span></span>  
 <span data-ttu-id="f808d-152">이 섹션에서는 `DisplayEntry`<xref:System.Windows.Forms.TextBox>의 최신 항목을 표시하는 기능을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f808d-152">In this section, you add a feature that displays the latest entry in the `DisplayEntry`<xref:System.Windows.Forms.TextBox>.</span></span> <span data-ttu-id="f808d-153">다양한 항목을 표시하며 사용자가 `DisplayEntry`<xref:System.Windows.Forms.TextBox>에 표시할 항목을 선택할 수 있는 <xref:System.Windows.Forms.ComboBox>를 추가할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f808d-153">You can also add a <xref:System.Windows.Forms.ComboBox> that displays various entries and from which a user can select an entry to display in the `DisplayEntry`<xref:System.Windows.Forms.TextBox>.</span></span> <span data-ttu-id="f808d-154"><xref:System.IO.StreamReader> 클래스의 인스턴스는 `MyDiary.txt`에서 정보를 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="f808d-154">An instance of the <xref:System.IO.StreamReader> class reads from `MyDiary.txt`.</span></span> <span data-ttu-id="f808d-155"><xref:System.IO.StreamWriter> 클래스와 마찬가지로 <xref:System.IO.StreamReader>도 텍스트 파일에 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f808d-155">Like the <xref:System.IO.StreamWriter> class, <xref:System.IO.StreamReader> is intended for use with text files.</span></span>  
  
 <span data-ttu-id="f808d-156">이 연습의 이 섹션에서는 다음 표의 컨트롤을 양식에 추가하고 각 속성의 해당 값을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f808d-156">For this section of the walkthrough, add the controls in the following table to the form and set the corresponding values for their properties.</span></span>  
  
|<span data-ttu-id="f808d-157">컨트롤</span><span class="sxs-lookup"><span data-stu-id="f808d-157">Control</span></span>|<span data-ttu-id="f808d-158">속성</span><span class="sxs-lookup"><span data-stu-id="f808d-158">Properties</span></span>|<span data-ttu-id="f808d-159">값</span><span class="sxs-lookup"><span data-stu-id="f808d-159">Values</span></span>|  
|-------------|----------------|------------|  
|<xref:System.Windows.Forms.TextBox>|<span data-ttu-id="f808d-160">**Name**</span><span class="sxs-lookup"><span data-stu-id="f808d-160">**Name**</span></span><br /><br /> <span data-ttu-id="f808d-161">**Visible**</span><span class="sxs-lookup"><span data-stu-id="f808d-161">**Visible**</span></span><br /><br /> <span data-ttu-id="f808d-162">**Size**</span><span class="sxs-lookup"><span data-stu-id="f808d-162">**Size**</span></span><br /><br /> <span data-ttu-id="f808d-163">**Multiline**</span><span class="sxs-lookup"><span data-stu-id="f808d-163">**Multiline**</span></span>|`DisplayEntry`<br /><br /> `False`<br /><br /> `120,60`<br /><br /> `True`|  
|<xref:System.Windows.Forms.Button>|<span data-ttu-id="f808d-164">**Name**</span><span class="sxs-lookup"><span data-stu-id="f808d-164">**Name**</span></span><br /><br /> <span data-ttu-id="f808d-165">**Text**</span><span class="sxs-lookup"><span data-stu-id="f808d-165">**Text**</span></span>|`Display`<br /><br /> <span data-ttu-id="f808d-166">**표시**</span><span class="sxs-lookup"><span data-stu-id="f808d-166">**Display**</span></span>|  
|<xref:System.Windows.Forms.Button>|<span data-ttu-id="f808d-167">**Name**</span><span class="sxs-lookup"><span data-stu-id="f808d-167">**Name**</span></span><br /><br /> <span data-ttu-id="f808d-168">**Text**</span><span class="sxs-lookup"><span data-stu-id="f808d-168">**Text**</span></span>|`GetEntries`<br /><br /> <span data-ttu-id="f808d-169">**항목 가져오기**</span><span class="sxs-lookup"><span data-stu-id="f808d-169">**Get Entries**</span></span>|  
|<xref:System.Windows.Forms.ComboBox>|<span data-ttu-id="f808d-170">**Name**</span><span class="sxs-lookup"><span data-stu-id="f808d-170">**Name**</span></span><br /><br /> <span data-ttu-id="f808d-171">**Text**</span><span class="sxs-lookup"><span data-stu-id="f808d-171">**Text**</span></span><br /><br /> <span data-ttu-id="f808d-172">**Enabled**</span><span class="sxs-lookup"><span data-stu-id="f808d-172">**Enabled**</span></span>|`PickEntries`<br /><br /> <span data-ttu-id="f808d-173">**항목 선택**</span><span class="sxs-lookup"><span data-stu-id="f808d-173">**Select an Entry**</span></span><br /><br /> `False`|  
  
#### <a name="to-populate-the-combo-box"></a><span data-ttu-id="f808d-174">콤보 상자를 채우려면</span><span class="sxs-lookup"><span data-stu-id="f808d-174">To populate the combo box</span></span>  
  
1.  <span data-ttu-id="f808d-175">`PickEntries`<xref:System.Windows.Forms.ComboBox>는 사용자가 특정 날짜의 항목을 선택할 수 있도록 사용자가 각 항목을 제출하는 날짜를 표시하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f808d-175">The `PickEntries`<xref:System.Windows.Forms.ComboBox> is used to display the dates on which a user submits each entry, so the user can select an entry from a specific date.</span></span> <span data-ttu-id="f808d-176">`GetEntries` 단추에 대한 <xref:System.Windows.Forms.Control.Click> 이벤트 처리기를 만들어 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f808d-176">Create a <xref:System.Windows.Forms.Control.Click> event handler to the `GetEntries` button and add the following code.</span></span>  
  
     <span data-ttu-id="f808d-177">[!code-vb[VbVbcnMyFileSystem#41](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-by-using-net-framework-methods_7.vb)]</span><span class="sxs-lookup"><span data-stu-id="f808d-177">[!code-vb[VbVbcnMyFileSystem#41](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-by-using-net-framework-methods_7.vb)]</span></span>  
  
2.  <span data-ttu-id="f808d-178">코드를 테스트하려면 F5를 눌러 응용 프로그램을 컴파일한 다음 **항목 가져오기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f808d-178">To test your code, press F5 to compile the application, and then click **Get Entries**.</span></span> <span data-ttu-id="f808d-179"><xref:System.Windows.Forms.ComboBox>에서 드롭다운 화살표를 클릭하여 항목 날짜를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="f808d-179">Click the drop-down arrow in the <xref:System.Windows.Forms.ComboBox> to display the entry dates.</span></span>  
  
#### <a name="to-choose-and-display-individual-entries"></a><span data-ttu-id="f808d-180">개별 항목을 선택하고 표시하려면</span><span class="sxs-lookup"><span data-stu-id="f808d-180">To choose and display individual entries</span></span>  
  
1.  <span data-ttu-id="f808d-181">`Display` 단추에 대한 <xref:System.Windows.Forms.Control.Click> 이벤트 처리기를 만들어 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f808d-181">Create a <xref:System.Windows.Forms.Control.Click> event handler for the `Display` button and add the following code.</span></span>  
  
     <span data-ttu-id="f808d-182">[!code-vb[VbVbcnMyFileSystem#42](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-by-using-net-framework-methods_8.vb)]</span><span class="sxs-lookup"><span data-stu-id="f808d-182">[!code-vb[VbVbcnMyFileSystem#42](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-by-using-net-framework-methods_8.vb)]</span></span>  
  
2.  <span data-ttu-id="f808d-183">코드를 테스트하려면 F5를 눌러 응용 프로그램을 컴파일한 다음 항목을 제출합니다.</span><span class="sxs-lookup"><span data-stu-id="f808d-183">To test your code, press F5 to compile the application, and then submit an entry.</span></span> <span data-ttu-id="f808d-184">**항목 가져오기**를 클릭하고 <xref:System.Windows.Forms.ComboBox>에서 항목을 선택한 다음, **표시**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f808d-184">Click **Get Entries**, select an entry from the <xref:System.Windows.Forms.ComboBox>, and then click **Display**.</span></span> <span data-ttu-id="f808d-185">선택한 항목의 내용이 `DisplayEntry`<xref:System.Windows.Forms.TextBox>에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f808d-185">The contents of the selected entry appear in the `DisplayEntry`<xref:System.Windows.Forms.TextBox>.</span></span>  
  
## <a name="enabling-users-to-delete-or-modify-entries"></a><span data-ttu-id="f808d-186">사용자가 항목을 삭제 또는 수정하도록 설정</span><span class="sxs-lookup"><span data-stu-id="f808d-186">Enabling Users to Delete or Modify Entries</span></span>  
 <span data-ttu-id="f808d-187">마지막으로 `DeleteEntry` 및 `EditEntry` 단추를 사용하여, 사용자가 항목을 삭제 또는 수정하도록 설정하는 추가 기능을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f808d-187">Finally, you can include additional functionality enables users to delete or modify an entry by using `DeleteEntry` and `EditEntry` buttons.</span></span> <span data-ttu-id="f808d-188">항목이 표시되지 않으면 두 단추 모두 비활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="f808d-188">Both buttons remain disabled unless an entry is displayed.</span></span>  
  
 <span data-ttu-id="f808d-189">다음 표의 컨트롤을 양식에 추가하고 속성의 해당 값을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f808d-189">Add the controls in the following table to the form and set the corresponding values for their properties.</span></span>  
  
|<span data-ttu-id="f808d-190">컨트롤</span><span class="sxs-lookup"><span data-stu-id="f808d-190">Control</span></span>|<span data-ttu-id="f808d-191">속성</span><span class="sxs-lookup"><span data-stu-id="f808d-191">Properties</span></span>|<span data-ttu-id="f808d-192">값</span><span class="sxs-lookup"><span data-stu-id="f808d-192">Values</span></span>|  
|-------------|----------------|------------|  
|<xref:System.Windows.Forms.Button>|<span data-ttu-id="f808d-193">**Name**</span><span class="sxs-lookup"><span data-stu-id="f808d-193">**Name**</span></span><br /><br /> <span data-ttu-id="f808d-194">**Text**</span><span class="sxs-lookup"><span data-stu-id="f808d-194">**Text**</span></span><br /><br /> <span data-ttu-id="f808d-195">**Enabled**</span><span class="sxs-lookup"><span data-stu-id="f808d-195">**Enabled**</span></span>|`DeleteEntry`<br /><br /> <span data-ttu-id="f808d-196">**항목 삭제**</span><span class="sxs-lookup"><span data-stu-id="f808d-196">**Delete Entry**</span></span><br /><br /> `False`|  
|<xref:System.Windows.Forms.Button>|<span data-ttu-id="f808d-197">**Name**</span><span class="sxs-lookup"><span data-stu-id="f808d-197">**Name**</span></span><br /><br /> <span data-ttu-id="f808d-198">**Text**</span><span class="sxs-lookup"><span data-stu-id="f808d-198">**Text**</span></span><br /><br /> <span data-ttu-id="f808d-199">**Enabled**</span><span class="sxs-lookup"><span data-stu-id="f808d-199">**Enabled**</span></span>|`EditEntry`<br /><br /> <span data-ttu-id="f808d-200">**항목 편집**</span><span class="sxs-lookup"><span data-stu-id="f808d-200">**Edit Entry**</span></span><br /><br /> `False`|  
|<xref:System.Windows.Forms.Button>|<span data-ttu-id="f808d-201">**Name**</span><span class="sxs-lookup"><span data-stu-id="f808d-201">**Name**</span></span><br /><br /> <span data-ttu-id="f808d-202">**Text**</span><span class="sxs-lookup"><span data-stu-id="f808d-202">**Text**</span></span><br /><br /> <span data-ttu-id="f808d-203">**Enabled**</span><span class="sxs-lookup"><span data-stu-id="f808d-203">**Enabled**</span></span>|`SubmitEdit`<br /><br /> <span data-ttu-id="f808d-204">**편집 제출**</span><span class="sxs-lookup"><span data-stu-id="f808d-204">**Submit Edit**</span></span><br /><br /> `False`|  
  
#### <a name="to-enable-deletion-and-modification-of-entries"></a><span data-ttu-id="f808d-205">항목을 삭제 및 수정하도록 설정하려면</span><span class="sxs-lookup"><span data-stu-id="f808d-205">To enable deletion and modification of entries</span></span>  
  
1.  <span data-ttu-id="f808d-206">다음 코드를 `Display` 단추의 <xref:System.Windows.Forms.Control.Click> 이벤트에서 `DisplayEntry.Text = ReadString` 뒤에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f808d-206">Add the following code to the `Display` button's <xref:System.Windows.Forms.Control.Click> event, after `DisplayEntry.Text = ReadString`.</span></span>  
  
     <span data-ttu-id="f808d-207">[!code-vb[VbVbcnMyFileSystem#43](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-by-using-net-framework-methods_9.vb)]</span><span class="sxs-lookup"><span data-stu-id="f808d-207">[!code-vb[VbVbcnMyFileSystem#43](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-by-using-net-framework-methods_9.vb)]</span></span>  
  
2.  <span data-ttu-id="f808d-208">`DeleteEntry` 단추에 대한 <xref:System.Windows.Forms.Control.Click> 이벤트 처리기를 만들어 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f808d-208">Create a <xref:System.Windows.Forms.Control.Click> event handler for the `DeleteEntry` button and add the following code.</span></span>  
  
     <span data-ttu-id="f808d-209">[!code-vb[VbVbcnMyFileSystem#44](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-by-using-net-framework-methods_10.vb)]</span><span class="sxs-lookup"><span data-stu-id="f808d-209">[!code-vb[VbVbcnMyFileSystem#44](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-by-using-net-framework-methods_10.vb)]</span></span>  
  
3.  <span data-ttu-id="f808d-210">사용자가 항목을 표시하면 `EditEntry` 단추가 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="f808d-210">When a user displays an entry, the `EditEntry` button becomes enabled.</span></span> <span data-ttu-id="f808d-211">다음 코드를 `Display` 단추의 <xref:System.Windows.Forms.Control.Click> 이벤트에서 `DisplayEntry.Text = ReadString` 뒤에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f808d-211">Add the following code to the <xref:System.Windows.Forms.Control.Click> event of the `Display` button after `DisplayEntry.Text = ReadString`.</span></span>  
  
     <span data-ttu-id="f808d-212">[!code-vb[VbVbcnMyFileSystem#45](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-by-using-net-framework-methods_11.vb)]</span><span class="sxs-lookup"><span data-stu-id="f808d-212">[!code-vb[VbVbcnMyFileSystem#45](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-by-using-net-framework-methods_11.vb)]</span></span>  
  
4.  <span data-ttu-id="f808d-213">`EditEntry` 단추에 대한 <xref:System.Windows.Forms.Control.Click> 이벤트 처리기를 만들어 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f808d-213">Create a <xref:System.Windows.Forms.Control.Click> event handler for the `EditEntry` button and add the following code.</span></span>  
  
     <span data-ttu-id="f808d-214">[!code-vb[VbVbcnMyFileSystem#46](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-by-using-net-framework-methods_12.vb)]</span><span class="sxs-lookup"><span data-stu-id="f808d-214">[!code-vb[VbVbcnMyFileSystem#46](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-by-using-net-framework-methods_12.vb)]</span></span>  
  
5.  <span data-ttu-id="f808d-215">`SubmitEdit` 단추에 대한 <xref:System.Windows.Forms.Control.Click> 이벤트 처리기를 만들어 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f808d-215">Create a <xref:System.Windows.Forms.Control.Click> event handler for the `SubmitEdit` button and add the following code</span></span>  
  
     <span data-ttu-id="f808d-216">[!code-vb[VbVbcnMyFileSystem#47](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-by-using-net-framework-methods_13.vb)]</span><span class="sxs-lookup"><span data-stu-id="f808d-216">[!code-vb[VbVbcnMyFileSystem#47](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-by-using-net-framework-methods_13.vb)]</span></span>  
  
 <span data-ttu-id="f808d-217">코드를 테스트하려면 F5를 눌러 응용 프로그램을 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="f808d-217">To test your code, press F5 to compile the application.</span></span> <span data-ttu-id="f808d-218">**항목 가져오기**를 클릭하고 항목을 선택한 다음 **표시**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f808d-218">Click **Get Entries**, select an entry, and then click **Display**.</span></span> <span data-ttu-id="f808d-219">항목이 `DisplayEntry`<xref:System.Windows.Forms.TextBox>에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="f808d-219">The entry appears in the `DisplayEntry`<xref:System.Windows.Forms.TextBox>.</span></span> <span data-ttu-id="f808d-220">**항목 편집**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f808d-220">Click **Edit Entry**.</span></span> <span data-ttu-id="f808d-221">항목이 `Entry`<xref:System.Windows.Forms.TextBox>에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="f808d-221">The entry appears in the `Entry`<xref:System.Windows.Forms.TextBox>.</span></span> <span data-ttu-id="f808d-222">`Entry`<xref:System.Windows.Forms.TextBox>에서 항목을 편집하고 **편집 제출**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f808d-222">Edit the entry in the `Entry`<xref:System.Windows.Forms.TextBox> and click **Submit Edit**.</span></span> <span data-ttu-id="f808d-223">`MyDiary.txt` 파일을 열어 수정한 내용을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="f808d-223">Open the `MyDiary.txt` file to confirm your correction.</span></span> <span data-ttu-id="f808d-224">이제 항목을 선택하고 **항목 삭제**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f808d-224">Now select an entry and click **Delete Entry**.</span></span> <span data-ttu-id="f808d-225"><xref:System.Windows.Forms.MessageBox>에 확인을 요청하는 메시지가 표시되면 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f808d-225">When the <xref:System.Windows.Forms.MessageBox> requests confirmation, click **OK**.</span></span> <span data-ttu-id="f808d-226">응용 프로그램을 닫고 `MyDiary.txt`를 열어 삭제를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="f808d-226">Close the application and open `MyDiary.txt` to confirm the deletion.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f808d-227">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f808d-227">See Also</span></span>  
 <span data-ttu-id="f808d-228"><xref:System.IO.StreamReader></span><span class="sxs-lookup"><span data-stu-id="f808d-228"><xref:System.IO.StreamReader></span></span>   
 <span data-ttu-id="f808d-229"><xref:System.IO.StreamWriter></span><span class="sxs-lookup"><span data-stu-id="f808d-229"><xref:System.IO.StreamWriter></span></span>   
 [<span data-ttu-id="f808d-230">연습</span><span class="sxs-lookup"><span data-stu-id="f808d-230">Walkthroughs</span></span>](../../../../visual-basic/walkthroughs.md)

