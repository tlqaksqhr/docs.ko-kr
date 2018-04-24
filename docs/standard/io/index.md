---
title: 파일 및 스트림 I/O
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IO namespace
- files, I/O
- System.IO namespace
- I/O [.NET Framework]
- streams, I/O
- data streams, I/O
ms.assetid: 4f4a33a9-66b7-4cd7-a285-4ad3e4276cd2
caps.latest.revision: 33
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: b420859380d7c3c39a7d85f94df1708d9f26bebc
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2018
---
# <a name="file-and-stream-io"></a><span data-ttu-id="61250-102">파일 및 스트림 I/O</span><span class="sxs-lookup"><span data-stu-id="61250-102">File and Stream I/O</span></span>
<span data-ttu-id="61250-103">파일 및 스트림 I/O(입/출력)는 저장 매체로 데이터를 전송하거나 저장 매체로부터 데이터를 전송 받습니다.</span><span class="sxs-lookup"><span data-stu-id="61250-103">File and stream I/O (input/output) refers to the transfer of data either to or from a storage medium.</span></span> <span data-ttu-id="61250-104">.NET Framework에서 `System.IO` 네임스페이스는 데이터 스트림과 파일에서 읽기 및 쓰기를 동기적 및 비동기적으로 사용하는 형식을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="61250-104">In the .NET Framework, the `System.IO` namespaces contain types that enable reading and writing, both synchronously and asynchronously, on data streams and files.</span></span> <span data-ttu-id="61250-105">이러한 네임스페이스는 파일의 압축 및 압축 풀기 기능을 수행하는 형식 및 파이프 및 직렬 포트를 통한 통신을 가능하도록 하는 형식을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="61250-105">These namespaces also contain types that perform compression and decompression on files, and types that enable communication through pipes and serial ports.</span></span>  
  
 <span data-ttu-id="61250-106">파일은 정돈되고 이름이 지정된 컬렉션의 바이트이며, 이 컬렉션에는 영구 저장소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61250-106">A file is an ordered and named collection of bytes that has persistent storage.</span></span> <span data-ttu-id="61250-107">사용자가 파일을 사용할 때, 디렉터리 경로, 디스크 저장소 및 파일과 디렉터리 이름을 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="61250-107">When you work with files, you work with directory paths, disk storage, and file and directory names.</span></span> <span data-ttu-id="61250-108">반대로, 스트림은 여러 가지 저장 매체 중 하나인 백업 저장소(예를 들어, 디스크 또는 메모리)에서 읽고 사용할 수 있는 바이트 시퀀스입니다.</span><span class="sxs-lookup"><span data-stu-id="61250-108">In contrast, a stream is a sequence of bytes that you can use to read from and write to a backing store, which can be one of several storage mediums (for example, disks or memory).</span></span> <span data-ttu-id="61250-109">디스크 외에 여러 백업 저장소가 존재하듯이, 파이프 스트림 외에 여러 종류의 스트림, 예를 들어 네트워크, 메모리, 파일 스트림도 존재합니다.</span><span class="sxs-lookup"><span data-stu-id="61250-109">Just as there are several backing stores other than disks, there are several kinds of streams other than file streams, such as network, memory, and pipe streams.</span></span>  
  
## <a name="files-and-directories"></a><span data-ttu-id="61250-110">파일 및 디렉터리</span><span class="sxs-lookup"><span data-stu-id="61250-110">Files and Directories</span></span>  
 <span data-ttu-id="61250-111">사용자는 이 형식들을 <xref:System.IO?displayProperty=nameWithType> 네임스페이스에서 파일 및 디렉터리와 상호 작용하기 위해 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61250-111">You can use the types in the <xref:System.IO?displayProperty=nameWithType> namespace to interact with files and directories.</span></span> <span data-ttu-id="61250-112">예를 들어, 파일 및 디렉터리에 대한 속성을 가져오고 설정할 수 있고, 검색 조건에 따라 파일 및 디렉터리의 컬렉션을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61250-112">For example, you can get and set properties for files and directories, and retrieve collections of files and directories based on search criteria.</span></span>  
  
 <span data-ttu-id="61250-113">다음은 몇 가지 흔히 사용되는 파일 및 디렉터리 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="61250-113">Here are some commonly used file and directory classes:</span></span>  
  
-   <span data-ttu-id="61250-114"><xref:System.IO.File> - 파일 만들기, 복사, 삭제, 이동 및 열기를 위한 정적 메서드를 제공하고 <xref:System.IO.FileStream> 개체 만들기를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="61250-114"><xref:System.IO.File> - provides static methods for creating, copying, deleting, moving, and opening files, and helps create a <xref:System.IO.FileStream> object.</span></span>  
  
