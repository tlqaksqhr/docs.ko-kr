---
title: '방법: 디렉터리 복사'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- directory copying
- I/O [.NET Framework], copying directories
- subdirectory copying
- copying directories
- directories [.NET Framework], copying
ms.assetid: 5a969765-e5f8-4b4e-977e-90e2b0a1fe3c
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1cfe07af216da1c35b093a1ca23e4d48c60a7bfe
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-copy-directories"></a><span data-ttu-id="6d01c-102">방법: 디렉터리 복사</span><span class="sxs-lookup"><span data-stu-id="6d01c-102">How to: Copy Directories</span></span>
<span data-ttu-id="6d01c-103">이 예제에서는 I/O 클래스를 사용하여 디렉터리의 내용을 다른 위치로 동기적으로 복사하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6d01c-103">This example demonstrates how to use I/O classes to synchronously copy the contents of a directory to another location.</span></span> <span data-ttu-id="6d01c-104">이 예제에서는 사용자가 하위 디렉터리도 복사할지 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d01c-104">In this example, the user can specify whether to also copy the subdirectories.</span></span> <span data-ttu-id="6d01c-105">하위 디렉터리를 복사하는 경우 이 예제의 메서드는 더 이상 복사할 항목이 없을 때까지 각 후속 하위 디렉터리에서 자신을 호출하여 재귀적으로 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="6d01c-105">If the subdirectories are copied, the method in this example recursively copies them by calling itself on each subsequent subdirectory until there are no more to copy.</span></span>  
  
 <span data-ttu-id="6d01c-106">비동기적인 파일 복사의 예제는 [Asynchronous File I/O](../../../docs/standard/io/asynchronous-file-i-o.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6d01c-106">For an example of copying files asynchronously, see [Asynchronous File I/O](../../../docs/standard/io/asynchronous-file-i-o.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="6d01c-107">예</span><span class="sxs-lookup"><span data-stu-id="6d01c-107">Example</span></span>  
 [!code-csharp[System.IO.Directory_Copy#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.Directory_Copy/cs/program.cs#1)]
 [!code-vb[System.IO.Directory_Copy#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.Directory_Copy/vb/Program.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="6d01c-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6d01c-108">See Also</span></span>  
 <xref:System.IO.FileInfo>  
 <xref:System.IO.DirectoryInfo>  
 <xref:System.IO.FileStream>  
 [<span data-ttu-id="6d01c-109">파일 및 스트림 I/O</span><span class="sxs-lookup"><span data-stu-id="6d01c-109">File and Stream I/O</span></span>](../../../docs/standard/io/index.md)  
 [<span data-ttu-id="6d01c-110">공통적인 I/O 작업</span><span class="sxs-lookup"><span data-stu-id="6d01c-110">Common I/O Tasks</span></span>](../../../docs/standard/io/common-i-o-tasks.md)  
 [<span data-ttu-id="6d01c-111">비동기 파일 I/O</span><span class="sxs-lookup"><span data-stu-id="6d01c-111">Asynchronous File I/O</span></span>](../../../docs/standard/io/asynchronous-file-i-o.md)
