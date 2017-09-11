---
title: "방법: StreamReader를 사용하여 파일에서 텍스트 읽기(Visual Basic)"
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
- reading files, text
- text, reading from files
- reading text from files
- files, reading
ms.assetid: 384033c6-18f9-4d59-9610-36371226558f
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
ms.openlocfilehash: d895b32b1613462a6c8dedcc19040b5040f936ec
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-read-text-from-files-with-a-streamreader-visual-basic"></a><span data-ttu-id="74f83-102">방법: StreamReader를 사용하여 파일에서 텍스트 읽기(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="74f83-102">How to: Read Text from Files with a StreamReader (Visual Basic)</span></span>
<span data-ttu-id="74f83-103">`My.Computer.FileSystem` 개체는 <xref:System.IO.TextReader> 및 <xref:System.IO.TextWriter>를 여는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="74f83-103">The `My.Computer.FileSystem` object provides methods to open a <xref:System.IO.TextReader> and a <xref:System.IO.TextWriter>.</span></span> <span data-ttu-id="74f83-104">`OpenTextFileWriter` 및 `OpenTextFileReader` 메서드는 **모두** 탭을 선택한 경우에만 IntelliSense에 표시되는 고급 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="74f83-104">These methods, `OpenTextFileWriter` and `OpenTextFileReader`, are advanced methods that do not appear in IntelliSense unless you select the **All** tab.</span></span>  
  
### <a name="to-read-a-line-from-a-file-with-a-text-reader"></a><span data-ttu-id="74f83-105">텍스트 판독기를 사용하여 파일에서 줄을 읽으려면</span><span class="sxs-lookup"><span data-stu-id="74f83-105">To read a line from a file with a text reader</span></span>  
  
-   <span data-ttu-id="74f83-106">파일을 지정하여 `OpenTextFileReader` 메서드를 통해 <xref:System.IO.TextReader>를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="74f83-106">Use the `OpenTextFileReader` method to open the <xref:System.IO.TextReader>, specifying the file.</span></span> <span data-ttu-id="74f83-107">이 예제에서는 `testfile.txt`라는 파일을 열고 파일에서 줄을 읽은 다음 메시지 상자에 줄을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="74f83-107">This example opens the file named `testfile.txt`, reads a line from it, and displays the line in a message box.</span></span>  
  
     <span data-ttu-id="74f83-108">[!code-vb[VbFileIORead#1](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-text-from-files-with-a-streamreader_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="74f83-108">[!code-vb[VbFileIORead#1](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-text-from-files-with-a-streamreader_1.vb)]</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="74f83-109">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="74f83-109">Robust Programming</span></span>  
 <span data-ttu-id="74f83-110">읽은 파일은 텍스트 파일이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="74f83-110">The file that is read must be a text file.</span></span>  
  
 <span data-ttu-id="74f83-111">파일 이름을 바탕으로 파일 내용을 판단하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="74f83-111">Do not make decisions about the contents of the file based on the name of the file.</span></span> <span data-ttu-id="74f83-112">예를 들어 Form1.vb 파일이 Visual Basic 소스 파일이 아닐 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74f83-112">For example, the file Form1.vb may not be a Visual Basic source file.</span></span>  
  
 <span data-ttu-id="74f83-113">응용 프로그램에서 데이터를 사용하기 전에 모든 입력을 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="74f83-113">Verify all inputs before using the data in your application.</span></span> <span data-ttu-id="74f83-114">파일의 내용이 예상한 내용과 다를 수 있으며 파일을 읽는 메서드가 실패할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74f83-114">The contents of the file may not be what is expected, and methods to read from the file may fail.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="74f83-115">.NET Framework 보안</span><span class="sxs-lookup"><span data-stu-id="74f83-115">.NET Framework Security</span></span>  
 <span data-ttu-id="74f83-116">파일에서 읽으려면 어셈블리에 <xref:System.Security.Permissions.FileIOPermission> 클래스에서 부여한 권한 수준이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="74f83-116">To read from a file, your assembly requires a privilege level granted by the <xref:System.Security.Permissions.FileIOPermission> class.</span></span> <span data-ttu-id="74f83-117">부분 신뢰 컨텍스트에서 실행하는 경우 권한 부족으로 인해 코드에서 예외를 throw할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74f83-117">If you are running in a partial-trust context, the code might throw an exception due to insufficient privileges.</span></span> <span data-ttu-id="74f83-118">자세한 내용은 [코드 액세스 보안 기본 사항](https://msdn.microsoft.com/library/33tceax8)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="74f83-118">For more information, see [Code Access Security Basics](https://msdn.microsoft.com/library/33tceax8).</span></span> <span data-ttu-id="74f83-119">사용자에게 파일에 대한 액세스 권한도 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="74f83-119">The user also needs access to the file.</span></span> <span data-ttu-id="74f83-120">자세한 내용은 [ACL 기술 개요](http://msdn.microsoft.com/en-us/06fbf66d-6f02-4378-b863-b2f12e349045)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="74f83-120">For more information, see [ACL Technology Overview](http://msdn.microsoft.com/en-us/06fbf66d-6f02-4378-b863-b2f12e349045).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74f83-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="74f83-121">See Also</span></span>  
 <span data-ttu-id="74f83-122"><xref:Microsoft.VisualBasic.FileIO.FileSystem></span><span class="sxs-lookup"><span data-stu-id="74f83-122"><xref:Microsoft.VisualBasic.FileIO.FileSystem></span></span>   
 <span data-ttu-id="74f83-123"><xref:System.Windows.Forms.OpenFileDialog></span><span class="sxs-lookup"><span data-stu-id="74f83-123"><xref:System.Windows.Forms.OpenFileDialog></span></span>   
 <span data-ttu-id="74f83-124"><xref:Microsoft.VisualBasic.FileIO.FileSystem.OpenTextFileWriter%2A></span><span class="sxs-lookup"><span data-stu-id="74f83-124"><xref:Microsoft.VisualBasic.FileIO.FileSystem.OpenTextFileWriter%2A></span></span>   
 <span data-ttu-id="74f83-125"><xref:Microsoft.VisualBasic.FileIO.FileSystem.OpenTextFileReader%2A></span><span class="sxs-lookup"><span data-stu-id="74f83-125"><xref:Microsoft.VisualBasic.FileIO.FileSystem.OpenTextFileReader%2A></span></span>   
 <span data-ttu-id="74f83-126">[SaveFileDialog 구성 요소](../../../../framework/winforms/controls/savefiledialog-component-windows-forms.md) </span><span class="sxs-lookup"><span data-stu-id="74f83-126">[SaveFileDialog Component](../../../../framework/winforms/controls/savefiledialog-component-windows-forms.md) </span></span>  
 [<span data-ttu-id="74f83-127">파일 읽기</span><span class="sxs-lookup"><span data-stu-id="74f83-127">Reading from Files</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/reading-from-files.md)

