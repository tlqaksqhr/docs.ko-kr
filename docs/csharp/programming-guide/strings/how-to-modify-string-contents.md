---
title: "방법: 문자열 내용 수정(C# 프로그래밍 가이드)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- strings [C#], modifying
ms.assetid: b6c20bba-ce22-43d7-ad1b-5ce65f714055
caps.latest.revision: 16
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
ms.openlocfilehash: 114b6fdabd235d7e57947e77b672352e28aff11e
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-modify-string-contents-c-programming-guide"></a><span data-ttu-id="fb01a-102">방법: 문자열 내용 수정(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="fb01a-102">How to: Modify String Contents (C# Programming Guide)</span></span>
<span data-ttu-id="fb01a-103">문자열은 *변경할 수 없으므로*, 안전하지 않은 코드를 사용하지 않으면 문자열 개체가 생성된 후 개체 값을 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fb01a-103">Because strings are *immutable*, it is not possible (without using unsafe code) to modify the value of a string object after it has been created.</span></span> <span data-ttu-id="fb01a-104">그러나 문자열 값을 수정하고 그 결과를 새 문자열 개체에 저장하는 여러 가지 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb01a-104">However, there are many ways to modify the value of a string and store the result in a new string object.</span></span> <span data-ttu-id="fb01a-105"><xref:System.String?displayProperty=fullName> 클래스는 입력 문자열에서 작동하고 새 문자열 개체를 반환하는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="fb01a-105">The <xref:System.String?displayProperty=fullName> class provides methods that operate on an input string and return a new string object.</span></span> <span data-ttu-id="fb01a-106">대부분의 경우 원래 문자열이 포함된 변수에 새 개체를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb01a-106">In many cases, you can assign the new object to the variable that held the original string.</span></span> <span data-ttu-id="fb01a-107"><xref:System.Text.RegularExpressions.Regex?displayProperty=fullName> 클래스는 비슷한 방식으로 작동하는 추가 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="fb01a-107">The <xref:System.Text.RegularExpressions.Regex?displayProperty=fullName> class provides additional methods that work in a similar manner.</span></span> <span data-ttu-id="fb01a-108"><xref:System.Text.StringBuilder?displayProperty=fullName> 클래스는 “현재 위치”에서 수정할 수 있는 문자 버퍼를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="fb01a-108">The <xref:System.Text.StringBuilder?displayProperty=fullName> class provides a character buffer that you can modify "in-place."</span></span> <span data-ttu-id="fb01a-109"><xref:System.Text.StringBuilder.ToString%2A?displayProperty=fullName> 메서드를 호출하여 버퍼의 현재 내용을 포함하는 새 문자열 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fb01a-109">You call the <xref:System.Text.StringBuilder.ToString%2A?displayProperty=fullName> method to create a new string object that contains the current contents of the buffer.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fb01a-110">예제</span><span class="sxs-lookup"><span data-stu-id="fb01a-110">Example</span></span>  
 <span data-ttu-id="fb01a-111">다음 예제에서는 지정된 문자열의 부분 문자열을 바꾸거나 제거하는 다양한 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fb01a-111">The following example shows various ways to replace or remove substrings in a specified string.</span></span>  
  
 <span data-ttu-id="fb01a-112">[!code-cs[csProgGuideStrings#28](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-modify-string-contents_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="fb01a-112">[!code-cs[csProgGuideStrings#28](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-modify-string-contents_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="fb01a-113">예제</span><span class="sxs-lookup"><span data-stu-id="fb01a-113">Example</span></span>  
 <span data-ttu-id="fb01a-114">배열 표기법을 사용하여 문자열의 개별 문자에 액세스하려면 <xref:System.Text.StringBuilder> 개체를 사용할 수 있습니다. 이 개체는 `[]` 연산자를 오버로드하여 내부 문자 버퍼에 대한 액세스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="fb01a-114">To access the individual characters in a string by using array notation, you can use the <xref:System.Text.StringBuilder> object, which overloads the `[]` operator to provide access to its internal character buffer.</span></span> <span data-ttu-id="fb01a-115"><xref:System.String.ToCharArray%2A> 메서드를 사용하여 문자열을 문자 배열로 변환할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb01a-115">You can also convert the string to an array of chars by using the <xref:System.String.ToCharArray%2A> method.</span></span> <span data-ttu-id="fb01a-116">다음 예제에서는 `ToCharArray`를 사용하여 배열을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fb01a-116">The following example uses `ToCharArray` to create the array.</span></span> <span data-ttu-id="fb01a-117">이 배열의 일부 요소를 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="fb01a-117">Some elements of this array are then modified.</span></span> <span data-ttu-id="fb01a-118">그런 다음 문자 배열을 입력 매개 변수로 사용하는 문자열 생성자를 호출하여 새 문자열을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fb01a-118">A string constructor that takes a char array as an input parameter is then called to create a new string.</span></span>  
  
 <span data-ttu-id="fb01a-119">[!code-cs[csProgGuideStrings#24](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-modify-string-contents_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="fb01a-119">[!code-cs[csProgGuideStrings#24](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-modify-string-contents_2.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="fb01a-120">예제</span><span class="sxs-lookup"><span data-stu-id="fb01a-120">Example</span></span>  
 <span data-ttu-id="fb01a-121">다음 예제는 C 스타일 문자 배열과 비슷한 방식으로 안전하지 않은 코드를 사용하여 현재 위치에서 문자열을 수정하려는 매우 드문 경우를 위해 제공되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fb01a-121">The following example is provided for those very rare situations in which you may want to modify a string in-place by using unsafe code in a manner similar to C-style char arrays.</span></span> <span data-ttu-id="fb01a-122">이 예제에서는 fixed 키워드를 사용하여 “현재 위치”에서 개별 문자에 액세스하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fb01a-122">The example shows how to access the individual characters "in-place" by using the fixed keyword.</span></span> <span data-ttu-id="fb01a-123">또한 문자열에 대한 안전하지 않은 작업의 가능한 부작용 중 하나를 보여 줍니다. 이 부작용은 C# 컴파일러가 문자열을 내부적으로 저장(intern)하는 방식에서 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="fb01a-123">It also demonstrates one possible side effect of unsafe operations on strings that results from the way that the C# compiler stores (interns) strings internally.</span></span> <span data-ttu-id="fb01a-124">일반적으로 이 방식은 반드시 필요한 경우에만 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb01a-124">In general, you should not use this technique unless it is absolutely necessary.</span></span>  
  
 <span data-ttu-id="fb01a-125">[!code-cs[csProgGuideStrings#29](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-modify-string-contents_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="fb01a-125">[!code-cs[csProgGuideStrings#29](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-modify-string-contents_3.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb01a-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fb01a-126">See Also</span></span>  
 <span data-ttu-id="fb01a-127">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="fb01a-127">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="fb01a-128">문자열</span><span class="sxs-lookup"><span data-stu-id="fb01a-128">Strings</span></span>](../../../csharp/programming-guide/strings/index.md)

