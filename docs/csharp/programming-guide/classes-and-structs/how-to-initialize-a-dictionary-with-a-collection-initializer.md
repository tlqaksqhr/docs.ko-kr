---
title: "방법: 컬렉션 이니셜라이저를 사용하여 사전 초기화(C# 프로그래밍 가이드)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- collection initializers [C#], with Dictionary
ms.assetid: 25283922-f8ee-40dc-a639-fac30804ec71
caps.latest.revision: 10
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 41d6a9934daaa1274901e20de58cfd480c904bfa
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-initialize-a-dictionary-with-a-collection-initializer-c-programming-guide"></a><span data-ttu-id="cd38b-102">방법: 컬렉션 이니셜라이저를 사용하여 사전 초기화(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="cd38b-102">How to: Initialize a Dictionary with a Collection Initializer (C# Programming Guide)</span></span>
<span data-ttu-id="cd38b-103">@@@<xref:System.Collections.Generic.Dictionary`2> contains a collection of key/value pairs. Its <xref:System.Collections.Generic.Dictionary`2.Add*> 메서드는 키와 값에 대해 하나씩, 두 개의 매개 변수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="cd38b-103">A <xref:System.Collections.Generic.Dictionary`2> contains a collection of key/value pairs. Its <xref:System.Collections.Generic.Dictionary`2.Add*> method takes two parameters, one for the key and one for the value.</span></span> <span data-ttu-id="cd38b-104">@@@<xref:System.Collections.Generic.Dictionary`2>, or any collection whose `Add\` 메서드가 여러 매개 변수를 사용함)를 초기화하려면 다음 예제와 같이 각 매개 변수 집합을 중괄호로 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="cd38b-104">To initialize a <xref:System.Collections.Generic.Dictionary`2>, or any collection whose `Add\` method takes multiple parameters, enclose each set of parameters in braces as shown in the following example.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cd38b-105">예제</span><span class="sxs-lookup"><span data-stu-id="cd38b-105">Example</span></span>  
 <span data-ttu-id="cd38b-106">@@@다음 코드 예제에서 <xref:System.Collections.Generic.Dictionary`2> is initialized with instances of type `StudentName\`.</span><span class="sxs-lookup"><span data-stu-id="cd38b-106">In the following code example, a <xref:System.Collections.Generic.Dictionary`2> is initialized with instances of type `StudentName\`.</span></span>  
  
 <span data-ttu-id="cd38b-107">[!code-cs[csProgGuideLINQ#34](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-initialize-a-dictionary-with-a-collection-initializer_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="cd38b-107">[!code-cs[csProgGuideLINQ#34](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-initialize-a-dictionary-with-a-collection-initializer_1.cs)]</span></span>  
  
 <span data-ttu-id="cd38b-108">컬렉션의 각 요소에는 두 쌍의 중괄호가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd38b-108">Note the two pairs of braces in each element of the collection.</span></span> <span data-ttu-id="cd38b-109">안쪽 중괄호는 `StudentName`에 대한 개체 이니셜라이저를 묶고, 바깥쪽 중괄호는 `students`<xref:System.Collections.Generic.Dictionary\`2>에 추가할 키/값 쌍에 대한 이니셜라이저를 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="cd38b-109">The innermost braces enclose the object initializer for the `StudentName`, and the outermost braces enclose the initializer for the key/value pair that will be added to the `students`<xref:System.Collections.Generic.Dictionary\`2>.</span></span> <span data-ttu-id="cd38b-110">마지막으로, 사전에 대한 전체 컬렉션 이니셜라이저가 중괄호로 묶여 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd38b-110">Finally, the whole collection initializer for the dictionary is enclosed in braces.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="cd38b-111">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="cd38b-111">Compiling the Code</span></span>  
 <span data-ttu-id="cd38b-112">이 코드를 실행하려면 클래스를 복사하여 [!INCLUDE[vs_current_short](~/includes/vs-current-short-md.md)]에서 생성된 Visual C# 콘솔 응용 프로그램 프로젝트에 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="cd38b-112">To run this code, copy and paste the class into a Visual C# console application project that has been created in [!INCLUDE[vs_current_short](~/includes/vs-current-short-md.md)].</span></span> <span data-ttu-id="cd38b-113">기본적으로 이 프로젝트는 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 버전 3.5를 대상으로 하며, System.Core.dll에 대한 참조 및 System.Linq에 대한 using 지시문을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="cd38b-113">By default, this project targets version 3.5 of the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)], and it has a reference to System.Core.dll and a using directive for System.Linq.</span></span> <span data-ttu-id="cd38b-114">이러한 요구 사항 중 하나 이상이 프로젝트에 없는 경우 수동으로 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd38b-114">If one or more of these requirements are missing from the project, you can add them manually.</span></span>   
  
## <a name="see-also"></a><span data-ttu-id="cd38b-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cd38b-115">See Also</span></span>  
 <span data-ttu-id="cd38b-116">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="cd38b-116">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="cd38b-117">개체 이니셜라이저 및 컬렉션 이니셜라이저</span><span class="sxs-lookup"><span data-stu-id="cd38b-117">Object and Collection Initializers</span></span>](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md)

