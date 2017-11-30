---
title: "스트림 작성"
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
- streams, base streams
- I/O [.NET Framework], composing streams
- Stream class, composing streams
- base streams
- streams, backing stores
ms.assetid: da761658-a535-4f26-a452-b30df47f73d5
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 75800210a52620c5b08a01c5f8fa888bf40843fe
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="composing-streams"></a><span data-ttu-id="96bf7-102">스트림 작성</span><span class="sxs-lookup"><span data-stu-id="96bf7-102">Composing Streams</span></span>
<span data-ttu-id="96bf7-103">백업 저장소는 디스크 또는 메모리와 같은 저장소 미디어입니다.</span><span class="sxs-lookup"><span data-stu-id="96bf7-103">A backing store is a storage medium, such as a disk or memory.</span></span> <span data-ttu-id="96bf7-104">각각의 백업 저장소의 구현으로 자체 스트림을 구현는 <xref:System.IO.Stream> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="96bf7-104">Each different backing store implements its own stream as an implementation of the <xref:System.IO.Stream> class.</span></span> <span data-ttu-id="96bf7-105">각 스트림 형식을 읽고과 지정 된 백업 저장소 바이트를 씁니다.</span><span class="sxs-lookup"><span data-stu-id="96bf7-105">Each stream type reads and writes bytes from and to its given backing store.</span></span> <span data-ttu-id="96bf7-106">백업 저장소에 연결 하는 스트림의 기본 스트림 라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="96bf7-106">Streams that connect to backing stores are called base streams.</span></span> <span data-ttu-id="96bf7-107">기본 스트림 백업 저장소에 스트림을 연결 하는 데 필요한 매개 변수가 있는 생성자가 있는 합니다.</span><span class="sxs-lookup"><span data-stu-id="96bf7-107">Base streams have constructors that have the parameters necessary to connect the stream to the backing store.</span></span> <span data-ttu-id="96bf7-108">예를 들어 <xref:System.IO.FileStream> 프로세스, 및 등의 파일을 공유 하는 방법을 지정 하는 경로 매개 변수를 지정 하는 생성자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96bf7-108">For example, <xref:System.IO.FileStream> has constructors that specify a path parameter, which specifies how the file will be shared by processes, and so on.</span></span>  
  
 <span data-ttu-id="96bf7-109">디자인은 <xref:System.IO> 간소화 된 스트림을 작성할 클래스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="96bf7-109">The design of the <xref:System.IO> classes provides simplified stream composing.</span></span> <span data-ttu-id="96bf7-110">기본 스트림 원하는 기능을 제공 하는 통과 스트림을 하나 이상 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96bf7-110">Base streams can be attached to one or more pass-through streams that provide the functionality you want.</span></span> <span data-ttu-id="96bf7-111">판독기 또는 작성기 기본 유형 읽거나 쉽게 쓸 수 있도록 체인의 끝에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96bf7-111">A reader or writer can be attached to the end of the chain so that the preferred types can be read or written easily.</span></span>  
  
 <span data-ttu-id="96bf7-112">다음 코드 예제에서는 한 **FileStream** 기존 주위 `MyFile.txt` 버퍼로 순서로 `MyFile.txt`합니다.</span><span class="sxs-lookup"><span data-stu-id="96bf7-112">The following code example creates a **FileStream** around the existing `MyFile.txt` in order to buffer `MyFile.txt`.</span></span> <span data-ttu-id="96bf7-113">(유의 **FileStreams** 기본적으로 버퍼링 됩니다.) 다음으로 <xref:System.IO.StreamReader> 에서 문자를 읽으려면 만들어집니다는 **FileStream**로 전달 되는 **StreamReader** 생성자 인수로 합니다.</span><span class="sxs-lookup"><span data-stu-id="96bf7-113">(Note that **FileStreams** are buffered by default.) Next, a <xref:System.IO.StreamReader> is created to read characters from the **FileStream**, which is passed to the **StreamReader** as its constructor argument.</span></span> <span data-ttu-id="96bf7-114"><xref:System.IO.StreamReader.ReadLine%2A>될 때까지 읽습니다 <xref:System.IO.StreamReader.Peek%2A> 문자가 더 이상 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="96bf7-114"><xref:System.IO.StreamReader.ReadLine%2A> reads until <xref:System.IO.StreamReader.Peek%2A> finds no more characters.</span></span>  
  
 [!code-cpp[System.IO.StreamReader#20](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.StreamReader/CPP/source2.cpp#20)]
 [!code-csharp[System.IO.StreamReader#20](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.StreamReader/CS/source2.cs#20)]
 [!code-vb[System.IO.StreamReader#20](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.StreamReader/VB/source2.vb#20)]  
  
 <span data-ttu-id="96bf7-115">다음 코드 예제에서는 한 **FileStream** 기존 주위 `MyFile.txt` 버퍼로 순서로 `MyFile.txt`합니다.</span><span class="sxs-lookup"><span data-stu-id="96bf7-115">The following code example creates a **FileStream** around the existing `MyFile.txt` in order to buffer `MyFile.txt`.</span></span> <span data-ttu-id="96bf7-116">(유의 **FileStreams** 기본적으로 버퍼링 됩니다.) 다음으로 **BinaryReader** 에서 바이트를 읽으려고 만들어집니다는 **FileStream**로 전달 되는 **BinaryReader** 생성자 인수로 합니다.</span><span class="sxs-lookup"><span data-stu-id="96bf7-116">(Note that **FileStreams** are buffered by default.) Next, a **BinaryReader** is created to read bytes from the **FileStream**, which is passed to the **BinaryReader** as its constructor argument.</span></span> <span data-ttu-id="96bf7-117"><xref:System.IO.BinaryReader.ReadByte%2A>될 때까지 읽습니다 <xref:System.IO.BinaryReader.PeekChar%2A> 추가 바이트를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="96bf7-117"><xref:System.IO.BinaryReader.ReadByte%2A> reads until <xref:System.IO.BinaryReader.PeekChar%2A> finds no more bytes.</span></span>  
  
 [!code-cpp[System.IO.StreamReader#21](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.StreamReader/CPP/source3.cpp#21)]
 [!code-csharp[System.IO.StreamReader#21](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.StreamReader/CS/source3.cs#21)]
 [!code-vb[System.IO.StreamReader#21](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.StreamReader/VB/source3.vb#21)]  
  
## <a name="see-also"></a><span data-ttu-id="96bf7-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="96bf7-118">See Also</span></span>  
 <xref:System.IO.StreamReader>  
 <xref:System.IO.StreamReader.ReadLine%2A?displayProperty=nameWithType>  
 <xref:System.IO.StreamReader.Peek%2A?displayProperty=nameWithType>  
 <xref:System.IO.FileStream>  
 <xref:System.IO.BinaryReader>  
 <xref:System.IO.BinaryReader.ReadByte%2A?displayProperty=nameWithType>  
 <xref:System.IO.BinaryReader.PeekChar%2A?displayProperty=nameWithType>
