---
title: '방법: 파일의 텍스트 읽기'
ms.date: 06/19/2018
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- streams, reading text from files
- reading text files
- reading data, text files
- data streams, reading text from files
- I/O [.NET Framework], reading text from files
ms.assetid: ed180baa-dfc6-4c69-a725-46e87edafb27
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b7c54e5e55770f3df44819cdf6d2d2c866f7e0fc
ms.sourcegitcommit: 640cee8fc5d256cdd80e5b80240469feac10499e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/21/2018
ms.locfileid: "36298164"
---
# <a name="how-to-read-text-from-a-file"></a><span data-ttu-id="0b6fe-102">방법: 파일의 텍스트 읽기</span><span class="sxs-lookup"><span data-stu-id="0b6fe-102">How to: Read Text from a File</span></span>
<span data-ttu-id="0b6fe-103">다음 예제에서는 데스크톱 응용 프로그램용 .NET을 사용하여 텍스트 파일에서 텍스트를 동기 또는 비동기적으로 읽는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0b6fe-103">The following examples show how to read text synchronously and asynchronously from a text file using .NET for desktop apps.</span></span> <span data-ttu-id="0b6fe-104">두 예제에서는 <xref:System.IO.StreamReader> 클래스의 인스턴스를 만들 때 파일의 상대 또는 절대 경로를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0b6fe-104">In both examples, when you create the instance of the <xref:System.IO.StreamReader> class, you provide the relative or absolute path to the file.</span></span> <span data-ttu-id="0b6fe-105">다음 예제에서는 TestFile.txt라는 파일이 응용 프로그램과 같은 폴더에 있다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="0b6fe-105">The following examples assume that the file named TestFile.txt is in the same folder as the application.</span></span>  
  
 <span data-ttu-id="0b6fe-106">Windows 런타임에서는 파일을 읽고 파일에 쓰는 다양한 스트림 형식을 제공하기 때문에 이러한 코드 예제는 Windows Store 앱 개발에는 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0b6fe-106">These code examples do not apply to developing for Windows Store Apps because the Windows Runtime provides different stream types for reading and writing to files.</span></span> <span data-ttu-id="0b6fe-107">Windows Store 앱에서 파일의 텍스트를 읽는 방법을 보여 주는 예제는 [Quickstart: Reading and writing files](https://docs.microsoft.com/en-us/previous-versions/windows/apps/hh758325(v=win.10))(빠른 시작: 파일 읽기 및 쓰기)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0b6fe-107">For an example that shows how to read text from a file in a Windows Store app, see [Quickstart: Reading and writing files](https://docs.microsoft.com/en-us/previous-versions/windows/apps/hh758325(v=win.10)).</span></span> <span data-ttu-id="0b6fe-108">.NET Framework 스트림과 Windows 런타임 스트림 간에 변환하는 방법의 예제는 [방법: .NET Framework 스트림과 Windows 런타임 스트림 간 변환](../../../docs/standard/io/how-to-convert-between-dotnet-streams-and-winrt-streams.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0b6fe-108">For examples that show how to convert between .NET Framework streams and Windows runtime streams, see [How to: Convert Between .NET Framework Streams and Windows Runtime Streams](../../../docs/standard/io/how-to-convert-between-dotnet-streams-and-winrt-streams.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0b6fe-109">예</span><span class="sxs-lookup"><span data-stu-id="0b6fe-109">Example</span></span>  
 <span data-ttu-id="0b6fe-110">다음 예제에서는 콘솔 응용 프로그램 내에서 동기적 읽기 작업을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0b6fe-110">The following example shows a synchronous read operation within a console application.</span></span> <span data-ttu-id="0b6fe-111">이 예제에서는 스트림 판독기를 사용하여 텍스트 파일을 열면 내용이 문자열로 복사되고 해당 문자열이 콘솔에 출력됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b6fe-111">In this example, the text file is opened using a stream reader, the contents are copied to a string, and the string is output to the console.</span></span>  
  
 [!code-csharp[Conceptual.BasicIO.TextFiles#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/source3.cs#3)]
 [!code-vb[Conceptual.BasicIO.TextFiles#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/source3.vb#3)]  
  
## <a name="example"></a><span data-ttu-id="0b6fe-112">예</span><span class="sxs-lookup"><span data-stu-id="0b6fe-112">Example</span></span>  
 <span data-ttu-id="0b6fe-113">다음 예제에서는 WPF(Windows Presentation Foundation) 응용 프로그램에서의 비동기 읽기 작업을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0b6fe-113">The following example shows an asynchronous read operation in a Windows Presentation Foundation (WPF) application.</span></span>  
  
 [!code-csharp[Conceptual.BasicIO.TextFiles#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/source6.cs#6)]
 [!code-vb[Conceptual.BasicIO.TextFiles#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/source6.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="0b6fe-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0b6fe-114">See Also</span></span>  
 <xref:System.IO.StreamReader>  
 <xref:System.IO.File.OpenText%2A?displayProperty=nameWithType>  
 <xref:System.IO.StreamReader.ReadLine%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="0b6fe-115">비동기 파일 I/O</span><span class="sxs-lookup"><span data-stu-id="0b6fe-115">Asynchronous File I/O</span></span>](../../../docs/standard/io/asynchronous-file-i-o.md)  
 [<span data-ttu-id="0b6fe-116">NIB: 방법: 디렉터리 목록 생성 만들기</span><span class="sxs-lookup"><span data-stu-id="0b6fe-116">NIB: How to: Create a Directory Listing</span></span>](https://msdn.microsoft.com/library/4d2772b1-b991-4532-a8a6-6ef733277e69)  
 <span data-ttu-id="0b6fe-117">[Quickstart: Reading and writing files](http://msdn.microsoft.com/library/windows/apps/hh758325.aspx)(빠른 시작: 파일 읽기 및 쓰기)</span><span class="sxs-lookup"><span data-stu-id="0b6fe-117">[Quickstart: Reading and writing files](http://msdn.microsoft.com/library/windows/apps/hh758325.aspx)</span></span>  
 [<span data-ttu-id="0b6fe-118">방법: .NET Framework 스트림과 Windows 런타임 스트림 간 변환</span><span class="sxs-lookup"><span data-stu-id="0b6fe-118">How to: Convert Between .NET Framework Streams and Windows Runtime Streams</span></span>](../../../docs/standard/io/how-to-convert-between-dotnet-streams-and-winrt-streams.md)  
 [<span data-ttu-id="0b6fe-119">방법: 새로 만든 데이터 파일 읽기 및 쓰기</span><span class="sxs-lookup"><span data-stu-id="0b6fe-119">How to: Read and Write to a Newly Created Data File</span></span>](../../../docs/standard/io/how-to-read-and-write-to-a-newly-created-data-file.md)  
 [<span data-ttu-id="0b6fe-120">방법: 로그 파일 열기 및 추가</span><span class="sxs-lookup"><span data-stu-id="0b6fe-120">How to: Open and Append to a Log File</span></span>](../../../docs/standard/io/how-to-open-and-append-to-a-log-file.md)  
 [<span data-ttu-id="0b6fe-121">방법: 파일에 텍스트 쓰기</span><span class="sxs-lookup"><span data-stu-id="0b6fe-121">How to: Write Text to a File</span></span>](../../../docs/standard/io/how-to-write-text-to-a-file.md)  
 [<span data-ttu-id="0b6fe-122">방법: 문자열에서 문자 읽기</span><span class="sxs-lookup"><span data-stu-id="0b6fe-122">How to: Read Characters from a String</span></span>](../../../docs/standard/io/how-to-read-characters-from-a-string.md)  
 [<span data-ttu-id="0b6fe-123">방법: 문자열에 문자 쓰기</span><span class="sxs-lookup"><span data-stu-id="0b6fe-123">How to: Write Characters to a String</span></span>](../../../docs/standard/io/how-to-write-characters-to-a-string.md)  
 [<span data-ttu-id="0b6fe-124">파일 및 스트림 I/O</span><span class="sxs-lookup"><span data-stu-id="0b6fe-124">File and Stream I/O</span></span>](../../../docs/standard/io/index.md)
