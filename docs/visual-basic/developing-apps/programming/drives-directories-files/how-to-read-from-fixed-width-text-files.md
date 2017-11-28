---
title: "방법: Visual Basic에서 고정 너비 텍스트 파일 읽기"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- fixed-width text file
- reading text files [Visual Basic], fixed-width
- files [Visual Basic], parsing
- text files [Visual Basic], tasks
- text files [Visual Basic], reading
ms.assetid: 99be5692-967a-4e85-993e-cd18139a5a69
caps.latest.revision: "24"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a5caa124af1bf4681a4c061f453ce5e09ec2dae7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-read-from-fixed-width-text-files-in-visual-basic"></a><span data-ttu-id="85f69-102">방법: Visual Basic에서 고정 너비 텍스트 파일 읽기</span><span class="sxs-lookup"><span data-stu-id="85f69-102">How to: read from fixed-width text files in Visual Basic</span></span>
<span data-ttu-id="85f69-103">`TextFieldParser` 개체는 로그와 같은 구조적 텍스트 파일을 쉽고 효율적으로 구문 분석하는 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="85f69-103">The `TextFieldParser` object provides a way to easily and efficiently parse structured text files, such as logs.</span></span>  
  
 <span data-ttu-id="85f69-104">`TextFieldType` 속성은 구문 분석된 파일이 구분된 파일인지 또는 고정 너비 텍스트 필드가 있는 파일인지를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="85f69-104">The `TextFieldType` property defines whether the parsed file is a delimited file or one that has fixed-width fields of text.</span></span> <span data-ttu-id="85f69-105">고정 너비 텍스트 파일의 끝에 있는 필드는 가변 너비를 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85f69-105">In a fixed-width text file, the field at the end can have a variable width.</span></span> <span data-ttu-id="85f69-106">끝에 있는 필드에 가변 너비를 지정하려면 0 이하의 너비로 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="85f69-106">To specify that the field at the end has a variable width, define it to have a width less than or equal to zero.</span></span>  
  
### <a name="to-parse-a-fixed-width-text-file"></a><span data-ttu-id="85f69-107">고정 너비 텍스트 파일을 구문 분석하려면</span><span class="sxs-lookup"><span data-stu-id="85f69-107">To parse a fixed-width text file</span></span>  
  
