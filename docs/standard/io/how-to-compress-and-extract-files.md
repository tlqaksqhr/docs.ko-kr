---
title: '방법: 파일 압축 및 추출'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- I/O [.NET Framework], compression
- compression
- compress files
ms.assetid: e9876165-3c60-4c84-a272-513e47acf579
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f3e535e13fe91e1a5cb9c868428f5edbb9eac03f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-compress-and-extract-files"></a><span data-ttu-id="f6b17-102">방법: 파일 압축 및 추출</span><span class="sxs-lookup"><span data-stu-id="f6b17-102">How to: Compress and Extract Files</span></span>
<span data-ttu-id="f6b17-103"><xref:System.IO.Compression> 네임스페이스는 파일 및 스트림을 압축하고 압축을 푸는 다음 형식을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="f6b17-103">The <xref:System.IO.Compression> namespace contains the following types for compressing and decompressing files and streams.</span></span> <span data-ttu-id="f6b17-104">또한 이러한 형식을 사용하여 압축된 파일의 내용을 읽고 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6b17-104">You can also use these types to read and modify the contents of a compressed file:</span></span>  
  
-   <xref:System.IO.Compression.ZipFile>  
  
-   <xref:System.IO.Compression.ZipArchive>  
  
-   <xref:System.IO.Compression.ZipArchiveEntry>  
  
-   <xref:System.IO.Compression.DeflateStream>  
  
