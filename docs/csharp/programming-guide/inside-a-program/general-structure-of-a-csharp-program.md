---
title: "C# 프로그램의 일반적인 구조(C# 프로그래밍 가이드)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords: C# language, program structure
ms.assetid: 5ae964a5-0ef0-40fe-88fb-6d1793371d0d
caps.latest.revision: "21"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 8886f7601ce4d1de4a6b277a803ff87eb67bee78
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="general-structure-of-a-c-program-c-programming-guide"></a><span data-ttu-id="8aabe-102">C# 프로그램의 일반적인 구조(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="8aabe-102">General Structure of a C# Program (C# Programming Guide)</span></span>
<span data-ttu-id="8aabe-103">C# 프로그램은 하나 이상의 파일로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="8aabe-103">C# programs can consist of one or more files.</span></span> <span data-ttu-id="8aabe-104">각 파일에는 0개 이상의 네임스페이스가 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8aabe-104">Each file can contain zero or more namespaces.</span></span> <span data-ttu-id="8aabe-105">네임스페이스에는 다른 네임스페이스 외에 클래스, 구조체, 인터페이스, 열거형 및 대리자 같은 형식이 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8aabe-105">A namespace can contain types such as classes, structs, interfaces, enumerations, and delegates, in addition to other namespaces.</span></span> <span data-ttu-id="8aabe-106">다음은 이러한 모든 요소를 포함하는 C# 프로그램의 기본 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="8aabe-106">The following is the skeleton of a C# program that contains all of these elements.</span></span>  
  
 [!code-csharp[csProgGuide#34](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/general-structure-of-a-csharp-program_1.cs)]  
  
## <a name="related-sections"></a><span data-ttu-id="8aabe-107">관련 단원</span><span class="sxs-lookup"><span data-stu-id="8aabe-107">Related Sections</span></span>  
 <span data-ttu-id="8aabe-108">추가 정보</span><span class="sxs-lookup"><span data-stu-id="8aabe-108">For more information:</span></span>  
  
-   [<span data-ttu-id="8aabe-109">클래스</span><span class="sxs-lookup"><span data-stu-id="8aabe-109">Classes</span></span>](../../../csharp/programming-guide/classes-and-structs/classes.md)  
  
-   [<span data-ttu-id="8aabe-110">구조체</span><span class="sxs-lookup"><span data-stu-id="8aabe-110">Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/structs.md)  
  
-   [<span data-ttu-id="8aabe-111">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="8aabe-111">Namespaces</span></span>](../../../csharp/programming-guide/namespaces/index.md)  
  
-   [<span data-ttu-id="8aabe-112">인터페이스</span><span class="sxs-lookup"><span data-stu-id="8aabe-112">Interfaces</span></span>](../../../csharp/programming-guide/interfaces/index.md)  
  
-   [<span data-ttu-id="8aabe-113">대리자</span><span class="sxs-lookup"><span data-stu-id="8aabe-113">Delegates</span></span>](../../../csharp/programming-guide/delegates/index.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="8aabe-114">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="8aabe-114">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="8aabe-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8aabe-115">See Also</span></span>  
 [<span data-ttu-id="8aabe-116">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="8aabe-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="8aabe-117">C# 프로그램 내부</span><span class="sxs-lookup"><span data-stu-id="8aabe-117">Inside a C# Program</span></span>](../../../csharp/programming-guide/inside-a-program/index.md)  
 [<span data-ttu-id="8aabe-118">C# 참조</span><span class="sxs-lookup"><span data-stu-id="8aabe-118">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="8aabe-119">\<paveover>C# 샘플 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="8aabe-119">\<paveover>C# Sample Applications</span></span>](http://msdn.microsoft.com/en-us/9a9d7aaa-51d3-4224-b564-95409b0f3e15)
