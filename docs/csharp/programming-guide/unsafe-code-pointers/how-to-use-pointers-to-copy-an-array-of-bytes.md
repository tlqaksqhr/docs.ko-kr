---
title: "방법: 포인터를 사용하여 바이트 배열 복사(C# 프로그래밍 가이드)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- byte arrays [C#]
- arrays [C#], byte
- pointers [C#], to copy bytes
ms.assetid: ec16fbb4-a24e-45f5-a763-9499d3fabe0a
caps.latest.revision: "21"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 375cab76063e4c77515d6b05b42f2d97ff3efc44
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-pointers-to-copy-an-array-of-bytes--c-programming-guide"></a><span data-ttu-id="71a92-102">방법: 포인터를 사용하여 바이트 배열 복사(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="71a92-102">How to: Use Pointers to Copy an Array of Bytes  (C# Programming Guide)</span></span>
<span data-ttu-id="71a92-103">다음 예제에서는 포인터를 사용하여 배열 간에 바이트를 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="71a92-103">The following example uses pointers to copy bytes from one array to another.</span></span>  
  
 <span data-ttu-id="71a92-104">이 예제에서는 `Copy` 메서드에서 포인터를 사용할 수 있도록 하는 [unsafe](../../../csharp/language-reference/keywords/unsafe.md) 키워드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="71a92-104">This example uses the [unsafe](../../../csharp/language-reference/keywords/unsafe.md) keyword, which enables you to use pointers in the `Copy` method.</span></span> <span data-ttu-id="71a92-105">[fixed](../../../csharp/language-reference/keywords/fixed-statement.md) 문은 소스 및 대상 배열에 대한 포인터를 선언하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="71a92-105">The [fixed](../../../csharp/language-reference/keywords/fixed-statement.md) statement is used to declare pointers to the source and destination arrays.</span></span> <span data-ttu-id="71a92-106">이렇게 하면 소스 및 대상 배열의 위치가 메모리에 *고정*되므로 가비지 수집에 의해 이동되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="71a92-106">This *pins* the location of the source and destination arrays in memory so that they will not be moved by garbage collection.</span></span> <span data-ttu-id="71a92-107">`fixed` 블록이 완료되면 배열에 대한 메모리 블록이 고정 해제됩니다.</span><span class="sxs-lookup"><span data-stu-id="71a92-107">The memory blocks for the arrays are unpinned when the `fixed` block is completed.</span></span> <span data-ttu-id="71a92-108">이 예제의 `Copy` 메서드는 `unsafe` 키워드를 사용하기 때문에 **/unsafe** 컴파일러 옵션으로 컴파일해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="71a92-108">Because the `Copy` method in this example uses the `unsafe` keyword, it must be compiled with the **/unsafe** compiler option.</span></span> <span data-ttu-id="71a92-109">Visual Studio에서 이 옵션을 설정하려면 프로젝트 이름을 마우스 오른쪽 단추로 클릭하고 **속성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="71a92-109">To set the option in Visual Studio, right-click the project name, and then click **Properties**.</span></span> <span data-ttu-id="71a92-110">**빌드** 탭에서 **안전하지 않은 코드 허용**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="71a92-110">On the **Build** tab, select **Allow unsafe code**.</span></span>  
  
## <a name="example"></a><span data-ttu-id="71a92-111">예제</span><span class="sxs-lookup"><span data-stu-id="71a92-111">Example</span></span>  
 [!code-csharp[csProgGuidePointers#3](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-use-pointers-to-copy-an-array-of-bytes_1.cs)]  
  
 [!code-csharp[csProgGuidePointers#18](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-use-pointers-to-copy-an-array-of-bytes_2.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="71a92-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="71a92-112">See Also</span></span>  
 [<span data-ttu-id="71a92-113">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="71a92-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="71a92-114">안전하지 않은 코드 및 포인터</span><span class="sxs-lookup"><span data-stu-id="71a92-114">Unsafe Code and Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/index.md)  
 [<span data-ttu-id="71a92-115">/unsafe(C# 컴파일러 옵션)</span><span class="sxs-lookup"><span data-stu-id="71a92-115">/unsafe (C# Compiler Options)</span></span>](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md)  
 [<span data-ttu-id="71a92-116">가비지 수집</span><span class="sxs-lookup"><span data-stu-id="71a92-116">Garbage Collection</span></span>](../../../standard/garbage-collection/index.md)
