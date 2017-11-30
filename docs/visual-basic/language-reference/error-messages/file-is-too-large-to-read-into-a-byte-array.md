---
title: "파일이 너무 커서 바이트 배열로 읽어 들일 수 없습니다."
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
ms.assetid: 686630a6-a439-46c7-8d7b-34613ae4c5d8
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2bbdb5a4dcaa22ca84428ef28c8838a6d9a0ee1b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="file-is-too-large-to-read-into-a-byte-array"></a><span data-ttu-id="7c050-102">파일이 너무 커서 바이트 배열로 읽어 들일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7c050-102">File is too large to read into a byte array</span></span>
<span data-ttu-id="7c050-103">바이트 배열로 읽을 하려는 파일의 크기는 4GB를 초과 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c050-103">The size of the file you are attempting to read into a byte array exceeds 4 GB.</span></span> <span data-ttu-id="7c050-104">`My.Computer.FileSystem.ReadAllBytes` 메서드는이 크기를 초과 하는 파일을 읽을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7c050-104">The `My.Computer.FileSystem.ReadAllBytes` method cannot read a file that exceeds this size.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="7c050-105">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="7c050-105">To correct this error</span></span>  
  
-   <span data-ttu-id="7c050-106">사용 하 여 한 <xref:System.IO.StreamReader> 파일을 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c050-106">Use a <xref:System.IO.StreamReader> to read the file.</span></span> <span data-ttu-id="7c050-107">자세한 내용은 참조 [기본 사항의.NET Framework 파일 I/O 및 파일 시스템 (Visual Basic)](../../../visual-basic/developing-apps/programming/drives-directories-files/basics-of-net-framework-file-io-and-the-file-system.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7c050-107">For more information, see [Basics of .NET Framework File I/O and the File System (Visual Basic)](../../../visual-basic/developing-apps/programming/drives-directories-files/basics-of-net-framework-file-io-and-the-file-system.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c050-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7c050-108">See Also</span></span>  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.ReadAllBytes%2A>  
 <xref:System.IO.StreamReader>  
 [<span data-ttu-id="7c050-109">Visual Basic을 사용한 파일 액세스</span><span class="sxs-lookup"><span data-stu-id="7c050-109">File Access with Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/drives-directories-files/file-access.md)  
 [<span data-ttu-id="7c050-110">방법: StreamReader를 사용하여 파일에서 텍스트 읽기</span><span class="sxs-lookup"><span data-stu-id="7c050-110">How to: Read Text from Files with a StreamReader</span></span>](../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-text-from-files-with-a-streamreader.md)