1.  <span data-ttu-id="85f69-108">새 `TextFieldParser`를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="85f69-108">Create a new `TextFieldParser`.</span></span> <span data-ttu-id="85f69-109">다음 코드는 `Reader`라는 `TextFieldParser`를 만들고 `test.log` 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="85f69-109">The following code creates the `TextFieldParser` named `Reader` and opens the file `test.log`.</span></span>  
  
     [!code-vb[VbFileIORead#9](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-fixed-width-text-files_1.vb)]  
  
2.  <span data-ttu-id="85f69-110">너비와 형식을 정의하여 `TextFieldType` 속성을 `FixedWidth`로 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="85f69-110">Define the `TextFieldType` property as `FixedWidth`, defining the width and format.</span></span> <span data-ttu-id="85f69-111">다음 코드는 텍스트 열을 정의합니다. 첫 번째 열은 너비가 5자이고, 두 번째 열은 10자, 세 번째 열은 11자, 네 번째 열은 가변 너비입니다.</span><span class="sxs-lookup"><span data-stu-id="85f69-111">The following code defines the columns of text; the first is 5 characters wide, the second 10, the third 11, and the fourth is of variable width.</span></span>  
  
     [!code-vb[VbFileIORead#10](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-fixed-width-text-files_2.vb)]  
  
3.  <span data-ttu-id="85f69-112">파일의 필드를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="85f69-112">Loop through the fields in the file.</span></span> <span data-ttu-id="85f69-113">손상된 줄이 있는 경우 오류를 보고하고 구문 분석을 계속합니다.</span><span class="sxs-lookup"><span data-stu-id="85f69-113">If any lines are corrupted, report an error and continue parsing.</span></span>  
  
     [!code-vb[VbFileIORead#11](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-fixed-width-text-files_3.vb)]  
  
4.  <span data-ttu-id="85f69-114">`End While` 및 `End Using`을 사용하여 `While` 및 `Using` 블록을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="85f69-114">Close the `While` and `Using` blocks with `End While` and `End Using`.</span></span>  
  
     [!code-vb[VbFileIORead#12](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-fixed-width-text-files_4.vb)]  
  
## <a name="example"></a><span data-ttu-id="85f69-115">예제</span><span class="sxs-lookup"><span data-stu-id="85f69-115">Example</span></span>  
 <span data-ttu-id="85f69-116">이 예제에서는 `test.log` 파일에서 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="85f69-116">This example reads from the file `test.log`.</span></span>  
  
 [!code-vb[VbFileIORead#13](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-fixed-width-text-files_5.vb)]  
  
## <a name="robust-programming"></a><span data-ttu-id="85f69-117">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="85f69-117">Robust programming</span></span>  
 <span data-ttu-id="85f69-118">다음 조건에서 예외가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="85f69-118">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="85f69-119">지정한 형식을 사용하여 행을 구문 분석할 수 없는 경우(<xref:Microsoft.VisualBasic.FileIO.MalformedLineException>).</span><span class="sxs-lookup"><span data-stu-id="85f69-119">A row cannot be parsed using the specified format (<xref:Microsoft.VisualBasic.FileIO.MalformedLineException>).</span></span> <span data-ttu-id="85f69-120">예외 메시지에는 예외를 발생시키는 줄이 지정되어 있지만 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.ErrorLine%2A> 속성은 해당 줄에 포함되어 있는 텍스트에 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="85f69-120">The exception message specifies the line causing the exception, while the <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.ErrorLine%2A> property is assigned to the text contained in the line.</span></span>  
  
-   <span data-ttu-id="85f69-121">지정한 파일이 없는 경우(<xref:System.IO.FileNotFoundException>)</span><span class="sxs-lookup"><span data-stu-id="85f69-121">The specified file does not exist (<xref:System.IO.FileNotFoundException>).</span></span>  
  
-   <span data-ttu-id="85f69-122">사용자에게 파일에 액세스할 수 있는 권한이 없는 부분 신뢰 상황인 경우</span><span class="sxs-lookup"><span data-stu-id="85f69-122">A partial-trust situation in which the user does not have sufficient permissions to access the file.</span></span> <span data-ttu-id="85f69-123">(<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="85f69-123">(<xref:System.Security.SecurityException>).</span></span>  
  
-   <span data-ttu-id="85f69-124">경로가 너무 긴 경우(<xref:System.IO.PathTooLongException>)</span><span class="sxs-lookup"><span data-stu-id="85f69-124">The path is too long (<xref:System.IO.PathTooLongException>).</span></span>  
  
-   <span data-ttu-id="85f69-125">사용자에게 파일에 액세스할 수 있는 권한이 없는 경우(<xref:System.UnauthorizedAccessException>)</span><span class="sxs-lookup"><span data-stu-id="85f69-125">The user does not have sufficient permissions to access the file (<xref:System.UnauthorizedAccessException>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85f69-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="85f69-126">See also</span></span>  
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser?displayProperty=nameWithType>  
 [<span data-ttu-id="85f69-127">방법: 쉼표로 구분된 텍스트 파일에서 읽기</span><span class="sxs-lookup"><span data-stu-id="85f69-127">How to: Read From Comma-Delimited Text Files</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-comma-delimited-text-files.md)  
 [<span data-ttu-id="85f69-128">방법: 여러 형식의 텍스트 파일에서 읽기</span><span class="sxs-lookup"><span data-stu-id="85f69-128">How to: Read From Text Files with Multiple Formats</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-text-files-with-multiple-formats.md)  
 [<span data-ttu-id="85f69-129">TextFieldParser 개체를 사용하여 텍스트 파일 구문 분석</span><span class="sxs-lookup"><span data-stu-id="85f69-129">Parsing Text Files with the TextFieldParser Object</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/parsing-text-files-with-the-textfieldparser-object.md)  
 [<span data-ttu-id="85f69-130">연습: Visual Basic에서 파일과 디렉터리 조작</span><span class="sxs-lookup"><span data-stu-id="85f69-130">Walkthrough: Manipulating Files and Directories in Visual Basic</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/walkthrough-manipulating-files-and-directories.md)  
 [<span data-ttu-id="85f69-131">문제 해결: 텍스트 파일 읽기 및 쓰기</span><span class="sxs-lookup"><span data-stu-id="85f69-131">Troubleshooting: Reading from and Writing to Text Files</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/troubleshooting-reading-from-and-writing-to-text-files.md)  
 
