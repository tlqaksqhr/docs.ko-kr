---
title: "방법: 텍스트 파일에 쓰기(C# 프로그래밍 가이드)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- TextWriter.WriteLine
- StreamWriter.Close
helpviewer_keywords:
- files [C#], text files
- text, writing to files [C#]
ms.assetid: 2e99f184-d88b-4719-a7f1-d9ec482aa809
caps.latest.revision: "23"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: c576536947cdb4984d6e5ce67c8377fe23b354c7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-write-to-a-text-file-c-programming-guide"></a><span data-ttu-id="66794-102">방법: 텍스트 파일에 쓰기(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="66794-102">How to: Write to a Text File (C# Programming Guide)</span></span>
<span data-ttu-id="66794-103">다음 코드 예제에서는 파일에 텍스트를 쓰는 여러 가지 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="66794-103">These examples show various ways to write text to a file.</span></span>  <span data-ttu-id="66794-104">처음 두 예제에서는 <xref:System.IO.File?displayProperty=nameWithType> 클래스에서 정적 편의 메서드를 사용하여 IEnumerable\<string>의 각 요소와 문자열을 텍스트 파일에 씁니다.</span><span class="sxs-lookup"><span data-stu-id="66794-104">The first two examples use static convenience methods on the <xref:System.IO.File?displayProperty=nameWithType> class to write each element of any IEnumerable\<string> and a string to a text file.</span></span>  <span data-ttu-id="66794-105">예제 3에서는 파일에 쓸 때 각 줄을 개별적으로 처리해야 하는 경우 파일에 텍스트를 추가하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="66794-105">Example 3 shows how to add text to a file when you have to process each line individually as you write to the file.</span></span>  <span data-ttu-id="66794-106">예제 1-3에서는 파일의 기존 내용을 모두 덮어쓰지만 예제 4에서는 기존 파일에 텍스트를 추가하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="66794-106">Examples 1-3 overwrite all existing content in the file, but example 4 shows you how to append text to an existing file.</span></span>  
  
 <span data-ttu-id="66794-107">이 네 예제에서는 모두 파일에 문자열 리터럴을 쓰지만 대개는 <xref:System.String.Format%2A> 메서드를 사용합니다. 이 메서드는 필드에서 값을 오른쪽 또는 왼쪽 맞춤으로 정렬하고 안쪽 여백을 포함하거나 포함하지 않는 등 다양한 형식의 값을 쓰기 위한 많은 컨트롤을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="66794-107">These examples all write string literals to files, but more likely you will want to use the <xref:System.String.Format%2A> method, which has many controls for writing different types of values  right or left justified in a field, with or without padding, and so on.</span></span>  <span data-ttu-id="66794-108">C# [문자열 보간](../../../csharp/language-reference/keywords/interpolated-strings.md) 기능을 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66794-108">You can also use the C# [string interpolation](../../../csharp/language-reference/keywords/interpolated-strings.md) feature.</span></span>  
  
## <a name="example"></a><span data-ttu-id="66794-109">예제</span><span class="sxs-lookup"><span data-stu-id="66794-109">Example</span></span>  
 [!code-csharp[csFilesandFolders#3](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-write-to-a-text-file_1.cs)]  
  
 <span data-ttu-id="66794-110">이 네 예제에서는 모두 파일에 문자열 리터럴을 쓰지만 대개는 <xref:System.String.Format%2A> 메서드를 사용합니다. 이 메서드는 필드에서 값을 오른쪽 또는 왼쪽 맞춤으로 정렬하고 안쪽 여백을 포함하거나 포함하지 않는 등 다양한 형식의 값을 쓰기 위한 많은 컨트롤을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="66794-110">These examples all write string literals to files, but more likely you will want to use the <xref:System.String.Format%2A> method, which has many controls for writing different types of values  right or left justified in a field, with or without padding, and so on.</span></span>  <span data-ttu-id="66794-111">C# [문자열 보간](../../../csharp/language-reference/keywords/interpolated-strings.md) 기능을 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66794-111">You can also use the C# [string interpolation](../../../csharp/language-reference/keywords/interpolated-strings.md) feature.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="66794-112">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="66794-112">Robust Programming</span></span>  
 <span data-ttu-id="66794-113">다음 조건에서 예외가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="66794-113">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="66794-114">파일이 있지만 읽기 전용인 경우</span><span class="sxs-lookup"><span data-stu-id="66794-114">The file exists and is read-only.</span></span>  
  
-   <span data-ttu-id="66794-115">경로 이름이 너무 긴 경우</span><span class="sxs-lookup"><span data-stu-id="66794-115">The path name may be too long.</span></span>  
  
-   <span data-ttu-id="66794-116">디스크가 꽉 찬 경우</span><span class="sxs-lookup"><span data-stu-id="66794-116">The disk may be full.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66794-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="66794-117">See Also</span></span>  
 [<span data-ttu-id="66794-118">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="66794-118">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="66794-119">파일 시스템 및 레지스트리(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="66794-119">File System and the Registry (C# Programming Guide)</span></span>](../../../csharp/programming-guide/file-system/index.md)  
 [<span data-ttu-id="66794-120">샘플: 응용 프로그램 저장소에 컬렉션 저장</span><span class="sxs-lookup"><span data-stu-id="66794-120">Sample: Save a collection to Application Storage</span></span>](http://code.msdn.microsoft.com/CSWinStoreAppSaveCollection-bed5d6e6)
