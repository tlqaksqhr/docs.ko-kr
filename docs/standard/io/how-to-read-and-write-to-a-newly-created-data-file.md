---
title: "방법: 새로 만든 데이터 파일 읽기 및 쓰기"
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
- streams, reading and writing data
- BinaryReader class, examples
- I/O [.NET Framework], reading data
- I/O [.NET Framework], writing data
- BinaryWriter class, examples
ms.assetid: e209d949-31e8-44ea-8e38-87f9093f3093
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 04ded71a23ba4cabab0a22e0d66c1084a726d8c8
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-read-and-write-to-a-newly-created-data-file"></a><span data-ttu-id="9339c-102">방법: 새로 만든 데이터 파일 읽기 및 쓰기</span><span class="sxs-lookup"><span data-stu-id="9339c-102">How to: Read and Write to a Newly Created Data File</span></span>
<span data-ttu-id="9339c-103"><xref:System.IO.BinaryWriter>와 <xref:System.IO.BinaryReader?displayProperty=nameWithType> 클래스는 문자열이 아닌 데이터를 쓰고 읽는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9339c-103">The <xref:System.IO.BinaryWriter> and <xref:System.IO.BinaryReader?displayProperty=nameWithType> classes are used for writing and reading data rather than character strings.</span></span> <span data-ttu-id="9339c-104">다음 예제에서는 `Test.data`라는 새로 만든 빈 파일 스트림에서 데이터를 읽거나 이 스트림에 데이터를 쓰는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9339c-104">The following example demonstrates how to write data to, and read data from, a new, empty file stream called `Test.data`.</span></span> <span data-ttu-id="9339c-105">현재 디렉터리에 데이터 파일을 만든 후 관련된 <xref:System.IO.BinaryWriter> 및 <xref:System.IO.BinaryReader> 개체를 만들고 <xref:System.IO.BinaryWriter> 개체를 사용하여 0부터 10까지의 정수를 `Test.data`에 씁니다. 이렇게 하면 파일 포인터가 파일 끝에 옵니다.</span><span class="sxs-lookup"><span data-stu-id="9339c-105">After creating the data file in the current directory, the associated <xref:System.IO.BinaryWriter> and <xref:System.IO.BinaryReader> objects are created, and the <xref:System.IO.BinaryWriter> object is used to write the integers 0 through 10 to `Test.data`, which leaves the file pointer at the end of the file.</span></span> <span data-ttu-id="9339c-106">파일 포인터를 다시 원점으로 설정하고 나면, <xref:System.IO.BinaryReader> 개체는 지정된 내용을 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="9339c-106">After setting the file pointer back to the origin, the <xref:System.IO.BinaryReader> object reads out the specified content.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9339c-107">예</span><span class="sxs-lookup"><span data-stu-id="9339c-107">Example</span></span>  
 [!code-cpp[System.IO.BinaryReaderWriter#7](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.BinaryReaderWriter/CPP/source6.cpp#7)]
 [!code-csharp[System.IO.BinaryReaderWriter#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.BinaryReaderWriter/CS/source6.cs#7)]
 [!code-vb[System.IO.BinaryReaderWriter#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.BinaryReaderWriter/VB/source6.vb#7)]  
  
## <a name="robust-programming"></a><span data-ttu-id="9339c-108">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="9339c-108">Robust Programming</span></span>  
 <span data-ttu-id="9339c-109">현재 디렉터리에 `Test.data`가 이미 있는 경우, <xref:System.IO.IOException> 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="9339c-109">If `Test.data` already exists in the current directory, an <xref:System.IO.IOException> exception is thrown.</span></span> <span data-ttu-id="9339c-110">파일 스트림을 초기화하여 예외를 throw하지 않고 항상 새 파일을 만들려면 <xref:System.IO.FileMode.Create?displayProperty=nameWithType> 파일 모드 옵션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9339c-110">Use the file mode option <xref:System.IO.FileMode.Create?displayProperty=nameWithType> when you initialize the file stream to always create a new file without throwing an  exception.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9339c-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9339c-111">See Also</span></span>  
 <xref:System.IO.BinaryReader>  
 <xref:System.IO.BinaryWriter>  
 <xref:System.IO.FileStream>  
 <xref:System.IO.FileStream.Seek%2A?displayProperty=nameWithType>  
 <xref:System.IO.SeekOrigin>  
 [<span data-ttu-id="9339c-112">방법: 디렉터리 및 파일 열거</span><span class="sxs-lookup"><span data-stu-id="9339c-112">How to: Enumerate Directories and Files</span></span>](../../../docs/standard/io/how-to-enumerate-directories-and-files.md)  
 [<span data-ttu-id="9339c-113">방법: 로그 파일 열기 및 추가</span><span class="sxs-lookup"><span data-stu-id="9339c-113">How to: Open and Append to a Log File</span></span>](../../../docs/standard/io/how-to-open-and-append-to-a-log-file.md)  
 [<span data-ttu-id="9339c-114">방법: 파일의 텍스트 읽기</span><span class="sxs-lookup"><span data-stu-id="9339c-114">How to: Read Text from a File</span></span>](../../../docs/standard/io/how-to-read-text-from-a-file.md)  
 [<span data-ttu-id="9339c-115">방법: 파일에 텍스트 쓰기</span><span class="sxs-lookup"><span data-stu-id="9339c-115">How to: Write Text to a File</span></span>](../../../docs/standard/io/how-to-write-text-to-a-file.md)  
 [<span data-ttu-id="9339c-116">방법: 문자열에서 문자 읽기</span><span class="sxs-lookup"><span data-stu-id="9339c-116">How to: Read Characters from a String</span></span>](../../../docs/standard/io/how-to-read-characters-from-a-string.md)  
 [<span data-ttu-id="9339c-117">방법: 문자열에 문자 쓰기</span><span class="sxs-lookup"><span data-stu-id="9339c-117">How to: Write Characters to a String</span></span>](../../../docs/standard/io/how-to-write-characters-to-a-string.md)  
 [<span data-ttu-id="9339c-118">파일 및 스트림 I/O</span><span class="sxs-lookup"><span data-stu-id="9339c-118">File and Stream I-O</span></span>](../../../docs/standard/io/index.md)
