---
title: "C# 프로그램의 일반적인 구조(C# 프로그래밍 가이드)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- C# language, program structure
ms.assetid: 5ae964a5-0ef0-40fe-88fb-6d1793371d0d
caps.latest.revision: 21
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
ms.openlocfilehash: d55ac6a6d35e5f47ab26da681afe9fb5555331ec
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="general-structure-of-a-c-program-c-programming-guide"></a><span data-ttu-id="82ea8-102">C# 프로그램의 일반적인 구조(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="82ea8-102">General Structure of a C# Program (C# Programming Guide)</span></span>
<span data-ttu-id="82ea8-103">C# 프로그램은 하나 이상의 파일로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="82ea8-103">C# programs can consist of one or more files.</span></span> <span data-ttu-id="82ea8-104">각 파일에는 0개 이상의 네임스페이스가 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82ea8-104">Each file can contain zero or more namespaces.</span></span> <span data-ttu-id="82ea8-105">네임스페이스에는 다른 네임스페이스 외에 클래스, 구조체, 인터페이스, 열거형 및 대리자 같은 형식이 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82ea8-105">A namespace can contain types such as classes, structs, interfaces, enumerations, and delegates, in addition to other namespaces.</span></span> <span data-ttu-id="82ea8-106">다음은 이러한 모든 요소를 포함하는 C# 프로그램의 기본 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="82ea8-106">The following is the skeleton of a C# program that contains all of these elements.</span></span>  
  
 <span data-ttu-id="82ea8-107">[!code-cs[csProgGuide#34](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/general-structure-of-a-csharp-program_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="82ea8-107">[!code-cs[csProgGuide#34](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/general-structure-of-a-csharp-program_1.cs)]</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="82ea8-108">관련 단원</span><span class="sxs-lookup"><span data-stu-id="82ea8-108">Related Sections</span></span>  
 <span data-ttu-id="82ea8-109">추가 정보</span><span class="sxs-lookup"><span data-stu-id="82ea8-109">For more information:</span></span>  
  
-   [<span data-ttu-id="82ea8-110">클래스</span><span class="sxs-lookup"><span data-stu-id="82ea8-110">Classes</span></span>](../../../csharp/programming-guide/classes-and-structs/classes.md)  
  
-   [<span data-ttu-id="82ea8-111">구조체</span><span class="sxs-lookup"><span data-stu-id="82ea8-111">Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/structs.md)  
  
-   [<span data-ttu-id="82ea8-112">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="82ea8-112">Namespaces</span></span>](../../../csharp/programming-guide/namespaces/index.md)  
  
-   [<span data-ttu-id="82ea8-113">인터페이스</span><span class="sxs-lookup"><span data-stu-id="82ea8-113">Interfaces</span></span>](../../../csharp/programming-guide/interfaces/index.md)  
  
-   [<span data-ttu-id="82ea8-114">대리자</span><span class="sxs-lookup"><span data-stu-id="82ea8-114">Delegates</span></span>](../../../csharp/programming-guide/delegates/index.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="82ea8-115">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="82ea8-115">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="82ea8-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="82ea8-116">See Also</span></span>  
 <span data-ttu-id="82ea8-117">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="82ea8-117">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="82ea8-118">[C# 프로그램 내부](../../../csharp/programming-guide/inside-a-program/index.md) </span><span class="sxs-lookup"><span data-stu-id="82ea8-118">[Inside a C# Program](../../../csharp/programming-guide/inside-a-program/index.md) </span></span>  
 <span data-ttu-id="82ea8-119">[C# 참조](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="82ea8-119">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 [<span data-ttu-id="82ea8-120">\<paveover>C# 샘플 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="82ea8-120">\<paveover>C# Sample Applications</span></span>](http://msdn.microsoft.com/en-us/9a9d7aaa-51d3-4224-b564-95409b0f3e15)

