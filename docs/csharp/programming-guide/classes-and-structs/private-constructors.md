---
title: "전용 생성자(C# 프로그래밍 가이드)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- C# language, private constructors
- private constructors [C#]
ms.assetid: 29eeaa7d-8d81-453c-94b9-0e2800172621
caps.latest.revision: 19
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
ms.openlocfilehash: 1ccd3db5f95e3a237bb37d9e09c34f415fcfd752
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="private-constructors-c-programming-guide"></a><span data-ttu-id="e57b4-102">전용 생성자(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="e57b4-102">Private Constructors (C# Programming Guide)</span></span>
<span data-ttu-id="e57b4-103">전용 생성자는 특수 인스턴스 생성자입니다.</span><span class="sxs-lookup"><span data-stu-id="e57b4-103">A private constructor is a special instance constructor.</span></span> <span data-ttu-id="e57b4-104">일반적으로 정적 멤버만 포함하는 클래스에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e57b4-104">It is generally used in classes that contain static members only.</span></span> <span data-ttu-id="e57b4-105">클래스에 하나 이상의 private 생성자가 있고 public 생성자가 없는 경우 중첩 클래스를 제외한 다른 클래스는 이 클래스의 인스턴스를 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e57b4-105">If a class has one or more private constructors and no public constructors, other classes (except nested classes) cannot create instances of this class.</span></span> <span data-ttu-id="e57b4-106">예:</span><span class="sxs-lookup"><span data-stu-id="e57b4-106">For example:</span></span>  
  
 <span data-ttu-id="e57b4-107">[!code-cs[csProgGuideObjects#11](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/private-constructors_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="e57b4-107">[!code-cs[csProgGuideObjects#11](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/private-constructors_1.cs)]</span></span>  
  
 <span data-ttu-id="e57b4-108">빈 생성자를 선언하면 기본 생성자가 자동으로 생성되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e57b4-108">The declaration of the empty constructor prevents the automatic generation of a default constructor.</span></span> <span data-ttu-id="e57b4-109">액세스 한정자를 생성자와 함께 사용하지 않는 경우 기본적으로 여전히 private입니다.</span><span class="sxs-lookup"><span data-stu-id="e57b4-109">Note that if you do not use an access modifier with the constructor it will still be private by default.</span></span> <span data-ttu-id="e57b4-110">그러나 일반적으로 [private](../../../csharp/language-reference/keywords/private.md) 한정자는 명시적으로 사용되어 클래스를 인스턴스화할 수 없음을 명확하게 합니다.</span><span class="sxs-lookup"><span data-stu-id="e57b4-110">However, the [private](../../../csharp/language-reference/keywords/private.md) modifier is usually used explicitly to make it clear that the class cannot be instantiated.</span></span>  
  
 <span data-ttu-id="e57b4-111">private 생성자는 <xref:System.Math> 클래스 등의 인스턴스 필드 또는 메서드가 없는 경우 또는 메서드를 호출하여 클래스 인스턴스를 가져오는 경우 클래스 인스턴스를 만들 수 없도록 하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e57b4-111">Private constructors are used to prevent creating instances of a class when there are no instance fields or methods, such as the <xref:System.Math> class, or when a method is called to obtain an instance of a class.</span></span> <span data-ttu-id="e57b4-112">클래스의 모든 메서드가 정적인 경우 전체 클래스를 정적 클래스로 만드는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e57b4-112">If all the methods in the class are static, consider making the complete class static.</span></span> <span data-ttu-id="e57b4-113">자세한 내용은 [정적 클래스 및 정적 클래스 멤버](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e57b4-113">For more information see [Static Classes and Static Class Members](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e57b4-114">예제</span><span class="sxs-lookup"><span data-stu-id="e57b4-114">Example</span></span>  
 <span data-ttu-id="e57b4-115">다음은 private 생성자를 사용하는 클래스의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="e57b4-115">The following is an example of a class using a private constructor.</span></span>  
  
 <span data-ttu-id="e57b4-116">[!code-cs[csProgGuideObjects#12](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/private-constructors_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="e57b4-116">[!code-cs[csProgGuideObjects#12](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/private-constructors_2.cs)]</span></span>  
  
 <span data-ttu-id="e57b4-117">예제에서 다음 문의 주석 처리를 제거하는 경우 보호 수준 때문에 생성자에 액세스할 수 없어 오류가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="e57b4-117">Notice that if you uncomment the following statement from the example, it will generate an error because the constructor is inaccessible because of its protection level:</span></span>  
  
 <span data-ttu-id="e57b4-118">[!code-cs[csProgGuideObjects#13](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/private-constructors_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="e57b4-118">[!code-cs[csProgGuideObjects#13](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/private-constructors_3.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="e57b4-119">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="e57b4-119">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e57b4-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e57b4-120">See Also</span></span>  
 <span data-ttu-id="e57b4-121">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="e57b4-121">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="e57b4-122">[클래스 및 구조체](../../../csharp/programming-guide/classes-and-structs/index.md) </span><span class="sxs-lookup"><span data-stu-id="e57b4-122">[Classes and Structs](../../../csharp/programming-guide/classes-and-structs/index.md) </span></span>  
 <span data-ttu-id="e57b4-123">[생성자](../../../csharp/programming-guide/classes-and-structs/constructors.md) </span><span class="sxs-lookup"><span data-stu-id="e57b4-123">[Constructors](../../../csharp/programming-guide/classes-and-structs/constructors.md) </span></span>  
 <span data-ttu-id="e57b4-124">[종료자](../../../csharp/programming-guide/classes-and-structs/destructors.md) </span><span class="sxs-lookup"><span data-stu-id="e57b4-124">[Finalizers](../../../csharp/programming-guide/classes-and-structs/destructors.md) </span></span>  
 <span data-ttu-id="e57b4-125">[private](../../../csharp/language-reference/keywords/private.md) </span><span class="sxs-lookup"><span data-stu-id="e57b4-125">[private](../../../csharp/language-reference/keywords/private.md) </span></span>  
 [<span data-ttu-id="e57b4-126">public</span><span class="sxs-lookup"><span data-stu-id="e57b4-126">public</span></span>](../../../csharp/language-reference/keywords/public.md)