-   <xref:System.IO.Compression.GZipStream>  
  
 <span data-ttu-id="f6b17-105">다음 예제에서는 압축된 파일로 작업할 때 수행할 수 있는 일부 기능을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f6b17-105">The following examples show some of the functions you can perform when working with compressed files.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f6b17-106">예</span><span class="sxs-lookup"><span data-stu-id="f6b17-106">Example</span></span>  
 <span data-ttu-id="f6b17-107">이 예제에서는 <xref:System.IO.Compression.ZipFile> 클래스를 사용하여 .zip 파일 이름 확장명을 가진 압축된 파일을 만들고 추출하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f6b17-107">This example shows how to create and extract a compressed file that has a .zip file name extension by using the <xref:System.IO.Compression.ZipFile> class.</span></span> <span data-ttu-id="f6b17-108">폴더의 내용을 새로운 .zip 파일에 압축한 다음 해당 내용을 새 폴더에 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="f6b17-108">It compresses the contents of a folder into a new .zip file and then extracts that content to a new folder.</span></span> <span data-ttu-id="f6b17-109"><xref:System.IO.Compression.ZipFile> 클래스를 사용하려면 프로젝트에서 `System.IO.Compression.FileSystem` 어셈블리를 참조해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6b17-109">To use the <xref:System.IO.Compression.ZipFile> class, you must reference the `System.IO.Compression.FileSystem` assembly in your project.</span></span>  
  
 [!code-csharp[System.IO.Compression.ZipFile#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.zipfile/cs/program1.cs#1)]
 [!code-vb[System.IO.Compression.ZipFile#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.zipfile/vb/program1.vb#1)]  
  
## <a name="example"></a><span data-ttu-id="f6b17-110">예</span><span class="sxs-lookup"><span data-stu-id="f6b17-110">Example</span></span>  
 <span data-ttu-id="f6b17-111">다음 예제는 기존 .zip 파일의 내용을 반복하는 방법과 확장명이 .txt인 파일을 추출하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f6b17-111">The next example shows how to iterate through the contents of an existing .zip file and extract files that have a .txt extension.</span></span> <span data-ttu-id="f6b17-112"><xref:System.IO.Compression.ZipArchive> 클래스를 기존 .zip 파일에 액세스하는 데 사용하고 <xref:System.IO.Compression.ZipArchiveEntry> 클래스를 압축된 파일 내의 개별 항목을 검사하는 데 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f6b17-112">It uses the <xref:System.IO.Compression.ZipArchive> class to access an existing .zip file, and the <xref:System.IO.Compression.ZipArchiveEntry> class to inspect the individual entries in the compressed file.</span></span> <span data-ttu-id="f6b17-113"><xref:System.IO.Compression.ZipFileExtensions.ExtractToFile%2A> 개체에 대해 확장 메서드(<xref:System.IO.Compression.ZipArchiveEntry>)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f6b17-113">It uses an extension method (<xref:System.IO.Compression.ZipFileExtensions.ExtractToFile%2A>) for the <xref:System.IO.Compression.ZipArchiveEntry> object.</span></span> <span data-ttu-id="f6b17-114">확장 메서드는 <xref:System.IO.Compression.ZipFileExtensions?displayProperty=nameWithType> 클래스에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6b17-114">The extension method is available in the <xref:System.IO.Compression.ZipFileExtensions?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="f6b17-115"><xref:System.IO.Compression.ZipFileExtensions> 클래스를 사용하려면 프로젝트에서 `System.IO.Compression.FileSystem` 어셈블리를 참조해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6b17-115">To use the <xref:System.IO.Compression.ZipFileExtensions> class, you must reference the `System.IO.Compression.FileSystem` assembly in your project.</span></span>  
  
 [!code-csharp[System.IO.Compression.ZipArchive#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.ziparchive/cs/program1.cs#1)]
 [!code-vb[System.IO.Compression.ZipArchive#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.ziparchive/vb/program1.vb#1)]  
  
## <a name="example"></a><span data-ttu-id="f6b17-116">예</span><span class="sxs-lookup"><span data-stu-id="f6b17-116">Example</span></span>  
 <span data-ttu-id="f6b17-117">다음 예제에서는 <xref:System.IO.Compression.ZipArchive> 클래스를 사용하여 기존 .zip 파일을 액세스하고, 압축된 파일에 새 파일을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f6b17-117">The next example uses the <xref:System.IO.Compression.ZipArchive> class to access an existing .zip file, and adds a new file to the compressed file.</span></span> <span data-ttu-id="f6b17-118">새 파일은 기존 .zip 파일에 추가할 때 압축됩니다.</span><span class="sxs-lookup"><span data-stu-id="f6b17-118">The new file gets compressed when you add it to the existing .zip file.</span></span>  
  
 [!code-csharp[System.IO.Compression.ZipArchiveMode#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.ziparchivemode/cs/program1.cs#1)]
 [!code-vb[System.IO.Compression.ZipArchiveMode#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.ziparchivemode/vb/program1.vb#1)]  
  
## <a name="example"></a><span data-ttu-id="f6b17-119">예</span><span class="sxs-lookup"><span data-stu-id="f6b17-119">Example</span></span>  
 <span data-ttu-id="f6b17-120"><xref:System.IO.Compression.GZipStream> 및 <xref:System.IO.Compression.DeflateStream> 클래스를 사용하여 데이터를 압축하거나 압축을 풀 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6b17-120">You can also use the <xref:System.IO.Compression.GZipStream> and <xref:System.IO.Compression.DeflateStream> classes to compress and decompress data.</span></span> <span data-ttu-id="f6b17-121">동일한 압축 알고리즘을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f6b17-121">They use the same compression algorithm.</span></span> <span data-ttu-id="f6b17-122">확장명이 .gz인 파일에 쓰인 압축된 <xref:System.IO.Compression.GZipStream> 개체는 <xref:System.IO.Compression.GZipStream>에서 제공한 메서드 외에도 여러 공통 도구를 사용하여 압축을 풀 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6b17-122">Compressed <xref:System.IO.Compression.GZipStream> objects that are written to a file that has an extension of .gz can be decompressed by using many common tools in addition to the methods provided by <xref:System.IO.Compression.GZipStream>.</span></span> <span data-ttu-id="f6b17-123">이 예제에서는 <xref:System.IO.Compression.GZipStream> 클래스를 사용하여 파일의 디렉터리를 압축하고 압축을 푸는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="f6b17-123">This example shows how to compress and decompress a directory of files by using the <xref:System.IO.Compression.GZipStream> class.</span></span>  
  
 [!code-csharp[IO.Compression.GZip1#1](../../../samples/snippets/csharp/VS_Snippets_CLR/IO.Compression.GZip1/CS/gziptest.cs#1)]
 [!code-vb[IO.Compression.GZip1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/IO.Compression.GZip1/VB/gziptest.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="f6b17-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f6b17-124">See Also</span></span>  
 <xref:System.IO.Compression.ZipArchive>  
 <xref:System.IO.Compression.ZipFile>  
 <xref:System.IO.Compression.ZipArchiveEntry>  
 <xref:System.IO.Compression.DeflateStream>  
 <xref:System.IO.Compression.GZipStream>  
 [<span data-ttu-id="f6b17-125">파일 및 스트림 I/O</span><span class="sxs-lookup"><span data-stu-id="f6b17-125">File and Stream I/O</span></span>](../../../docs/standard/io/index.md)