-   <span data-ttu-id="61250-115"><xref:System.IO.FileInfo> - 파일 만들기, 복사, 삭제, 이동 및 열기를 위한 인스턴스 메서드를 제공하고 <xref:System.IO.FileStream> 개체 만들기를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="61250-115"><xref:System.IO.FileInfo> - provides instance methods for creating, copying, deleting, moving, and opening files, and helps create a <xref:System.IO.FileStream> object.</span></span>  
  
-   <span data-ttu-id="61250-116"><xref:System.IO.Directory> - 디렉터리와 하위 디렉터리를 통해 만들고, 이동하고, 열거하기 위한 정적 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="61250-116"><xref:System.IO.Directory> - provides static methods for creating, moving, and enumerating through directories and subdirectories.</span></span>  
  
-   <span data-ttu-id="61250-117"><xref:System.IO.DirectoryInfo> - 디렉터리와 하위 디렉터리를 통해 만들고, 이동하고, 열거하기 위한 인스턴스 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="61250-117"><xref:System.IO.DirectoryInfo> - provides instance methods for creating, moving, and enumerating through directories and subdirectories.</span></span>  
  
-   <span data-ttu-id="61250-118"><xref:System.IO.Path> - 플랫폼 간에 호환되는 방식으로 디렉터리 문자열을 처리하기 위한 메서드와 속성을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="61250-118"><xref:System.IO.Path> - provides methods and properties for processing directory strings in a cross-platform manner.</span></span>  
  
 <span data-ttu-id="61250-119">Visual Basic 사용자는 이러한 클래스를 사용하는 것 외에도, 파일 I/O에 대한 <xref:Microsoft.VisualBasic.FileIO.FileSystem?displayProperty=nameWithType> 클래스에서 제공하는 메서드와 속성을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61250-119">In addition to using these classes, Visual Basic users can use the methods and properties provided by the <xref:Microsoft.VisualBasic.FileIO.FileSystem?displayProperty=nameWithType> class for file I/O.</span></span>  
  
 <span data-ttu-id="61250-120">[방법: 디렉터리 복사](../../../docs/standard/io/how-to-copy-directories.md), [방법: 디렉터리 목록 만들기](https://msdn.microsoft.com/library/4d2772b1-b991-4532-a8a6-6ef733277e69) 및 [방법: 디렉터리 및 파일 열거](../../../docs/standard/io/how-to-enumerate-directories-and-files.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="61250-120">See [How to: Copy Directories](../../../docs/standard/io/how-to-copy-directories.md), [How to: Create a Directory Listing](https://msdn.microsoft.com/library/4d2772b1-b991-4532-a8a6-6ef733277e69), and [How to: Enumerate Directories and Files](../../../docs/standard/io/how-to-enumerate-directories-and-files.md).</span></span>  
  
## <a name="streams"></a><span data-ttu-id="61250-121">스트림</span><span class="sxs-lookup"><span data-stu-id="61250-121">Streams</span></span>  
 <span data-ttu-id="61250-122">추상 기본 클래스 <xref:System.IO.Stream>은 바이트 읽기 및 쓰기를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="61250-122">The abstract base class <xref:System.IO.Stream> supports reading and writing bytes.</span></span> <span data-ttu-id="61250-123">스트림을 나타내는 모든 클래스는 <xref:System.IO.Stream> 클래스로부터 상속됩니다.</span><span class="sxs-lookup"><span data-stu-id="61250-123">All classes that represent streams inherit from the <xref:System.IO.Stream> class.</span></span> <span data-ttu-id="61250-124"><xref:System.IO.Stream> 클래스와 이 클래스에서 파생되는 클래스는 데이터 소스와 리포지토리의 일반 뷰를 제공하고, 이때 프로그래머는 운영 체제 및 내부 장치의 세부 사항에서 격리됩니다.</span><span class="sxs-lookup"><span data-stu-id="61250-124">The <xref:System.IO.Stream> class and its derived classes provide a common view of data sources and repositories, and isolate the programmer from the specific details of the operating system and underlying devices.</span></span>  
  
 <span data-ttu-id="61250-125">스트림에는 다음의 세 가지 기본 작업이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="61250-125">Streams involve three fundamental operations:</span></span>  
  
-   <span data-ttu-id="61250-126">읽기 - 스트림의 데이터를 바이트 배열과 같은 데이터 구조로 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="61250-126">Reading - transferring data from a stream into a data structure, such as an array of bytes.</span></span>  
  
-   <span data-ttu-id="61250-127">쓰기 - 데이터 소스에서 스트림으로 데이터를 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="61250-127">Writing - transferring data to a stream from a data source.</span></span>  
  
-   <span data-ttu-id="61250-128">검색 - 스트림 내에서 현재 위치를 쿼리하고 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="61250-128">Seeking - querying and modifying the current position within a stream.</span></span>  
  
 <span data-ttu-id="61250-129">내부 데이터 소스 또는 리포지토리에 따라 스트림에서 이러한 기능 중 일부만 지원할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61250-129">Depending on the underlying data source or repository, a stream might support only some of these capabilities.</span></span> <span data-ttu-id="61250-130">예를 들어, <xref:System.IO.Pipes.PipeStream> 클래스는 검색을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="61250-130">For example, the <xref:System.IO.Pipes.PipeStream> class does not support seeking.</span></span> <span data-ttu-id="61250-131"><xref:System.IO.Stream.CanRead%2A>, <xref:System.IO.Stream.CanWrite%2A>, <xref:System.IO.Stream.CanSeek%2A> 스트림 속성은 스트림이 지원하는 작업을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="61250-131">The <xref:System.IO.Stream.CanRead%2A>, <xref:System.IO.Stream.CanWrite%2A>, and <xref:System.IO.Stream.CanSeek%2A> properties of a stream specify the operations that the stream supports.</span></span>  
  
 <span data-ttu-id="61250-132">다음은 몇 가지 자주 사용되는 스트림 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="61250-132">Here are some commonly used stream classes:</span></span>  
  
-   <span data-ttu-id="61250-133"><xref:System.IO.FileStream> – 파일을 읽고 쓰는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="61250-133"><xref:System.IO.FileStream> – for reading and writing to a file.</span></span>  
  
-   <span data-ttu-id="61250-134"><xref:System.IO.IsolatedStorage.IsolatedStorageFileStream> – 격리된 저장소의 파일을 읽고 파일에 기록하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="61250-134"><xref:System.IO.IsolatedStorage.IsolatedStorageFileStream> – for reading and writing to a file in isolated storage.</span></span>  
  
-   <span data-ttu-id="61250-135"><xref:System.IO.MemoryStream> – 메모리를 백업 저장소로 읽고 여기에 기록하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="61250-135"><xref:System.IO.MemoryStream> – for reading and writing to memory as the backing store.</span></span>  
  
-   <span data-ttu-id="61250-136"><xref:System.IO.BufferedStream> – 읽기 및 쓰기 작업의 성능을 향상시키는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="61250-136"><xref:System.IO.BufferedStream> – for improving performance of read and write operations.</span></span>  
  
-   <span data-ttu-id="61250-137"><xref:System.Net.Sockets.NetworkStream> – 네트워크 소켓을 통한 읽기 및 쓰기를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="61250-137"><xref:System.Net.Sockets.NetworkStream> – for reading and writing over network sockets.</span></span>  
  
-   <span data-ttu-id="61250-138"><xref:System.IO.Pipes.PipeStream> – 익명 및 명명된 파이프를 통한 읽기와 쓰기를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="61250-138"><xref:System.IO.Pipes.PipeStream> – for reading and writing over anonymous and named pipes.</span></span>  
  
-   <span data-ttu-id="61250-139"><xref:System.Security.Cryptography.CryptoStream> – 데이터 스트림을 암호화 변환에 연결하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="61250-139"><xref:System.Security.Cryptography.CryptoStream> – for linking data streams to cryptographic transformations.</span></span>  
  
 <span data-ttu-id="61250-140">스트림의 비동기화 작업에 대한 예제는 [비동기 파일 I/O](../../../docs/standard/io/asynchronous-file-i-o.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="61250-140">For an example of working with streams asynchronously, see [Asynchronous File I/O](../../../docs/standard/io/asynchronous-file-i-o.md).</span></span>  
  
## <a name="readers-and-writers"></a><span data-ttu-id="61250-141">판독기 및 작성기</span><span class="sxs-lookup"><span data-stu-id="61250-141">Readers and Writers</span></span>  
 <span data-ttu-id="61250-142">또한 <xref:System.IO?displayProperty=nameWithType> 네임스페이스는 스트림으로부터 인코딩된 문자를 읽고 이를 스트림에 쓰기 위한 형식을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="61250-142">The <xref:System.IO?displayProperty=nameWithType> namespace also provides types for reading encoded characters from streams and writing them to streams.</span></span> <span data-ttu-id="61250-143">일반적으로 스트림은 바이트 입력 및 출력용으로 디자인됩니다.</span><span class="sxs-lookup"><span data-stu-id="61250-143">Typically, streams are designed for byte input and output.</span></span> <span data-ttu-id="61250-144">판독기 및 작성기 형식은 스트림 작업을 완료할 수 있도록 인코딩된 문자와 바이트의 변환을 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="61250-144">The reader and writer types handle the conversion of the encoded characters to and from bytes so the stream can complete the operation.</span></span> <span data-ttu-id="61250-145">각 판독기 및 작성기 클래스는 스트림과 연결되어 있고, 이것은 클래스의 `BaseStream` 속성을 통해 검색될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61250-145">Each reader and writer class is associated with a stream, which can be retrieved through the class's `BaseStream` property.</span></span>  
  
 <span data-ttu-id="61250-146">일부 자주 사용되는 판독기 및 작성기 클래스는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="61250-146">Here are some commonly used reader and writer classes:</span></span>  
  
-   <span data-ttu-id="61250-147"><xref:System.IO.BinaryReader> 및 <xref:System.IO.BinaryWriter> – 기본 데이터 형식을 바이너리 값으로 읽고 쓰는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="61250-147"><xref:System.IO.BinaryReader> and <xref:System.IO.BinaryWriter> – for reading and writing primitive data types as binary values.</span></span>  
  
-   <span data-ttu-id="61250-148"><xref:System.IO.StreamReader> 및 <xref:System.IO.StreamWriter> – 인코딩 값을 사용하여 바이트에서 문자, 문자에서 바이트로 변환함으로써 문자를 읽고 쓰는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="61250-148"><xref:System.IO.StreamReader> and <xref:System.IO.StreamWriter> – for reading and writing characters by using an encoding value to convert the characters to and from bytes.</span></span>  
  
-   <span data-ttu-id="61250-149"><xref:System.IO.StringReader> 및 <xref:System.IO.StringWriter> – 문자열에서 문자를, 문자에서 문자열을 읽고 쓰는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="61250-149"><xref:System.IO.StringReader> and <xref:System.IO.StringWriter> – for reading and writing characters to and from strings.</span></span>  
  
-   <span data-ttu-id="61250-150"><xref:System.IO.TextReader> 및 <xref:System.IO.TextWriter> – 이진 데이터가 아닌 문자 및 문자열을 읽고 쓰는 다른 판독기와 작성기에 대한 추상 기본 클래스로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="61250-150"><xref:System.IO.TextReader> and <xref:System.IO.TextWriter> – serve as the abstract base classes for other readers and writers that read and write characters and strings, but not binary data.</span></span>  
  
 <span data-ttu-id="61250-151">[방법: 파일의 텍스트 읽기](../../../docs/standard/io/how-to-read-text-from-a-file.md), [방법: 파일에 텍스트 쓰기](../../../docs/standard/io/how-to-write-text-to-a-file.md), [방법: 문자열에서 문자 읽기](../../../docs/standard/io/how-to-read-characters-from-a-string.md) 및 [방법: 문자열에 문자 쓰기](../../../docs/standard/io/how-to-write-characters-to-a-string.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="61250-151">See [How to: Read Text from a File](../../../docs/standard/io/how-to-read-text-from-a-file.md), [How to: Write Text to a File](../../../docs/standard/io/how-to-write-text-to-a-file.md), [How to: Read Characters from a String](../../../docs/standard/io/how-to-read-characters-from-a-string.md), and [How to: Write Characters to a String](../../../docs/standard/io/how-to-write-characters-to-a-string.md).</span></span>  
  
## <a name="asynchronous-io-operations"></a><span data-ttu-id="61250-152">비동기 I/O 작업</span><span class="sxs-lookup"><span data-stu-id="61250-152">Asynchronous I/O Operations</span></span>  
 <span data-ttu-id="61250-153">많은 양의 데이터를 읽거나 쓸 때 리소스가 많이 사용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61250-153">Reading or writing a large amount of data can be resource-intensive.</span></span> <span data-ttu-id="61250-154">이러한 작업은 응용 프로그램 사용자에게 응답을 유지해야 하는 경우 비동기적으로 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="61250-154">You should perform these tasks asynchronously if your application needs to remain responsive to the user.</span></span> <span data-ttu-id="61250-155">동기 I/O 작업에서 UI 스레드는 리소스 집약적인 작업이 완료될 때까지 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="61250-155">With synchronous I/O operations, the UI thread is blocked until the resource-intensive operation has completed.</span></span>  <span data-ttu-id="61250-156">[!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] 응용 프로그램을 개발할 때 비동기 I/O 작업을 사용하여 응용 프로그램이 작동을 멈춘 것처럼 보이지 않게 해줍니다.</span><span class="sxs-lookup"><span data-stu-id="61250-156">Use asynchronous I/O operations when developing [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] apps to prevent creating the impression that your app has stopped working.</span></span>  
  
 <span data-ttu-id="61250-157">비동기 멤버의 이름에는 `Async`가 포함됩니다(예: <xref:System.IO.Stream.CopyToAsync%2A>, <xref:System.IO.Stream.FlushAsync%2A>, <xref:System.IO.Stream.ReadAsync%2A> 및 <xref:System.IO.Stream.WriteAsync%2A> 메서드).</span><span class="sxs-lookup"><span data-stu-id="61250-157">The asynchronous members contain `Async` in their names, such as the <xref:System.IO.Stream.CopyToAsync%2A>, <xref:System.IO.Stream.FlushAsync%2A>,  <xref:System.IO.Stream.ReadAsync%2A>, and <xref:System.IO.Stream.WriteAsync%2A> methods.</span></span> <span data-ttu-id="61250-158">이러한 메서드는 `async` 및 `await` 키워드와 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="61250-158">You use these methods with the `async` and `await` keywords.</span></span>  
  
 <span data-ttu-id="61250-159">자세한 내용은 [비동기 파일 I/O](../../../docs/standard/io/asynchronous-file-i-o.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="61250-159">For more information, see [Asynchronous File I/O](../../../docs/standard/io/asynchronous-file-i-o.md).</span></span>  
  
## <a name="compression"></a><span data-ttu-id="61250-160">압축</span><span class="sxs-lookup"><span data-stu-id="61250-160">Compression</span></span>  
 <span data-ttu-id="61250-161">압축은 저장소에 맞춰 파일 크기를 줄이는 프로세스를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="61250-161">Compression refers to the process of reducing the size of a file for storage.</span></span> <span data-ttu-id="61250-162">압축 해제는 압축된 파일의 내용을 사용 가능한 형식으로 추출하는 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="61250-162">Decompression is the process of extracting the contents of a compressed file so they are in a usable format.</span></span> <span data-ttu-id="61250-163"><xref:System.IO.Compression?displayProperty=nameWithType> 네임스페이스는 파일 및 스트림을 압축하고 압축을 푸는 형식을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="61250-163">The <xref:System.IO.Compression?displayProperty=nameWithType> namespace contains types for compressing and decompressing files and streams.</span></span>  
  
 <span data-ttu-id="61250-164">다음 클래스는 파일과 스트림을 압축하고 압축 해제할 때 자주 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="61250-164">The following classes are frequently used when compressing and decompressing files and streams:</span></span>  
  
-   <span data-ttu-id="61250-165"><xref:System.IO.Compression.ZipArchive> – zip 보관 파일에 항목을 만들고 이를 검색하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="61250-165"><xref:System.IO.Compression.ZipArchive> – for creating and retrieving entries in the zip archive.</span></span>  
  
-   <span data-ttu-id="61250-166"><xref:System.IO.Compression.ZipArchiveEntry> – 압축된 파일을 표시할 때 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="61250-166"><xref:System.IO.Compression.ZipArchiveEntry> – for representing a compressed file.</span></span>  
  
-   <span data-ttu-id="61250-167"><xref:System.IO.Compression.ZipFile> – 압축된 패키지를 만들고 추출하고 여는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="61250-167"><xref:System.IO.Compression.ZipFile> – for creating,  extracting, and opening a compressed package.</span></span>  
  
-   <span data-ttu-id="61250-168"><xref:System.IO.Compression.ZipFileExtensions> – 압축된 패키지에 항목을 만들고 추출하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="61250-168"><xref:System.IO.Compression.ZipFileExtensions> – for creating and extracting entries in a compressed package.</span></span>  
  
-   <span data-ttu-id="61250-169"><xref:System.IO.Compression.DeflateStream> – Deflate 알고리즘을 사용하여 스트림을 압축 및 압축 해제하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="61250-169"><xref:System.IO.Compression.DeflateStream> – for compressing and decompressing streams using the Deflate algorithm.</span></span>  
  
-   <span data-ttu-id="61250-170"><xref:System.IO.Compression.GZipStream> – gzip 데이터 형식의 스트림을 압축 및 압축 해제하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="61250-170"><xref:System.IO.Compression.GZipStream> – for compressing and decompressing streams in gzip data format.</span></span>  
  
 <span data-ttu-id="61250-171">[방법: 파일 압축 및 추출](../../../docs/standard/io/how-to-compress-and-extract-files.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="61250-171">See [How to: Compress and Extract Files](../../../docs/standard/io/how-to-compress-and-extract-files.md).</span></span>  
  
## <a name="isolated-storage"></a><span data-ttu-id="61250-172">격리된 저장소</span><span class="sxs-lookup"><span data-stu-id="61250-172">Isolated Storage</span></span>  
 <span data-ttu-id="61250-173">격리된 저장소는 코드와 저장된 데이터를 연결하는 표준화된 방법을 정의하여 격리와 안전을 제공하는 데이터 저장소 메커니즘입니다.</span><span class="sxs-lookup"><span data-stu-id="61250-173">Isolated storage is a data storage mechanism that provides isolation and safety by defining standardized ways of associating code with saved data.</span></span> <span data-ttu-id="61250-174">저장소는 사용자, 어셈블리 및 도메인(옵션)에 의해 격리된 가상 파일 시스템을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="61250-174">The storage provides a virtual file system that is isolated by user, assembly, and (optionally) domain.</span></span> <span data-ttu-id="61250-175">격리된 저장소는 응용 프로그램에 사용자 파일을 액세스할 수 있는 권한이 없는 경우 특히 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="61250-175">Isolated storage is particularly useful when your application does not have permission to access user files.</span></span> <span data-ttu-id="61250-176">컴퓨터의 보안 정책에 의해 제어되는 방식으로 응용 프로그램에 대한 설정이나 파일을 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61250-176">You can save settings or files for your application in a manner that is controlled by the computer's security policy.</span></span>  
  
 <span data-ttu-id="61250-177">격리된 저장소는 [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] 응용 프로그램에 사용할 수 없습니다. 대신에, [Windows.Storage](/uwp/api/Windows.Storage) 네임스페이스의 응용 프로그램 데이터 클래스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="61250-177">Isolated storage is not available for [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] apps; instead, use application data classes in the [Windows.Storage](/uwp/api/Windows.Storage) namespace.</span></span> <span data-ttu-id="61250-178">자세한 내용은 Windows 개발자 센터에서 [응용 프로그램 데이터](/previous-versions/windows/apps/hh464917(v=win.10))를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="61250-178">For more information, see [Application data](/previous-versions/windows/apps/hh464917(v=win.10)) in the Windows Dev Center.</span></span>  
  
 <span data-ttu-id="61250-179">다음의 클래스는 격리된 저장소를 구현할 때 자주 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="61250-179">The following classes are frequently used when implementing isolated storage:</span></span>  
  
-   <span data-ttu-id="61250-180"><xref:System.IO.IsolatedStorage.IsolatedStorage> – 격리된 저장소 구현을 위한 기본 클래스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="61250-180"><xref:System.IO.IsolatedStorage.IsolatedStorage> – provides the base class for isolated storage implementations.</span></span>  
  
-   <span data-ttu-id="61250-181"><xref:System.IO.IsolatedStorage.IsolatedStorageFile> – 파일 및 디렉터리를 포함하는 격리된 저장소 영역을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="61250-181"><xref:System.IO.IsolatedStorage.IsolatedStorageFile> – provides an isolated storage area that contains files and directories.</span></span>  
  
-   <span data-ttu-id="61250-182"><xref:System.IO.IsolatedStorage.IsolatedStorageFileStream> - 격리된 저장소 내에서 파일을 노출시킵니다.</span><span class="sxs-lookup"><span data-stu-id="61250-182"><xref:System.IO.IsolatedStorage.IsolatedStorageFileStream> - exposes a file within isolated storage.</span></span>  
  
 <span data-ttu-id="61250-183">[격리된 저장소](../../../docs/standard/io/isolated-storage.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="61250-183">See [Isolated Storage](../../../docs/standard/io/isolated-storage.md).</span></span>  
  
## <a name="io-operations-in-windows-store-apps"></a><span data-ttu-id="61250-184">Windows 스토어 응용 프로그램의 I/O 작업</span><span class="sxs-lookup"><span data-stu-id="61250-184">I/O Operations in Windows Store apps</span></span>  
 <span data-ttu-id="61250-185">[!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)]에는 스트림에서 읽고 스트림에 쓰기 위한 다양한 형식이 포함됩니다. 하지만, 이 세트에 모든 .NET Framework I/O 형식이 포함되는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="61250-185">The [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)] contains many of the types for reading from and writing to streams; however, this set does not include all the .NET Framework I/O types.</span></span>  
  
 <span data-ttu-id="61250-186">다음은 [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] 응용 프로그램에서 I/O 작업을 사용할 때 알아야 할 몇 가지 중요한 차이점입니다.</span><span class="sxs-lookup"><span data-stu-id="61250-186">Some important differences to note when using I/O operations in [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] apps:</span></span>  
  
-   <span data-ttu-id="61250-187">특히 파일 작업에 관련된 형식(예: <xref:System.IO.File>, <xref:System.IO.FileInfo>, <xref:System.IO.Directory> 및 <xref:System.IO.DirectoryInfo>)은 [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)]에 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="61250-187">Types specifically related to file operations, such as <xref:System.IO.File>, <xref:System.IO.FileInfo>, <xref:System.IO.Directory> and <xref:System.IO.DirectoryInfo>, are not included in the [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)].</span></span> <span data-ttu-id="61250-188">대신에 [!INCLUDE[wrt](../../../includes/wrt-md.md)]의 [Windows.Storage](http://msdn.microsoft.com/library/windows/apps/windows.storage.aspx) 네임스페이스에 있는 형식(예: [StorageFile](http://msdn.microsoft.com/library/windows/apps/windows.storage.storagefile.aspx) 및 [StorageFolder](http://msdn.microsoft.com/library/windows/apps/windows.storage.storagefolder.aspx))을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="61250-188">Instead, use the types in the [Windows.Storage](http://msdn.microsoft.com/library/windows/apps/windows.storage.aspx) namespace of the [!INCLUDE[wrt](../../../includes/wrt-md.md)], such as [StorageFile](http://msdn.microsoft.com/library/windows/apps/windows.storage.storagefile.aspx) and [StorageFolder](http://msdn.microsoft.com/library/windows/apps/windows.storage.storagefolder.aspx).</span></span>  
  
-   <span data-ttu-id="61250-189">격리된 저장소는 사용할 수 없습니다. 대신에 [응용 프로그램 데이터](/previous-versions/windows/apps/hh464917(v=win.10))를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="61250-189">Isolated storage is not available; instead, use [application data](/previous-versions/windows/apps/hh464917(v=win.10)).</span></span>  
  
-   <span data-ttu-id="61250-190">비동기 메서드(예: <xref:System.IO.Stream.ReadAsync%2A> 및 <xref:System.IO.Stream.WriteAsync%2A>)를 사용하여 UI 스레드를 차단하지 못하게 합니다.</span><span class="sxs-lookup"><span data-stu-id="61250-190">Use asynchronous methods, such as <xref:System.IO.Stream.ReadAsync%2A> and <xref:System.IO.Stream.WriteAsync%2A>, to prevent blocking the UI thread.</span></span>  
  
-   <span data-ttu-id="61250-191">경로 기반 압축 형식 <xref:System.IO.Compression.ZipFile> 및 <xref:System.IO.Compression.ZipFileExtensions>는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="61250-191">The path-based compression types <xref:System.IO.Compression.ZipFile> and <xref:System.IO.Compression.ZipFileExtensions> are not available.</span></span> <span data-ttu-id="61250-192">대신에, [Windows.Storage.Compression](http://msdn.microsoft.com/library/windows/apps/windows.storage.compression.aspx) 네임스페이스에서 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="61250-192">Instead, use the types in the [Windows.Storage.Compression](http://msdn.microsoft.com/library/windows/apps/windows.storage.compression.aspx) namespace.</span></span>  
  
 <span data-ttu-id="61250-193">필요하다면 .NET Framework 스트림과 Windows 런타임 스트림 간에 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61250-193">You can convert between .NET Framework streams and Windows Runtime streams, if necessary.</span></span> <span data-ttu-id="61250-194">자세한 내용은 [방법: .NET Framework 스트림과 Windows 런타임 스트림 간 변환](../../../docs/standard/io/how-to-convert-between-dotnet-streams-and-winrt-streams.md) 또는 [System.IO.WindowsRuntimeStreamExtensions](https://msdn.microsoft.com/library/system.io.windowsruntimestreamextensions.aspx)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="61250-194">For more information, see [How to: Convert Between .NET Framework Streams and Windows Runtime Streams](../../../docs/standard/io/how-to-convert-between-dotnet-streams-and-winrt-streams.md) or [System.IO.WindowsRuntimeStreamExtensions](https://msdn.microsoft.com/library/system.io.windowsruntimestreamextensions.aspx).</span></span> <!--zz TODO: <xref:System.IO.WindowsRuntimeStreamExtensions>--> 
  
 <span data-ttu-id="61250-195">[!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] 앱에서 I/O 작업에 대한 자세한 내용은 [빠른 시작: 파일 읽기 및 쓰기](/previous-versions/windows/apps/hh758325(v=win.10))를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="61250-195">For more information about I/O operations in a [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] app, see [Quickstart: Reading and writing files](/previous-versions/windows/apps/hh758325(v=win.10)).</span></span>  
  
## <a name="io-and-security"></a><span data-ttu-id="61250-196">I/O와 보안</span><span class="sxs-lookup"><span data-stu-id="61250-196">I/O and Security</span></span>  
 <span data-ttu-id="61250-197"><xref:System.IO?displayProperty=nameWithType> 네임스페이스에서 클래스를 사용할 때, 파일 및 디렉터리에 대한 액세스를 제어하기 위해 액세스 제어 목록(ACL)과 같은 운영 체제 보안 요구 사항을 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="61250-197">When you use the classes in the <xref:System.IO?displayProperty=nameWithType> namespace, you must follow operating system security requirements such as access control lists (ACLs) to control access to files and directories.</span></span> <span data-ttu-id="61250-198"><xref:System.Security.Permissions.FileIOPermission> 요구 사항에 이 요구 사항이 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="61250-198">This requirement is in addition to any <xref:System.Security.Permissions.FileIOPermission> requirements.</span></span> <span data-ttu-id="61250-199">ACL은 프로그래밍 방식으로 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61250-199">You can manage ACLs programmatically.</span></span> <span data-ttu-id="61250-200">자세한 내용은 [방법: Access Control 목록 항목 추가 또는 제거](../../../docs/standard/io/how-to-add-or-remove-access-control-list-entries.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="61250-200">For more information, see [How to: Add or Remove Access Control List Entries](../../../docs/standard/io/how-to-add-or-remove-access-control-list-entries.md).</span></span>  
  
 <span data-ttu-id="61250-201">기본 보안 정책은 인터넷 또는 인트라넷 응용 프로그램에서 사용자의 컴퓨터에 있는 파일의 액세스를 방지합니다.</span><span class="sxs-lookup"><span data-stu-id="61250-201">Default security policies prevent Internet or intranet applications from accessing files on the user’s computer.</span></span> <span data-ttu-id="61250-202">따라서 실제 파일의 경로를 인터넷이나 인트라넷을 통해 다운로드되는 코드를 작성할 때 필요한 I/O 클래스를 사용하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="61250-202">Therefore, do not use the I/O classes that require a path to a physical file when writing code that will be downloaded over the Internet or intranet.</span></span> <span data-ttu-id="61250-203">대신에 기존의 .NET Framework 응용 프로그램의 경우 [격리된 저장소](../../../docs/standard/io/isolated-storage.md)를 사용하거나 [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] 응용 프로그램의 경우 [응용 프로그램 데이터](/previous-versions/windows/apps/hh464917(v=win.10))를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="61250-203">Instead, use [isolated storage](../../../docs/standard/io/isolated-storage.md) for traditional .NET Framework applications, or use [application data](/previous-versions/windows/apps/hh464917(v=win.10)) for [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] apps.</span></span>  
  
 <span data-ttu-id="61250-204">스트림이 생성될 때만 보안 검사가 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="61250-204">A security check is performed only when the stream is constructed.</span></span> <span data-ttu-id="61250-205">따라서 스트림을 열지 말고, 이것을 신뢰할 수 없는 코드 또는 응용 프로그램 도메인으로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="61250-205">Therefore, do not open a stream and then pass it to less-trusted code or application domains.</span></span>  
  
## <a name="related-topics"></a><span data-ttu-id="61250-206">관련 항목</span><span class="sxs-lookup"><span data-stu-id="61250-206">Related Topics</span></span>  
  
-   [<span data-ttu-id="61250-207">공통적인 I/O 작업</span><span class="sxs-lookup"><span data-stu-id="61250-207">Common I/O Tasks</span></span>](../../../docs/standard/io/common-i-o-tasks.md)  
  
 <span data-ttu-id="61250-208">파일, 디렉터리 및 스트림과 관련된 I/O 작업 목록과 각 작업에 대한 예제 및 관련 내용에 대한 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="61250-208">Provides a list of I/O tasks associated with files, directories, and streams, and links to relevant content and examples for each task.</span></span>  
  
-   [<span data-ttu-id="61250-209">비동기 파일 I/O</span><span class="sxs-lookup"><span data-stu-id="61250-209">Asynchronous File I/O</span></span>](../../../docs/standard/io/asynchronous-file-i-o.md)  
  
 <span data-ttu-id="61250-210">비동기 I/O의 기본 연산 및 성능상의 이점에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="61250-210">Describes the performance advantages and basic operation of asynchronous I/O.</span></span>  
  
-   [<span data-ttu-id="61250-211">격리된 저장소</span><span class="sxs-lookup"><span data-stu-id="61250-211">Isolated Storage</span></span>](../../../docs/standard/io/isolated-storage.md)  
  
 <span data-ttu-id="61250-212">코드와 저장된 데이터를 연결하는 표준화된 방법을 정의하여 격리와 안전을 제공하는 데이터 저장소 메커니즘에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="61250-212">Describes a data storage mechanism that provides isolation and safety by defining standardized ways of associating code with saved data.</span></span>  
  
-   [<span data-ttu-id="61250-213">파이프</span><span class="sxs-lookup"><span data-stu-id="61250-213">Pipes</span></span>](../../../docs/standard/io/pipe-operations.md)  
  
 <span data-ttu-id="61250-214">.NET Framework에서 익명 사용자와 명명된 파이프 작업에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="61250-214">Describes anonymous and named pipe operations in the .NET Framework.</span></span>  
  
-   [<span data-ttu-id="61250-215">메모리 매핑된 파일</span><span class="sxs-lookup"><span data-stu-id="61250-215">Memory-Mapped Files</span></span>](../../../docs/standard/io/memory-mapped-files.md)  
  
 <span data-ttu-id="61250-216">가상 메모리의 디스크에 있는 파일의 내용을 포함하는 메모리 매핑된 파일에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="61250-216">Describes memory-mapped files, which contain the contents of files on disk in virtual memory.</span></span> <span data-ttu-id="61250-217">메모리 매핑된 파일을 사용하면 매우 큰 파일을 편집하고 프로세스 간 통신을 위한 공유 메모리를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61250-217">You can use memory-mapped files to edit very large files and to create shared memory for interprocess communication.</span></span>
