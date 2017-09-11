---
title: "방법: 파일 및 폴더 복사, 삭제 및 이동(C# 프로그래밍 가이드)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- I/O [C#]
ms.assetid: 62e52cd7-9597-4e4a-acf9-1315f5cdbf05
caps.latest.revision: 13
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
ms.openlocfilehash: a4cfec46e0af0056a0de20a1ed83a370cd010055
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-copy-delete-and-move-files-and-folders-c-programming-guide"></a><span data-ttu-id="1a9f6-102">방법: 파일 및 폴더 복사, 삭제 및 이동(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="1a9f6-102">How to: Copy, Delete, and Move Files and Folders (C# Programming Guide)</span></span>
<span data-ttu-id="1a9f6-103">다음 예제에서는 <xref:System.IO?displayProperty=fullName> 네임스페이스의 <xref:System.IO.File?displayProperty=fullName>, <xref:System.IO.Directory?displayProperty=fullName>, <xref:System.IO.FileInfo?displayProperty=fullName>, <xref:System.IO.DirectoryInfo?displayProperty=fullName> 클래스를 사용하여 파일과 폴더를 동기 방식으로 복사, 이동 및 삭제하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1a9f6-103">The following examples show how to copy, move, and delete files and folders in a synchronous manner by using the <xref:System.IO.File?displayProperty=fullName>, <xref:System.IO.Directory?displayProperty=fullName>, <xref:System.IO.FileInfo?displayProperty=fullName>, and <xref:System.IO.DirectoryInfo?displayProperty=fullName> classes from the <xref:System.IO?displayProperty=fullName> namespace.</span></span> <span data-ttu-id="1a9f6-104">이러한 예제는 진행률 표시줄이나 다른 사용자 인터페이스를 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1a9f6-104">These examples do not provide a progress bar or any other user interface.</span></span> <span data-ttu-id="1a9f6-105">표준 진행률 대화 상자를 제공하려는 경우 [방법: 파일 작업에 대한 진행률 대화 상자 제공](how-to-provide-a-progress-dialog-box-for-file-operations.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1a9f6-105">If you want to provide a standard progress dialog box, see [How to: Provide a Progress Dialog Box for File Operations](how-to-provide-a-progress-dialog-box-for-file-operations.md).</span></span>  
  
 <span data-ttu-id="1a9f6-106"><xref:System.IO.FileSystemWatcher?displayProperty=fullName>를 사용하여 여러 파일에 대해 작업할 때 진행률을 계산할 수 있는 이벤트를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a9f6-106">Use <xref:System.IO.FileSystemWatcher?displayProperty=fullName> to provide events that will enable you to calculate the progress when operating on multiple files.</span></span> <span data-ttu-id="1a9f6-107">또 다른 방법은 플랫폼 호출을 사용하여 Windows Shell에서 적절한 파일 관련 메서드를 호출하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1a9f6-107">Another approach is to use platform invoke to call the relevant file-related methods in the Windows Shell.</span></span> <span data-ttu-id="1a9f6-108">이러한 파일 작업을 비동기적으로 수행하는 방법에 대한 자세한 내용은 [비동기 파일 I/O](https://msdn.microsoft.com/library/kztecsys)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1a9f6-108">For information about how to perform these file operations asynchronously, see [Asynchronous File I/O](https://msdn.microsoft.com/library/kztecsys).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1a9f6-109">예제</span><span class="sxs-lookup"><span data-stu-id="1a9f6-109">Example</span></span>  
 <span data-ttu-id="1a9f6-110">다음 예제에서는 파일 및 디렉터리를 복사하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1a9f6-110">The following example shows how to copy files and directories.</span></span>  
  
 <span data-ttu-id="1a9f6-111">[!code-cs[csFilesandFolders#7](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-copy-delete-and-move-files-and-folders_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="1a9f6-111">[!code-cs[csFilesandFolders#7](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-copy-delete-and-move-files-and-folders_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="1a9f6-112">예제</span><span class="sxs-lookup"><span data-stu-id="1a9f6-112">Example</span></span>  
 <span data-ttu-id="1a9f6-113">다음 예제에서는 파일 및 디렉터리를 이동하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1a9f6-113">The following example shows how to move files and directories.</span></span>  
  
 <span data-ttu-id="1a9f6-114">[!code-cs[csFilesandFolders#8](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-copy-delete-and-move-files-and-folders_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="1a9f6-114">[!code-cs[csFilesandFolders#8](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-copy-delete-and-move-files-and-folders_2.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="1a9f6-115">예제</span><span class="sxs-lookup"><span data-stu-id="1a9f6-115">Example</span></span>  
 <span data-ttu-id="1a9f6-116">다음 예제에서는 파일 및 디렉터리를 삭제하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1a9f6-116">The following example shows how to delete files and directories.</span></span>  
  
 <span data-ttu-id="1a9f6-117">[!code-cs[csFilesandFolders#9](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-copy-delete-and-move-files-and-folders_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="1a9f6-117">[!code-cs[csFilesandFolders#9](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-copy-delete-and-move-files-and-folders_3.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a9f6-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1a9f6-118">See Also</span></span>  
 <span data-ttu-id="1a9f6-119"><xref:System.IO?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="1a9f6-119"><xref:System.IO?displayProperty=fullName></span></span>   
 <span data-ttu-id="1a9f6-120">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="1a9f6-120">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="1a9f6-121">[파일 시스템 및 레지스트리(C# 프로그래밍 가이드)](index.md) </span><span class="sxs-lookup"><span data-stu-id="1a9f6-121">[File System and the Registry (C# Programming Guide)](index.md) </span></span>  
 <span data-ttu-id="1a9f6-122">[방법: 파일 작업에 대한 진행률 대화 상자 제공](how-to-provide-a-progress-dialog-box-for-file-operations.md) </span><span class="sxs-lookup"><span data-stu-id="1a9f6-122">[How to: Provide a Progress Dialog Box for File Operations](how-to-provide-a-progress-dialog-box-for-file-operations.md) </span></span>  
 <span data-ttu-id="1a9f6-123">[파일 및 스트림 I/O](https://msdn.microsoft.com/library/k3352a4t) </span><span class="sxs-lookup"><span data-stu-id="1a9f6-123">[File and Stream I/O](https://msdn.microsoft.com/library/k3352a4t) </span></span>  
 [<span data-ttu-id="1a9f6-124">공통적인 I/O 작업</span><span class="sxs-lookup"><span data-stu-id="1a9f6-124">Common I/O Tasks</span></span>](https://msdn.microsoft.com/library/ms404278)

