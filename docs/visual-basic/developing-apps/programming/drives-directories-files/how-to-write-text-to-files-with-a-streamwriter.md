---
title: "방법: Visual Basic에서 StreamWriter를 사용하여 파일에 텍스트 쓰기"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- files [Visual Basic], writing to
- text, writing to files
- writing to files [Visual Basic], StreamWriter
ms.assetid: 99762e57-ef46-4dcc-8959-a8f79c22f067
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 874bb9cb88bbf25cb6208a0a33858855a7b26a49
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-write-text-to-files-with-a-streamwriter-in-visual-basic"></a><span data-ttu-id="ae9c6-102">방법: Visual Basic에서 StreamWriter를 사용하여 파일에 텍스트 쓰기</span><span class="sxs-lookup"><span data-stu-id="ae9c6-102">How to: Write Text to Files with a StreamWriter in Visual Basic</span></span>
<span data-ttu-id="ae9c6-103">이 예제에서는 `My.Computer.FileSystem.OpenTextFileWriter` 메서드를 사용하여 <xref:System.IO.StreamWriter> 개체를 열고 이 개체를 사용하여 <xref:System.IO.StreamWriter> 클래스의 <xref:System.IO.TextWriter.WriteLine%2A> 메서드로 텍스트 파일에 문자열을 씁니다.</span><span class="sxs-lookup"><span data-stu-id="ae9c6-103">This example opens a <xref:System.IO.StreamWriter> object with the `My.Computer.FileSystem.OpenTextFileWriter` method and uses it to write a string to a text file with the <xref:System.IO.TextWriter.WriteLine%2A> method of the <xref:System.IO.StreamWriter> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ae9c6-104">예제</span><span class="sxs-lookup"><span data-stu-id="ae9c6-104">Example</span></span>  
 [!code-vb[VbFileIOWrite#5](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-write-text-to-files-with-a-streamwriter_1.vb)]  
  
## <a name="robust-programming"></a><span data-ttu-id="ae9c6-105">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="ae9c6-105">Robust Programming</span></span>  
 <span data-ttu-id="ae9c6-106">다음 조건에서 예외가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="ae9c6-106">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="ae9c6-107">파일이 있지만 읽기 전용인 경우(<xref:System.IO.IOException>)</span><span class="sxs-lookup"><span data-stu-id="ae9c6-107">The file exists and is read-only (<xref:System.IO.IOException>).</span></span>  
  
-   <span data-ttu-id="ae9c6-108">디스크가 꽉 찬 경우(<xref:System.IO.IOException>)</span><span class="sxs-lookup"><span data-stu-id="ae9c6-108">The disk is full (<xref:System.IO.IOException>).</span></span>  
  
-   <span data-ttu-id="ae9c6-109">경로 이름이 너무 긴 경우(<xref:System.IO.PathTooLongException>)</span><span class="sxs-lookup"><span data-stu-id="ae9c6-109">The pathname is too long (<xref:System.IO.PathTooLongException>).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="ae9c6-110">.NET Framework 보안</span><span class="sxs-lookup"><span data-stu-id="ae9c6-110">.NET Framework Security</span></span>  
 <span data-ttu-id="ae9c6-111">이 예제에서는 파일이 아직 없는 경우 새 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ae9c6-111">This example creates a new file, if the file does not already exist.</span></span> <span data-ttu-id="ae9c6-112">응용 프로그램에서 파일을 만들어야 하는 경우 해당 응용 프로그램에 폴더에 대한 `Create` 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae9c6-112">If an application needs to create a file, that application needs `Create` access for the folder.</span></span> <span data-ttu-id="ae9c6-113">파일이 이미 있는 경우 응용 프로그램에 더 낮은 권한인 `Write` 권한만 있으면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae9c6-113">If the file already exists, the application needs only `Write` access, a lesser privilege.</span></span> <span data-ttu-id="ae9c6-114">가능한 경우 배포하는 동안 파일을 만들고, 폴더에 대한 `Create` 권한 대신 단일 파일에 대해 `Read` 권한만 부여하는 것이 더 안전합니다.</span><span class="sxs-lookup"><span data-stu-id="ae9c6-114">Where possible, it is more secure to create the file during deployment, and only grant `Read` access to a single file, rather than `Create` access for a folder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae9c6-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ae9c6-115">See Also</span></span>  
 <xref:System.IO.StreamWriter>  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.OpenTextFileWriter%2A>  
 [<span data-ttu-id="ae9c6-116">방법: 텍스트 파일에서 읽기</span><span class="sxs-lookup"><span data-stu-id="ae9c6-116">How to: Read from Text Files</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-text-files.md)  
 [<span data-ttu-id="ae9c6-117">파일에 쓰기</span><span class="sxs-lookup"><span data-stu-id="ae9c6-117">Writing to Files</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/writing-to-files.md)
