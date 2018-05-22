---
title: 스트림 작성
ms.date: 03/30/2017
ms.technology: dotnet-standard
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 231bd98b556dafeb69091de4a6770c1462824659
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="composing-streams"></a><span data-ttu-id="77755-102">스트림 작성</span><span class="sxs-lookup"><span data-stu-id="77755-102">Composing Streams</span></span>
<span data-ttu-id="77755-103">백업 저장소는 디스크 또는 메모리와 같은 저장 매체입니다.</span><span class="sxs-lookup"><span data-stu-id="77755-103">A backing store is a storage medium, such as a disk or memory.</span></span> <span data-ttu-id="77755-104">다양한 각 백업 저장소는 <xref:System.IO.Stream> 클래스의 구현으로 고유한 스트림을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="77755-104">Each different backing store implements its own stream as an implementation of the <xref:System.IO.Stream> class.</span></span> <span data-ttu-id="77755-105">각 스트림 유형은 지정된 백업 저장소에 유입 또는 유출되는 바이트를 읽고 씁니다.</span><span class="sxs-lookup"><span data-stu-id="77755-105">Each stream type reads and writes bytes from and to its given backing store.</span></span> <span data-ttu-id="77755-106">백업 저장소에 연결되는 스트림을 기본 스트림이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="77755-106">Streams that connect to backing stores are called base streams.</span></span> <span data-ttu-id="77755-107">기본 스트림에는 스트림을 백업 저장소에 연결하는 데 필요한 매개 변수가 있는 생성자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77755-107">Base streams have constructors that have the parameters necessary to connect the stream to the backing store.</span></span> <span data-ttu-id="77755-108">예를 들어 <xref:System.IO.FileStream>에는 프로세스가 경로 매개 변수를 지정하는 생성자가 있습니다. 경로 매개 변수는 파일을 공유할 방식 등을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="77755-108">For example, <xref:System.IO.FileStream> has constructors that specify a path parameter, which specifies how the file will be shared by processes, and so on.</span></span>  
  
 <span data-ttu-id="77755-109"><xref:System.IO> 클래스의 디자인은 간소화된 스트림 작성을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="77755-109">The design of the <xref:System.IO> classes provides simplified stream composing.</span></span> <span data-ttu-id="77755-110">원하는 기능을 제공하는 하나 이상의 통과 스트림에 기본 스트림을 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77755-110">Base streams can be attached to one or more pass-through streams that provide the functionality you want.</span></span> <span data-ttu-id="77755-111">기본 설정 유형을 쉽게 읽거나 쓸 수 있도록 체인 끝에 reader 또는 writer를 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77755-111">A reader or writer can be attached to the end of the chain so that the preferred types can be read or written easily.</span></span>  
  
 <span data-ttu-id="77755-112">다음 코드 예제에서는 `MyFile.txt`를 버퍼링하기 위해 기존의 `MyFile.txt`를 바탕으로 **FileStream**을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="77755-112">The following code example creates a **FileStream** around the existing `MyFile.txt` in order to buffer `MyFile.txt`.</span></span> <span data-ttu-id="77755-113">(기본적으로 **FileStream**은 버퍼링됩니다.) 다음으로, **StreamReader**에 해당 생성자 인수로 전달되는 **FileStream**에서 문자를 읽도록 <xref:System.IO.StreamReader>를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="77755-113">(Note that **FileStreams** are buffered by default.) Next, a <xref:System.IO.StreamReader> is created to read characters from the **FileStream**, which is passed to the **StreamReader** as its constructor argument.</span></span> <span data-ttu-id="77755-114"><xref:System.IO.StreamReader.ReadLine%2A>은 <xref:System.IO.StreamReader.Peek%2A>가 더 이상 문자를 찾지 못할 때까지 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="77755-114"><xref:System.IO.StreamReader.ReadLine%2A> reads until <xref:System.IO.StreamReader.Peek%2A> finds no more characters.</span></span>  
  
 [!code-cpp[System.IO.StreamReader#20](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.StreamReader/CPP/source2.cpp#20)]
 [!code-csharp[System.IO.StreamReader#20](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.StreamReader/CS/source2.cs#20)]
 [!code-vb[System.IO.StreamReader#20](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.StreamReader/VB/source2.vb#20)]  
  
 <span data-ttu-id="77755-115">다음 코드 예제에서는 `MyFile.txt`를 버퍼링하기 위해 기존의 `MyFile.txt`를 바탕으로 **FileStream**을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="77755-115">The following code example creates a **FileStream** around the existing `MyFile.txt` in order to buffer `MyFile.txt`.</span></span> <span data-ttu-id="77755-116">(기본적으로 **FileStream**은 버퍼링됩니다.) 다음으로, **BinaryReader**에 해당 생성자 인수로 전달되는 **FileStream**에서 바이트를 읽도록 **BinaryReader**를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="77755-116">(Note that **FileStreams** are buffered by default.) Next, a **BinaryReader** is created to read bytes from the **FileStream**, which is passed to the **BinaryReader** as its constructor argument.</span></span> <span data-ttu-id="77755-117"><xref:System.IO.BinaryReader.ReadByte%2A>는 <xref:System.IO.BinaryReader.PeekChar%2A>이 더 이상 바이트를 찾지 못할 때까지 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="77755-117"><xref:System.IO.BinaryReader.ReadByte%2A> reads until <xref:System.IO.BinaryReader.PeekChar%2A> finds no more bytes.</span></span>  
  
 [!code-cpp[System.IO.StreamReader#21](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.StreamReader/CPP/source3.cpp#21)]
 [!code-csharp[System.IO.StreamReader#21](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.StreamReader/CS/source3.cs#21)]
 [!code-vb[System.IO.StreamReader#21](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.StreamReader/VB/source3.vb#21)]  
  
## <a name="see-also"></a><span data-ttu-id="77755-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="77755-118">See Also</span></span>  
 <xref:System.IO.StreamReader>  
 <xref:System.IO.StreamReader.ReadLine%2A?displayProperty=nameWithType>  
 <xref:System.IO.StreamReader.Peek%2A?displayProperty=nameWithType>  
 <xref:System.IO.FileStream>  
 <xref:System.IO.BinaryReader>  
 <xref:System.IO.BinaryReader.ReadByte%2A?displayProperty=nameWithType>  
 <xref:System.IO.BinaryReader.PeekChar%2A?displayProperty=nameWithType>
