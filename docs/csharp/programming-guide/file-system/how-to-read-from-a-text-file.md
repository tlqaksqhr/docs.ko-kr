---
title: '방법: 텍스트 파일에서 읽기(C# 프로그래밍 가이드)'
ms.date: 07/20/2015
f1_keywords:
- StreamReader.ReadToEnd
helpviewer_keywords:
- text files, writing to
- reading text files
- reading data, text files
- text files, reading
ms.assetid: 92246c5b-e819-4eea-9370-1a9460e12de3
ms.openlocfilehash: a42f98a81ff9e9bdbbf6c61554667aa223c7c269
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-read-from-a-text-file-c-programming-guide"></a><span data-ttu-id="e4dd2-102">방법: 텍스트 파일에서 읽기(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="e4dd2-102">How to: Read From a Text File (C# Programming Guide)</span></span>
<span data-ttu-id="e4dd2-103">이 예제에서는 <xref:System.IO.File?displayProperty=nameWithType> 클래스의 정적 메서드 <xref:System.IO.File.ReadAllText%2A> 및 <xref:System.IO.File.ReadAllLines%2A>를 사용하여 텍스트 파일의 내용을 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="e4dd2-103">This example reads the contents of a text file by using the static methods <xref:System.IO.File.ReadAllText%2A> and <xref:System.IO.File.ReadAllLines%2A> from the <xref:System.IO.File?displayProperty=nameWithType> class.</span></span>  
  
 <span data-ttu-id="e4dd2-104"><xref:System.IO.StreamReader>를 사용하는 예제는 [방법: 텍스트 파일을 한 번에 한 줄씩 읽기](../../../csharp/programming-guide/file-system/how-to-read-a-text-file-one-line-at-a-time.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e4dd2-104">For an example that uses <xref:System.IO.StreamReader>, see [How to: Read a Text File One Line at a Time](../../../csharp/programming-guide/file-system/how-to-read-a-text-file-one-line-at-a-time.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e4dd2-105">이 예제에 사용되는 파일은 [방법: 텍스트 파일에 쓰기](../../../csharp/programming-guide/file-system/how-to-write-to-a-text-file.md) 항목에서 생성되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e4dd2-105">The files that are used in this example are created in the topic [How to: Write to a Text File](../../../csharp/programming-guide/file-system/how-to-write-to-a-text-file.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e4dd2-106">예</span><span class="sxs-lookup"><span data-stu-id="e4dd2-106">Example</span></span>  
 [!code-csharp[csFilesandFolders#4](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-read-from-a-text-file_1.cs)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="e4dd2-107">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="e4dd2-107">Compiling the Code</span></span>  
 <span data-ttu-id="e4dd2-108">코드를 복사하고 C# 콘솔 응용 프로그램에 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="e4dd2-108">Copy the code and paste it into a C# console application.</span></span>  
  
 <span data-ttu-id="e4dd2-109">[방법: 텍스트 파일에 쓰기](../../../csharp/programming-guide/file-system/how-to-write-to-a-text-file.md)의 텍스트 파일을 사용하지 않는 경우 `ReadAllText` 및 `ReadAllLines`에 대한 인수를 사용자 컴퓨터의 적절한 경로 및 파일 이름으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="e4dd2-109">If you are not using the text files from [How to: Write to a Text File](../../../csharp/programming-guide/file-system/how-to-write-to-a-text-file.md), replace the argument to `ReadAllText` and `ReadAllLines` with the appropriate path and file name on your computer.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="e4dd2-110">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="e4dd2-110">Robust Programming</span></span>  
 <span data-ttu-id="e4dd2-111">다음 조건에서 예외가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="e4dd2-111">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="e4dd2-112">파일이 없거나 지정된 위치에 없는 경우.</span><span class="sxs-lookup"><span data-stu-id="e4dd2-112">The file doesn't exist or doesn't exist at the specified location.</span></span> <span data-ttu-id="e4dd2-113">경로와 파일 이름의 철자를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="e4dd2-113">Check the path and the spelling of the file name.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="e4dd2-114">.NET Framework 보안</span><span class="sxs-lookup"><span data-stu-id="e4dd2-114">.NET Framework Security</span></span>  
 <span data-ttu-id="e4dd2-115">파일 이름을 사용하여 파일 내용을 확인하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="e4dd2-115">Do not rely on the name of a file to determine the contents of the file.</span></span> <span data-ttu-id="e4dd2-116">예를 들어 `myFile.cs` 파일이 C# 소스 파일이 아닐 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4dd2-116">For example, the file `myFile.cs` might not be a C# source file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4dd2-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e4dd2-117">See Also</span></span>  
 <xref:System.IO?displayProperty=nameWithType>  
 [<span data-ttu-id="e4dd2-118">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="e4dd2-118">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="e4dd2-119">파일 시스템 및 레지스트리(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="e4dd2-119">File System and the Registry (C# Programming Guide)</span></span>](../../../csharp/programming-guide/file-system/index.md)
