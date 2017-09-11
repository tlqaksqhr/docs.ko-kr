---
title: "방법: 파일 또는 폴더 만들기(C# 프로그래밍 가이드)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- folders [C#]
- creating files [C#]
- files [C#]
- creating folders [C#]
ms.assetid: 4582ee2d-d72d-4687-bcb9-08d336c62c25
caps.latest.revision: 22
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
ms.openlocfilehash: 150190eeef829bd0431eeea7789025b9905553e3
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-create-a-file-or-folder-c-programming-guide"></a><span data-ttu-id="2593a-102">방법: 파일 또는 폴더 만들기(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="2593a-102">How to: Create a File or Folder (C# Programming Guide)</span></span>
<span data-ttu-id="2593a-103">프로그래밍 방식으로 컴퓨터에 폴더를 만들고, 하위 폴더를 만들고, 하위 폴더에 파일을 만들고, 파일에 데이터를 쓸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2593a-103">You can programmatically create a folder on your computer, create a subfolder, create a file in the subfolder, and write data to the file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2593a-104">예제</span><span class="sxs-lookup"><span data-stu-id="2593a-104">Example</span></span>  
 <span data-ttu-id="2593a-105">[!code-cs[csFilesandFolders#10](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-create-a-file-or-folder_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="2593a-105">[!code-cs[csFilesandFolders#10](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-create-a-file-or-folder_1.cs)]</span></span>  
  
 <span data-ttu-id="2593a-106">폴더가 이미 있으면 <xref:System.IO.Directory.CreateDirectory%2A>는 아무 작업도 수행하지 않으며 예외가 throw되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2593a-106">If the folder already exists, <xref:System.IO.Directory.CreateDirectory%2A> does nothing, and no exception is thrown.</span></span> <span data-ttu-id="2593a-107">그러나 <xref:System.IO.File.Create%2A?displayProperty=fullName>는 기존 파일을 새 파일로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="2593a-107">However, <xref:System.IO.File.Create%2A?displayProperty=fullName> replaces an existing file with a new file.</span></span> <span data-ttu-id="2593a-108">이 예제에서는 `if`-`else` 문을 사용하여 기존 파일이 바뀌지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="2593a-108">The example uses an `if`-`else` statement to prevent an existing file from being replaced.</span></span>  
  
 <span data-ttu-id="2593a-109">예제에서 다음을 변경하여 특정 이름의 파일이 이미 있는지 여부에 따라 다른 결과를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2593a-109">By making the following changes in the example, you can specify different outcomes based on whether a file with a certain name already exists.</span></span> <span data-ttu-id="2593a-110">파일이 없는 경우 코드에서 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2593a-110">If such a file doesn't exist, the code creates one.</span></span> <span data-ttu-id="2593a-111">파일이 있는 경우 코드에서 해당 파일에 데이터를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2593a-111">If such a file exists, the code appends data to that file.</span></span>  
  
-   <span data-ttu-id="2593a-112">임의가 아닌 파일 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2593a-112">Specify a non-random file name.</span></span>  
  
    ```csharp  
    // Comment out the following line.  
    //string fileName = System.IO.Path.GetRandomFileName();  
  
    // Replace that line with the following assignment.  
    string fileName = "MyNewFile.txt";  
    ```  
  
-   <span data-ttu-id="2593a-113">다음 코드를 사용하여 `if`-`else` 문을 `using` 문으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="2593a-113">Replace the `if`-`else` statement with the `using` statement in the following code.</span></span>  
  
    ```csharp  
    using (System.IO.FileStream fs = new System.IO.FileStream(pathString, FileMode.Append))   
    {  
        for (byte i = 0; i < 100; i++)  
        {  
            fs.WriteByte(i);  
        }  
    }  
    ```  
  
 <span data-ttu-id="2593a-114">예제를 여러 번 실행하여 매번 파일에 데이터가 추가되는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="2593a-114">Run the example several times to verify that data is added to the file each time.</span></span>  
  
 <span data-ttu-id="2593a-115">시도할 수 있는 추가 `FileMode` 값은 <xref:System.IO.FileMode>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2593a-115">For more `FileMode` values that you can try, see <xref:System.IO.FileMode>.</span></span>  
  
 <span data-ttu-id="2593a-116">다음 조건에서 예외가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="2593a-116">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="2593a-117">폴더 이름 형식이 잘못된 경우.</span><span class="sxs-lookup"><span data-stu-id="2593a-117">The folder name is malformed.</span></span> <span data-ttu-id="2593a-118">예를 들어 잘못된 문자를 포함하거나 공백만으로 이루어져 있습니다(<xref:System.ArgumentException> 클래스).</span><span class="sxs-lookup"><span data-stu-id="2593a-118">For example, it contains illegal characters or is only white space (<xref:System.ArgumentException> class).</span></span> <span data-ttu-id="2593a-119"><xref:System.IO.Path> 클래스를 사용하여 유효한 경로 이름을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2593a-119">Use the <xref:System.IO.Path> class to create valid path names.</span></span>  
  
-   <span data-ttu-id="2593a-120">만들 폴더의 부모 폴더가 읽기 전용입니다(<xref:System.IO.IOException> 클래스).</span><span class="sxs-lookup"><span data-stu-id="2593a-120">The parent folder of the folder to be created is read-only (<xref:System.IO.IOException> class).</span></span>  
  
-   <span data-ttu-id="2593a-121">폴더 이름이 `null`입니다(<xref:System.ArgumentNullException> 클래스).</span><span class="sxs-lookup"><span data-stu-id="2593a-121">The folder name is `null` (<xref:System.ArgumentNullException> class).</span></span>  
  
-   <span data-ttu-id="2593a-122">폴더 이름이 너무 깁니다(<xref:System.IO.PathTooLongException> 클래스).</span><span class="sxs-lookup"><span data-stu-id="2593a-122">The folder name is too long (<xref:System.IO.PathTooLongException> class).</span></span>  
  
-   <span data-ttu-id="2593a-123">폴더 이름이 콜론(“:”)뿐입니다(<xref:System.IO.PathTooLongException> 클래스).</span><span class="sxs-lookup"><span data-stu-id="2593a-123">The folder name is only a colon, ":" (<xref:System.IO.PathTooLongException> class).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="2593a-124">.NET Framework 보안</span><span class="sxs-lookup"><span data-stu-id="2593a-124">.NET Framework Security</span></span>  
 <span data-ttu-id="2593a-125">부분 신뢰 상황에서는 <xref:System.Security.SecurityException> 클래스의 인스턴스가 throw될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2593a-125">An instance of the <xref:System.Security.SecurityException> class may be thrown in partial-trust situations.</span></span>  
  
 <span data-ttu-id="2593a-126">폴더를 만들 수 있는 권한이 없는 경우 이 예제에서는 <xref:System.UnauthorizedAccessException> 클래스의 인스턴스가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="2593a-126">If you don’t have permission to create the folder, the example throws an instance of the <xref:System.UnauthorizedAccessException> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2593a-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2593a-127">See Also</span></span>  
 <span data-ttu-id="2593a-128"><xref:System.IO?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="2593a-128"><xref:System.IO?displayProperty=fullName></span></span>   
 <span data-ttu-id="2593a-129">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="2593a-129">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="2593a-130">파일 시스템 및 레지스트리(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="2593a-130">File System and the Registry (C# Programming Guide)</span></span>](../../../csharp/programming-guide/file-system/index.md)

