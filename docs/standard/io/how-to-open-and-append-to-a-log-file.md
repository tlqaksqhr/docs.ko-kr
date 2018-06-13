---
title: '방법: 로그 파일 열기 및 추가'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- log files, opening
- streams, opening and appending to log file
- log files, appending to
- I/O [.NET Framework], log files
ms.assetid: 74423362-1721-49cb-aa0a-e04005f72a06
author: mairaw
ms.author: mairaw
ms.openlocfilehash: cd2d13a49d9b696541ac278b9f1847c8e4a48cf1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33571945"
---
# <a name="how-to-open-and-append-to-a-log-file"></a><span data-ttu-id="4c081-102">방법: 로그 파일 열기 및 추가</span><span class="sxs-lookup"><span data-stu-id="4c081-102">How to: Open and Append to a Log File</span></span>
<span data-ttu-id="4c081-103"><xref:System.IO.StreamWriter> 및 <xref:System.IO.StreamReader>는 스트림에서 문자를 쓰고 문자를 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="4c081-103"><xref:System.IO.StreamWriter> and <xref:System.IO.StreamReader> write characters to and read characters from streams.</span></span> <span data-ttu-id="4c081-104">다음 코드 예제는 입력을 위해 `log.txt` 파일을 열거나, 파일이 존재하지 않는 경우 파일을 만들고 파일의 끝에 정보를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="4c081-104">The following code example opens the `log.txt` file for input, or creates the file if it does not already exist, and appends information to the end of the file.</span></span> <span data-ttu-id="4c081-105">그러면 파일의 콘텐츠가 디스플레이의 표준 출력에 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c081-105">The contents of the file are then written to standard output for display.</span></span> <span data-ttu-id="4c081-106">이 예제의 대안으로, 정보를 단일 문자열 또는 문자열 배열로 저장할 수 있으며, <xref:System.IO.File.WriteAllText%2A> 또는 <xref:System.IO.File.WriteAllLines%2A> 메서드를 동일한 기능을 수행하는 데 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c081-106">As an alternative to this example, the information could be stored as a single string or string array, and the <xref:System.IO.File.WriteAllText%2A> or <xref:System.IO.File.WriteAllLines%2A> method could be used to achieve the same functionality.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4c081-107">Visual Basic 사용자는 로그 파일을 생성하거나 로그 파일에 쓰기 위해 <xref:Microsoft.VisualBasic.Logging.Log> 클래스 또는 <xref:Microsoft.VisualBasic.FileIO.FileSystem> 클래스에서 제공하는 메서드 및 속성을 사용하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c081-107">Visual Basic users may choose to use the methods and properties provided by the <xref:Microsoft.VisualBasic.Logging.Log> class or <xref:Microsoft.VisualBasic.FileIO.FileSystem> class for creating or writing to log files.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4c081-108">예</span><span class="sxs-lookup"><span data-stu-id="4c081-108">Example</span></span>  
 [!code-csharp[Conceptual.BasicIO.TextFiles#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/source2.cs#2)]
 [!code-vb[Conceptual.BasicIO.TextFiles#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/source2.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="4c081-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4c081-109">See Also</span></span>  
 <xref:System.IO.StreamWriter>  
 <xref:System.IO.StreamReader>  
 <xref:System.IO.File.AppendText%2A?displayProperty=nameWithType>  
 <xref:System.IO.File.OpenText%2A?displayProperty=nameWithType>  
 <xref:System.IO.StreamReader.ReadLine%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="4c081-110">방법: 디렉터리 및 파일 열거</span><span class="sxs-lookup"><span data-stu-id="4c081-110">How to: Enumerate Directories and Files</span></span>](../../../docs/standard/io/how-to-enumerate-directories-and-files.md)  
 [<span data-ttu-id="4c081-111">방법: 새로 만든 데이터 파일 읽기 및 쓰기</span><span class="sxs-lookup"><span data-stu-id="4c081-111">How to: Read and Write to a Newly Created Data File</span></span>](../../../docs/standard/io/how-to-read-and-write-to-a-newly-created-data-file.md)  
 [<span data-ttu-id="4c081-112">방법: 파일의 텍스트 읽기</span><span class="sxs-lookup"><span data-stu-id="4c081-112">How to: Read Text from a File</span></span>](../../../docs/standard/io/how-to-read-text-from-a-file.md)  
 [<span data-ttu-id="4c081-113">방법: 파일에 텍스트 쓰기</span><span class="sxs-lookup"><span data-stu-id="4c081-113">How to: Write Text to a File</span></span>](../../../docs/standard/io/how-to-write-text-to-a-file.md)  
 [<span data-ttu-id="4c081-114">방법: 문자열에서 문자 읽기</span><span class="sxs-lookup"><span data-stu-id="4c081-114">How to: Read Characters from a String</span></span>](../../../docs/standard/io/how-to-read-characters-from-a-string.md)  
 [<span data-ttu-id="4c081-115">방법: 문자열에 문자 쓰기</span><span class="sxs-lookup"><span data-stu-id="4c081-115">How to: Write Characters to a String</span></span>](../../../docs/standard/io/how-to-write-characters-to-a-string.md)  
 [<span data-ttu-id="4c081-116">파일 및 스트림 I/O</span><span class="sxs-lookup"><span data-stu-id="4c081-116">File and Stream I/O</span></span>](../../../docs/standard/io/index.md)
