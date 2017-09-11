---
title: "방법: Visual Basic에서 파일 만들기"
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
- text files, creating
- files, creating
ms.assetid: 0253bb6d-5519-4a50-b882-b93ef5cca0d9
caps.latest.revision: 15
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
ms.openlocfilehash: d06d274b31afad0a437405d1679e0be7548f2e14
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-create-a-file-in-visual-basic"></a><span data-ttu-id="80a70-102">방법: Visual Basic에서 파일 만들기</span><span class="sxs-lookup"><span data-stu-id="80a70-102">How to: Create a File in Visual Basic</span></span>
<span data-ttu-id="80a70-103">이 예제에서는 <xref:System.IO.File> 클래스의 <xref:System.IO.File.Create%2A> 메서드를 사용하여 지정된 경로에 빈 텍스트 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="80a70-103">This example creates an empty text file at the specified path using the <xref:System.IO.File.Create%2A> method in the <xref:System.IO.File> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="80a70-104">예제</span><span class="sxs-lookup"><span data-stu-id="80a70-104">Example</span></span>  
 <span data-ttu-id="80a70-105">[!code-vb[VbFileIOMisc#1](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-create-a-file_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="80a70-105">[!code-vb[VbFileIOMisc#1](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-create-a-file_1.vb)]</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="80a70-106">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="80a70-106">Compiling the Code</span></span>  
 <span data-ttu-id="80a70-107">파일에 쓰려면 `file` 변수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="80a70-107">Use the `file` variable to write to the file.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="80a70-108">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="80a70-108">Robust Programming</span></span>  
 <span data-ttu-id="80a70-109">파일이 이미 있으면 대체됩니다.</span><span class="sxs-lookup"><span data-stu-id="80a70-109">If the file already exists, it is replaced.</span></span>  
  
 <span data-ttu-id="80a70-110">다음 조건에서 예외가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="80a70-110">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="80a70-111">경로 이름 형식이 잘못되었습니다.</span><span class="sxs-lookup"><span data-stu-id="80a70-111">The path name is malformed.</span></span> <span data-ttu-id="80a70-112">예를 들어 잘못된 문자를 포함하거나 공백만으로 이루어져 있습니다(<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="80a70-112">For example, it contains illegal characters or is only white space (<xref:System.ArgumentException>).</span></span>  
  
-   <span data-ttu-id="80a70-113">경로가 읽기 전용인 경우(<xref:System.IO.IOException>)</span><span class="sxs-lookup"><span data-stu-id="80a70-113">The path is read-only (<xref:System.IO.IOException>).</span></span>  
  
-   <span data-ttu-id="80a70-114">경로 이름이 `Nothing`인 경우(<xref:System.ArgumentNullException>)</span><span class="sxs-lookup"><span data-stu-id="80a70-114">The path name is `Nothing` (<xref:System.ArgumentNullException>).</span></span>  
  
-   <span data-ttu-id="80a70-115">경로 이름이 너무 긴 경우(<xref:System.IO.PathTooLongException>)</span><span class="sxs-lookup"><span data-stu-id="80a70-115">The path name is too long (<xref:System.IO.PathTooLongException>).</span></span>  
  
-   <span data-ttu-id="80a70-116">경로가 잘못된 경우(<xref:System.IO.DirectoryNotFoundException>)</span><span class="sxs-lookup"><span data-stu-id="80a70-116">The path is invalid (<xref:System.IO.DirectoryNotFoundException>).</span></span>  
  
-   <span data-ttu-id="80a70-117">경로가 콜론 ":"뿐인 경우(<xref:System.NotSupportedException>)</span><span class="sxs-lookup"><span data-stu-id="80a70-117">The path is only a colon ":" (<xref:System.NotSupportedException>).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="80a70-118">.NET Framework 보안</span><span class="sxs-lookup"><span data-stu-id="80a70-118">.NET Framework Security</span></span>  
 <span data-ttu-id="80a70-119">부분 신뢰 환경에서는 <xref:System.Security.SecurityException>이 throw될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80a70-119">A <xref:System.Security.SecurityException> may be thrown in partial-trust environments.</span></span>  
  
 <span data-ttu-id="80a70-120"><xref:System.IO.File.Create%2A> 메서드를 호출하려면 <xref:System.Security.Permissions.FileIOPermission>이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="80a70-120">The call to the <xref:System.IO.File.Create%2A> method requires <xref:System.Security.Permissions.FileIOPermission>.</span></span>  
  
 <span data-ttu-id="80a70-121">사용자에게 파일을 만들 수 있는 권한이 없으면 <xref:System.UnauthorizedAccessException>이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="80a70-121">An <xref:System.UnauthorizedAccessException> is thrown if the user does not have permission to create the file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80a70-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="80a70-122">See Also</span></span>  
 <span data-ttu-id="80a70-123"><xref:System.IO></span><span class="sxs-lookup"><span data-stu-id="80a70-123"><xref:System.IO></span></span>   
 <span data-ttu-id="80a70-124"><xref:System.IO.File.Create%2A></span><span class="sxs-lookup"><span data-stu-id="80a70-124"><xref:System.IO.File.Create%2A></span></span>   
 <span data-ttu-id="80a70-125">[부분적으로 신뢰할 수 있는 코드에서 라이브러리 사용](../../../../framework/misc/using-libraries-from-partially-trusted-code.md) </span><span class="sxs-lookup"><span data-stu-id="80a70-125">[Using Libraries from Partially Trusted Code](../../../../framework/misc/using-libraries-from-partially-trusted-code.md) </span></span>  
 [<span data-ttu-id="80a70-126">코드 액세스 보안 기본 사항</span><span class="sxs-lookup"><span data-stu-id="80a70-126">Code Access Security Basics</span></span>](https://msdn.microsoft.com/library/33tceax8)

