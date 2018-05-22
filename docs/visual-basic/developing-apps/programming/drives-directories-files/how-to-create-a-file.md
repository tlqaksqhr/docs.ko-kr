---
title: '방법: Visual Basic에서 파일 만들기'
ms.date: 07/20/2015
helpviewer_keywords:
- text files [Visual Basic], creating
- files [Visual Basic], creating
ms.assetid: 0253bb6d-5519-4a50-b882-b93ef5cca0d9
ms.openlocfilehash: 6167ea0850308eec4b558a47dd881476325a8ea1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-a-file-in-visual-basic"></a><span data-ttu-id="48f2e-102">방법: Visual Basic에서 파일 만들기</span><span class="sxs-lookup"><span data-stu-id="48f2e-102">How to: Create a File in Visual Basic</span></span>
<span data-ttu-id="48f2e-103">이 예제에서는 <xref:System.IO.File> 클래스의 <xref:System.IO.File.Create%2A> 메서드를 사용하여 지정된 경로에 빈 텍스트 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="48f2e-103">This example creates an empty text file at the specified path using the <xref:System.IO.File.Create%2A> method in the <xref:System.IO.File> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="48f2e-104">예</span><span class="sxs-lookup"><span data-stu-id="48f2e-104">Example</span></span>  
 [!code-vb[VbFileIOMisc#1](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-create-a-file_1.vb)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="48f2e-105">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="48f2e-105">Compiling the Code</span></span>  
 <span data-ttu-id="48f2e-106">파일에 쓰려면 `file` 변수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="48f2e-106">Use the `file` variable to write to the file.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="48f2e-107">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="48f2e-107">Robust Programming</span></span>  
 <span data-ttu-id="48f2e-108">파일이 이미 있으면 대체됩니다.</span><span class="sxs-lookup"><span data-stu-id="48f2e-108">If the file already exists, it is replaced.</span></span>  
  
 <span data-ttu-id="48f2e-109">다음 조건에서 예외가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="48f2e-109">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="48f2e-110">경로 이름 형식이 잘못되었습니다.</span><span class="sxs-lookup"><span data-stu-id="48f2e-110">The path name is malformed.</span></span> <span data-ttu-id="48f2e-111">예를 들어 잘못된 문자를 포함하거나 공백만으로 이루어져 있습니다(<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="48f2e-111">For example, it contains illegal characters or is only white space (<xref:System.ArgumentException>).</span></span>  
  
-   <span data-ttu-id="48f2e-112">경로가 읽기 전용인 경우(<xref:System.IO.IOException>)</span><span class="sxs-lookup"><span data-stu-id="48f2e-112">The path is read-only (<xref:System.IO.IOException>).</span></span>  
  
-   <span data-ttu-id="48f2e-113">경로 이름이 `Nothing`인 경우(<xref:System.ArgumentNullException>)</span><span class="sxs-lookup"><span data-stu-id="48f2e-113">The path name is `Nothing` (<xref:System.ArgumentNullException>).</span></span>  
  
-   <span data-ttu-id="48f2e-114">경로 이름이 너무 긴 경우(<xref:System.IO.PathTooLongException>)</span><span class="sxs-lookup"><span data-stu-id="48f2e-114">The path name is too long (<xref:System.IO.PathTooLongException>).</span></span>  
  
-   <span data-ttu-id="48f2e-115">경로가 잘못된 경우(<xref:System.IO.DirectoryNotFoundException>)</span><span class="sxs-lookup"><span data-stu-id="48f2e-115">The path is invalid (<xref:System.IO.DirectoryNotFoundException>).</span></span>  
  
-   <span data-ttu-id="48f2e-116">경로가 콜론 ":"뿐인 경우(<xref:System.NotSupportedException>)</span><span class="sxs-lookup"><span data-stu-id="48f2e-116">The path is only a colon ":" (<xref:System.NotSupportedException>).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="48f2e-117">.NET Framework 보안</span><span class="sxs-lookup"><span data-stu-id="48f2e-117">.NET Framework Security</span></span>  
 <span data-ttu-id="48f2e-118">부분 신뢰 환경에서는 <xref:System.Security.SecurityException>이 throw될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48f2e-118">A <xref:System.Security.SecurityException> may be thrown in partial-trust environments.</span></span>  
  
 <span data-ttu-id="48f2e-119"><xref:System.IO.File.Create%2A> 메서드를 호출하려면 <xref:System.Security.Permissions.FileIOPermission>이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="48f2e-119">The call to the <xref:System.IO.File.Create%2A> method requires <xref:System.Security.Permissions.FileIOPermission>.</span></span>  
  
 <span data-ttu-id="48f2e-120">사용자에게 파일을 만들 수 있는 권한이 없으면 <xref:System.UnauthorizedAccessException>이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="48f2e-120">An <xref:System.UnauthorizedAccessException> is thrown if the user does not have permission to create the file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48f2e-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="48f2e-121">See Also</span></span>  
 <xref:System.IO>  
 <xref:System.IO.File.Create%2A>  
 [<span data-ttu-id="48f2e-122">부분적으로 신뢰할 수 있는 코드에서 라이브러리 사용</span><span class="sxs-lookup"><span data-stu-id="48f2e-122">Using Libraries from Partially Trusted Code</span></span>](../../../../framework/misc/using-libraries-from-partially-trusted-code.md)  
 [<span data-ttu-id="48f2e-123">코드 액세스 보안 기본 사항</span><span class="sxs-lookup"><span data-stu-id="48f2e-123">Code Access Security Basics</span></span>](../../../../framework/misc/code-access-security-basics.md)
