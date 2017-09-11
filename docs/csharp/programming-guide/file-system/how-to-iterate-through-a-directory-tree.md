---
title: "방법: 디렉터리 트리 반복(C# 프로그래밍 가이드)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- iterating through folders [C#]
- file iteration [C#]
ms.assetid: c4be4a75-6b1b-46a7-9d38-bab353091ed7
caps.latest.revision: 10
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 562431f525cc58b5d630671c9015e30a14ea06ee
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-iterate-through-a-directory-tree-c-programming-guide"></a><span data-ttu-id="e2aec-102">방법: 디렉터리 트리 반복(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="e2aec-102">How to: Iterate Through a Directory Tree (C# Programming Guide)</span></span>
<span data-ttu-id="e2aec-103">"디렉터리 트리 반복" 구는 지정된 루트 폴더 아래의 임의 깊이까지 중첩된 각 하위 디렉터리에 있는 각 파일에 대한 액세스를 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="e2aec-103">The phrase "iterate a directory tree" means to access each file in each nested subdirectory under a specified root folder, to any depth.</span></span> <span data-ttu-id="e2aec-104">반드시 각 파일을 열 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e2aec-104">You do not necessarily have to open each file.</span></span> <span data-ttu-id="e2aec-105">단순히 파일 또는 하위 디렉터리의 이름을 `string`으로 검색하거나, <xref:System.IO.FileInfo?displayProperty=fullName> 또는 <xref:System.IO.DirectoryInfo?displayProperty=fullName> 개체의 형태로 추가 정보를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2aec-105">You can just retrieve the name of the file or subdirectory as a `string`, or you can retrieve additional information in the form of a <xref:System.IO.FileInfo?displayProperty=fullName> or <xref:System.IO.DirectoryInfo?displayProperty=fullName> object.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e2aec-106">Windows에서 "디렉터리" 및 "폴더" 용어는 같은 의미로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e2aec-106">In Windows, the terms "directory" and "folder" are used interchangeably.</span></span> <span data-ttu-id="e2aec-107">대부분의 설명서와 사용자 인터페이스 텍스트는 "폴더"라는 용어를 사용하지만 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 클래스 라이브러리는 "디렉터리"라는 용어를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e2aec-107">Most documentation and user interface text uses the term "folder," but the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] class library uses the term "directory."</span></span>  
  
 <span data-ttu-id="e2aec-108">지정된 루트 아래의 모든 디렉터리에 대해 확실히 액세스 권한이 있는 가장 간단한 경우에는 `System.IO.SearchOption.AllDirectories` 플래그를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2aec-108">In the simplest case, in which you know for certain that you have access permissions for all directories under a specified root, you can use the `System.IO.SearchOption.AllDirectories` flag.</span></span> <span data-ttu-id="e2aec-109">이 플래그는 지정된 패턴과 일치하는 모든 중첩된 하위 디렉터리를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="e2aec-109">This flag returns all the nested subdirectories that match the specified pattern.</span></span> <span data-ttu-id="e2aec-110">다음 예제에서는 이 플래그를 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e2aec-110">The following example shows how to use this flag.</span></span>  
  
```csharp  
root.GetDirectories("*.*", System.IO.SearchOption.AllDirectories);  
```  
  
 <span data-ttu-id="e2aec-111">이 방식의 취약성은 지정된 루트 아래의 하위 디렉터리 중 하나에서 <xref:System.IO.DirectoryNotFoundException> 또는 <xref:System.UnauthorizedAccessException>이 발생할 경우 전체 메서드가 실패하고 디렉터리가 반환되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e2aec-111">The weakness in this approach is that if any one of the subdirectories under the specified root causes a <xref:System.IO.DirectoryNotFoundException> or <xref:System.UnauthorizedAccessException>, the whole method fails and returns no directories.</span></span> <span data-ttu-id="e2aec-112"><xref:System.IO.DirectoryInfo.GetFiles%2A> 메서드를 사용하는 경우도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="e2aec-112">The same is true when you use the <xref:System.IO.DirectoryInfo.GetFiles%2A> method.</span></span> <span data-ttu-id="e2aec-113">특정 하위 폴더에서 이러한 예외를 처리해야 하는 경우 다음 예제와 같이 디렉터리 트리를 수동으로 탐색해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2aec-113">If you have to handle these exceptions on specific subfolders, you must manually walk the directory tree, as shown in the following examples.</span></span>  
  
 <span data-ttu-id="e2aec-114">디렉터리 트리를 수동으로 탐색하는 경우 하위 디렉터리를 먼저 처리하거나(*전위 순회*), 파일을 먼저 처리(*후위 순회*)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2aec-114">When you manually walk a directory tree, you can handle the subdirectories first (*pre-order traversal*), or the files first (*post-order traversal*).</span></span> <span data-ttu-id="e2aec-115">전위 순회를 수행하는 경우 해당 폴더 자체에 바로 있는 파일을 반복하기 전에 현재 폴더 아래의 전체 트리를 탐색합니다.</span><span class="sxs-lookup"><span data-stu-id="e2aec-115">If you perform a pre-order traversal, you walk the whole tree under the current folder before iterating through the files that are directly in that folder itself.</span></span> <span data-ttu-id="e2aec-116">이 문서의 뒷부분에 나오는 예제에서는 후위 순회를 수행하지만 전위 순회를 수행하도록 쉽게 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2aec-116">The examples later in this document perform post-order traversal, but you can easily modify them to perform pre-order traversal.</span></span>  
  
 <span data-ttu-id="e2aec-117">또 다른 옵션은 재귀 또는 스택 기반 탐색을 사용하는지 여부입니다.</span><span class="sxs-lookup"><span data-stu-id="e2aec-117">Another option is whether to use recursion or a stack-based traversal.</span></span> <span data-ttu-id="e2aec-118">이 문서의 뒷부분에 나오는 예제에서는 두 가지 방식을 모두 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e2aec-118">The examples later in this document show both approaches.</span></span>  
  
 <span data-ttu-id="e2aec-119">파일 및 폴더에 대해 다양한 작업을 수행해야 하는 경우 단일 대리자를 통해 호출할 수 있는 별도 함수로 작업을 리팩터링하여 이러한 예제를 모듈화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2aec-119">If you have to perform a variety of operations on files and folders, you can modularize these examples by refactoring the operation into separate functions that you can invoke by using a single delegate.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e2aec-120">NTFS 파일 시스템에는 *재분석 지점*이 *연결 지점*, *기호 링크* 및 *하드 링크* 형태로 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2aec-120">NTFS file systems can contain *reparse points* in the form of *junction points*, *symbolic links*, and *hard links*.</span></span> <span data-ttu-id="e2aec-121"><xref:System.IO.DirectoryInfo.GetFiles%2A>, <xref:System.IO.DirectoryInfo.GetDirectories%2A> 등의 .NET Framework 메서드는 재분석 지점 아래의 하위 디렉터리를 반환하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e2aec-121">The .NET Framework methods such as <xref:System.IO.DirectoryInfo.GetFiles%2A> and <xref:System.IO.DirectoryInfo.GetDirectories%2A> will not return any subdirectories under a reparse point.</span></span> <span data-ttu-id="e2aec-122">이 동작은 두 재분석 지점이 서로를 가리키는 경우 무한 루프로 전환되는 위험으로부터 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="e2aec-122">This behavior guards against the risk of entering into an infinite loop when two reparse points refer to each other.</span></span> <span data-ttu-id="e2aec-123">일반적으로 재분석 지점을 다룰 때는 파일이 실수로 수정되거나 삭제되지 않도록 특별히 주의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2aec-123">In general, you should use extreme caution when you deal with reparse points to ensure that you do not unintentionally modify or delete files.</span></span> <span data-ttu-id="e2aec-124">재분석 지점을 정밀하게 제어해야 하는 경우 플랫폼 호출 또는 네이티브 코드를 사용하여 적절한 Win32 파일 시스템 메서드를 직접 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="e2aec-124">If you require precise control over reparse points, use platform invoke or native code to call the appropriate Win32 file system methods directly.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e2aec-125">예제</span><span class="sxs-lookup"><span data-stu-id="e2aec-125">Example</span></span>  
 <span data-ttu-id="e2aec-126">다음 예제에서는 재귀를 사용하여 디렉터리 트리를 탐색하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e2aec-126">The following example shows how to walk a directory tree by using recursion.</span></span> <span data-ttu-id="e2aec-127">재귀 방식은 세련된 방식이긴 하지만 디렉터리 트리가 크고 깊이 중첩된 경우 스택 오버플로 예외가 발생할 가능성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2aec-127">The recursive approach is elegant but has the potential to cause a stack overflow exception if the directory tree is large and deeply nested.</span></span>  
  
 <span data-ttu-id="e2aec-128">처리되는 특정 예외와 각 파일 또는 폴더에서 수행되는 특정 작업은 예로만 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="e2aec-128">The particular exceptions that are handled, and the particular actions that are performed on each file or folder, are provided as examples only.</span></span> <span data-ttu-id="e2aec-129">특정 요구 사항에 맞게 이 코드를 수정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2aec-129">You should modify this code to meet your specific requirements.</span></span> <span data-ttu-id="e2aec-130">자세한 내용은 코드 주석을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e2aec-130">See the comments in the code for more information.</span></span>  
  
 <span data-ttu-id="e2aec-131">[!code-cs[csFilesandFolders#1](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-iterate-through-a-directory-tree_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="e2aec-131">[!code-cs[csFilesandFolders#1](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-iterate-through-a-directory-tree_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="e2aec-132">예제</span><span class="sxs-lookup"><span data-stu-id="e2aec-132">Example</span></span>  
 <span data-ttu-id="e2aec-133">다음 예제에서는 재귀를 사용하지 않고 디렉터리 트리의 파일 및 폴더를 반복하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e2aec-133">The following example shows how to iterate through files and folders in a directory tree without using recursion.</span></span> <span data-ttu-id="e2aec-134">이 기술은 LIFO(후입선출) 스택인 제네릭 <xref:System.Collections.Generic.Stack%601> 컬렉션 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e2aec-134">This technique uses the generic <xref:System.Collections.Generic.Stack%601> collection type, which is a last in first out (LIFO) stack.</span></span>  
  
 <span data-ttu-id="e2aec-135">처리되는 특정 예외와 각 파일 또는 폴더에서 수행되는 특정 작업은 예로만 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="e2aec-135">The particular exceptions that are handled, and the particular actions that are performed on each file or folder, are provided as examples only.</span></span> <span data-ttu-id="e2aec-136">특정 요구 사항에 맞게 이 코드를 수정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2aec-136">You should modify this code to meet your specific requirements.</span></span> <span data-ttu-id="e2aec-137">자세한 내용은 코드 주석을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e2aec-137">See the comments in the code for more information.</span></span>  
  
 <span data-ttu-id="e2aec-138">[!code-cs[csFilesandFolders#2](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-iterate-through-a-directory-tree_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="e2aec-138">[!code-cs[csFilesandFolders#2](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-iterate-through-a-directory-tree_2.cs)]</span></span>  
  
 <span data-ttu-id="e2aec-139">일반적으로 모든 폴더를 테스트하여 응용 프로그램에 폴더를 열 수 있는 권한이 있는지 확인하려면 너무 많은 시간이 걸립니다.</span><span class="sxs-lookup"><span data-stu-id="e2aec-139">It is generally too time-consuming to test every folder to determine whether your application has permission to open it.</span></span> <span data-ttu-id="e2aec-140">따라서 코드 예제에서는 해당 작업 부분을 `try/catch` 블록으로 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="e2aec-140">Therefore, the code example just encloses that part of the operation in a `try/catch` block.</span></span> <span data-ttu-id="e2aec-141">폴더에 대한 액세스가 거부될 경우 사용 권한을 높인 후 다시 액세스를 시도하도록 `catch` 블록을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2aec-141">You can modify the `catch` block so that when you are denied access to a folder, you try to elevate your permissions and then access it again.</span></span> <span data-ttu-id="e2aec-142">일반적으로 응용 프로그램을 알 수 없는 상태로 유지하지 않고 처리할 수 있는 예외만 catch합니다.</span><span class="sxs-lookup"><span data-stu-id="e2aec-142">As a rule, only catch those exceptions that you can handle without leaving your application in an unknown state.</span></span>  
  
 <span data-ttu-id="e2aec-143">디렉터리 트리의 내용을 메모리 내 또는 디스크에 저장해야 하는 경우 최상의 옵션은 각 파일의 <xref:System.IO.FileSystemInfo.FullName%2A> 속성(`string` 형식)만 저장하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e2aec-143">If you must store the contents of a directory tree, either in memory or on disk, the best option is to store only the <xref:System.IO.FileSystemInfo.FullName%2A> property (of type `string`) for each file.</span></span> <span data-ttu-id="e2aec-144">그런 다음 이 문자열을 사용하여 필요에 따라 <xref:System.IO.FileInfo> 또는 <xref:System.IO.DirectoryInfo> 개체를 새로 만들거나, 추가 처리가 필요한 파일을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2aec-144">You can then use this string to create a new <xref:System.IO.FileInfo> or <xref:System.IO.DirectoryInfo> object as necessary, or open any file that requires additional processing.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="e2aec-145">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="e2aec-145">Robust Programming</span></span>  
 <span data-ttu-id="e2aec-146">강력한 파일 반복 코드는 파일 시스템의 여러 복잡성을 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2aec-146">Robust file iteration code must take into account many complexities of the file system.</span></span> <span data-ttu-id="e2aec-147">자세한 내용은 [NTFS 기술 참조](http://go.microsoft.com/fwlink/?LinkId=79488)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e2aec-147">For more information, see [NTFS Technical Reference](http://go.microsoft.com/fwlink/?LinkId=79488).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2aec-148">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e2aec-148">See Also</span></span>  
 <span data-ttu-id="e2aec-149"><xref:System.IO></span><span class="sxs-lookup"><span data-stu-id="e2aec-149"><xref:System.IO></span></span>   
 <span data-ttu-id="e2aec-150">[LINQ 및 파일 디렉터리](http://msdn.microsoft.com/library/5a5d516c-0279-4a84-ac84-b87f54caa808) </span><span class="sxs-lookup"><span data-stu-id="e2aec-150">[LINQ and File Directories](http://msdn.microsoft.com/library/5a5d516c-0279-4a84-ac84-b87f54caa808) </span></span>  
 [<span data-ttu-id="e2aec-151">파일 시스템 및 레지스트리(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="e2aec-151">File System and the Registry (C# Programming Guide)</span></span>](../../../csharp/programming-guide/file-system/index.md)

