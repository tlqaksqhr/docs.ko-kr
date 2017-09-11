---
title: "구조체(C# 프로그래밍 가이드)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- C# language, structs
- structs [C#]
ms.assetid: b7cf4ff2-0eb7-4e5c-93d5-b2196b4f5d89
caps.latest.revision: 31
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
ms.openlocfilehash: ce12f402c0748ea6729c82e3f188c0a58f63d628
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="structs-c-programming-guide"></a><span data-ttu-id="b63a4-102">구조체(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="b63a4-102">Structs (C# Programming Guide)</span></span>
<span data-ttu-id="b63a4-103">구조체는 [struct](../../../csharp/language-reference/keywords/struct.md) 키워드를 사용하여 정의합니다. 예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b63a4-103">Structs are defined by using the [struct](../../../csharp/language-reference/keywords/struct.md) keyword, for example:</span></span>  
  
 <span data-ttu-id="b63a4-104">[!code-cs[csProgGuideObjects#39](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/structs_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="b63a4-104">[!code-cs[csProgGuideObjects#39](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/structs_1.cs)]</span></span>  
  
 <span data-ttu-id="b63a4-105">구조체가 클래스보다 더 제한적이지만 구조체는 클래스와 동일한 구문을 대부분 공유합니다.</span><span class="sxs-lookup"><span data-stu-id="b63a4-105">Structs share most of the same syntax as classes, although structs are more limited than classes:</span></span>  
  
-   <span data-ttu-id="b63a4-106">구조체 선언 내에서 필드가 const 또는 static으로 선언된 경우가 아니면 필드를 초기화할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b63a4-106">Within a struct declaration, fields cannot be initialized unless they are declared as const or static.</span></span>  
  
-   <span data-ttu-id="b63a4-107">구조체는 기본 생성자(매개 변수가 없는 생성자) 또는 종료자를 선언할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b63a4-107">A struct cannot declare a default constructor (a constructor without parameters) or a finalizer.</span></span>  
  
-   <span data-ttu-id="b63a4-108">할당 시 구조체가 복사됩니다.</span><span class="sxs-lookup"><span data-stu-id="b63a4-108">Structs are copied on assignment.</span></span> <span data-ttu-id="b63a4-109">구조체를 새 변수에 할당하면 모든 데이터가 복사되고, 새 복사본을 수정해도 원래 복사본의 데이터는 변경되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b63a4-109">When a struct is assigned to a new variable, all the data is copied, and any modification to the new copy does not change the data for the original copy.</span></span> <span data-ttu-id="b63a4-110">Dictionary\<string, myStruct> 등의 값 형식 컬렉션으로 작업하는 경우 이 점을 명심해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b63a4-110">This is important to remember when working with collections of value types such as Dictionary\<string, myStruct>.</span></span>  
  
-   <span data-ttu-id="b63a4-111">구조체는 값 형식이고 클래스는 참조 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="b63a4-111">Structs are value types and classes are reference types.</span></span>  
  
-   <span data-ttu-id="b63a4-112">클래스와 달리 구조체는 `new` 연산자를 사용하지 않고 인스턴스화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b63a4-112">Unlike classes, structs can be instantiated without using a `new` operator.</span></span>  
  
-   <span data-ttu-id="b63a4-113">구조체는 매개 변수가 있는 생성자를 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b63a4-113">Structs can declare constructors that have parameters.</span></span>  
  
-   <span data-ttu-id="b63a4-114">구조체는 다른 구조체 또는 클래스에서 상속될 수 없으며, 클래스의 기본 클래스가 될 수도 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b63a4-114">A struct cannot inherit from another struct or class, and it cannot be the base of a class.</span></span> <span data-ttu-id="b63a4-115">모든 구조체는 `System.Object`에서 상속하는 `System.ValueType`에서 직접 상속합니다.</span><span class="sxs-lookup"><span data-stu-id="b63a4-115">All structs inherit directly from `System.ValueType`, which inherits from `System.Object`.</span></span>  
  
-   <span data-ttu-id="b63a4-116">구조체는 인터페이스를 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b63a4-116">A struct can implement interfaces.</span></span>  
  
-   <span data-ttu-id="b63a4-117">구조체는 nullable 형식으로 사용할 수 있으며 null 값을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b63a4-117">A struct can be used as a nullable type and can be assigned a null value.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="b63a4-118">관련 단원</span><span class="sxs-lookup"><span data-stu-id="b63a4-118">Related Sections</span></span>  
 <span data-ttu-id="b63a4-119">추가 정보</span><span class="sxs-lookup"><span data-stu-id="b63a4-119">For more information:</span></span>  
  
-   [<span data-ttu-id="b63a4-120">구조체 사용</span><span class="sxs-lookup"><span data-stu-id="b63a4-120">Using Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/using-structs.md)  
  
-   [<span data-ttu-id="b63a4-121">생성자</span><span class="sxs-lookup"><span data-stu-id="b63a4-121">Constructors</span></span>](../../../csharp/programming-guide/classes-and-structs/constructors.md)  
  
-   [<span data-ttu-id="b63a4-122">Nullable 형식</span><span class="sxs-lookup"><span data-stu-id="b63a4-122">Nullable Types</span></span>](../../../csharp/programming-guide/nullable-types/index.md)  
  
-   [<span data-ttu-id="b63a4-123">방법: 메서드에 구조체를 전달하는 것과 클래스 참조를 전달하는 것의 차이점 이해</span><span class="sxs-lookup"><span data-stu-id="b63a4-123">How to: Know the Difference Between Passing a Struct and Passing a Class Reference to a Method</span></span>](../../../csharp/programming-guide/classes-and-structs/how-to-know-the-difference-passing-a-struct-and-passing-a-class-to-a-method.md)  
  
-   [<span data-ttu-id="b63a4-124">방법: 구조체 간의 사용자 정의 변환 구현</span><span class="sxs-lookup"><span data-stu-id="b63a4-124">How to: Implement User-Defined Conversions Between Structs</span></span>](../../../csharp/programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)  
  
## <a name="see-also"></a><span data-ttu-id="b63a4-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b63a4-125">See Also</span></span>  
 <span data-ttu-id="b63a4-126">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="b63a4-126">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="b63a4-127">[클래스 및 구조체](../../../csharp/programming-guide/classes-and-structs/index.md) </span><span class="sxs-lookup"><span data-stu-id="b63a4-127">[Classes and Structs](../../../csharp/programming-guide/classes-and-structs/index.md) </span></span>  
 [<span data-ttu-id="b63a4-128">클래스</span><span class="sxs-lookup"><span data-stu-id="b63a4-128">Classes</span></span>](../../../csharp/programming-guide/classes-and-structs/classes.md)

