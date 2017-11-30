---
title: "방법: 문자열에서 문자 읽기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- reading characters from strings
- data streams, reading characters from string
- I/O [.NET Framework], reading characters from strings
- reading data, strings
- streams, reading characters from string
ms.assetid: 27ea5e52-6db8-42d8-980a-50bcfc7fd270
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 9116ec63bfc1d12daf7627186a52bd29d5918485
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-read-characters-from-a-string"></a><span data-ttu-id="d8b71-102">방법: 문자열에서 문자 읽기</span><span class="sxs-lookup"><span data-stu-id="d8b71-102">How to: Read Characters from a String</span></span>
<span data-ttu-id="d8b71-103">다음 코드 예제에서는 문자열에서 문자를 동기적 및 비동기적으로 읽고 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d8b71-103">The following code examples show how to read characters synchronously and asynchronously from a string.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d8b71-104">예제</span><span class="sxs-lookup"><span data-stu-id="d8b71-104">Example</span></span>  
 <span data-ttu-id="d8b71-105">이 예제에서는 문자열에서 동기적으로 13 자로 배열에 저장 하 고 해당 문자를 표시를 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="d8b71-105">This example reads 13 characters synchronously from a string, stores them in an array, and displays those characters.</span></span> <span data-ttu-id="d8b71-106">문자열의 나머지 문자를 읽고, 여섯 번째 요소부터 시작 하 여 배열에 저장 하 고 배열 콘텐츠가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8b71-106">It then reads the remaining characters in the string, stores them in the array starting at the sixth element, and displays the contents of the array.</span></span>  
  
 [!code-cpp[Conceptual.StringReader#1](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.stringreader/cpp/source.cpp#1)]
 [!code-csharp[Conceptual.StringReader#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.stringreader/cs/source.cs#1)]
 [!code-vb[Conceptual.StringReader#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.stringreader/vb/source.vb#1)]  
  
## <a name="example"></a><span data-ttu-id="d8b71-107">예제</span><span class="sxs-lookup"><span data-stu-id="d8b71-107">Example</span></span>  
 <span data-ttu-id="d8b71-108">다음 예제는 <xref:System.Windows.Controls.TextBox> 컨트롤에서 모든 문자를 비동기적으로 읽고 배열에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="d8b71-108">The next example reads all the characters asynchronously from a <xref:System.Windows.Controls.TextBox> control, and stores them in an array.</span></span> <span data-ttu-id="d8b71-109">그런 다음 별도의 줄에 각 문자 또는 공백 문자를 비동기적으로 쓰고 이어서 <xref:System.Windows.Controls.TextBlock> 컨트롤에 대한 줄 바꿈이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="d8b71-109">It then asynchronously writes each letter or white space character on a separate line followed by a line break to a <xref:System.Windows.Controls.TextBlock> control.</span></span>  
  
 [!code-csharp[Conceptual.StringReader#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.stringreader/cs/source2.cs#2)]
 [!code-vb[Conceptual.StringReader#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.stringreader/vb/source2.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="d8b71-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d8b71-110">See Also</span></span>  
 <xref:System.IO.StringReader>  
 <xref:System.IO.StringReader.Read%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="d8b71-111">비동기 파일 I/O</span><span class="sxs-lookup"><span data-stu-id="d8b71-111">Asynchronous File I/O</span></span>](../../../docs/standard/io/asynchronous-file-i-o.md)  
 [<span data-ttu-id="d8b71-112">NIB: 방법: 디렉터리 목록 만들기</span><span class="sxs-lookup"><span data-stu-id="d8b71-112">NIB: How to: Create a Directory Listing</span></span>](http://msdn.microsoft.com/en-us/4d2772b1-b991-4532-a8a6-6ef733277e69)  
 [<span data-ttu-id="d8b71-113">방법: 새로 만든 데이터 파일 읽기 및 쓰기</span><span class="sxs-lookup"><span data-stu-id="d8b71-113">How to: Read and Write to a Newly Created Data File</span></span>](../../../docs/standard/io/how-to-read-and-write-to-a-newly-created-data-file.md)  
 [<span data-ttu-id="d8b71-114">방법: 로그 파일 열기 및 추가</span><span class="sxs-lookup"><span data-stu-id="d8b71-114">How to: Open and Append to a Log File</span></span>](../../../docs/standard/io/how-to-open-and-append-to-a-log-file.md)  
 [<span data-ttu-id="d8b71-115">방법: 파일의 텍스트 읽기</span><span class="sxs-lookup"><span data-stu-id="d8b71-115">How to: Read Text from a File</span></span>](../../../docs/standard/io/how-to-read-text-from-a-file.md)  
 [<span data-ttu-id="d8b71-116">방법: 파일에 텍스트 쓰기</span><span class="sxs-lookup"><span data-stu-id="d8b71-116">How to: Write Text to a File</span></span>](../../../docs/standard/io/how-to-write-text-to-a-file.md)  
 [<span data-ttu-id="d8b71-117">방법: 문자열에 문자 쓰기</span><span class="sxs-lookup"><span data-stu-id="d8b71-117">How to: Write Characters to a String</span></span>](../../../docs/standard/io/how-to-write-characters-to-a-string.md)  
 [<span data-ttu-id="d8b71-118">파일 및 스트림 I/O</span><span class="sxs-lookup"><span data-stu-id="d8b71-118">File and Stream I-O</span></span>](../../../docs/standard/io/index.md)
