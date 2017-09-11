---
title: "액세스 한정자(C# 프로그래밍 가이드)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- C# Language, access modifiers
- access modifiers [C#], about
ms.assetid: 6e81ee82-224f-4a12-9baf-a0dca2656c5b
caps.latest.revision: 32
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
ms.openlocfilehash: 38b259b4d85d54467cd15cd49e5987f6198e8d99
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="access-modifiers-c-programming-guide"></a><span data-ttu-id="3ff09-102">액세스 한정자(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="3ff09-102">Access Modifiers (C# Programming Guide)</span></span>
<span data-ttu-id="3ff09-103">모든 형식과 형식 멤버에는 사용 중인 어셈블리나 기타 어셈블리의 다른 코드에서 사용될 수 있는지 여부를 제어하는 액세스 가능성 수준이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ff09-103">All types and type members have an accessibility level, which controls whether they can be used from other code in your assembly or other assemblies.</span></span> <span data-ttu-id="3ff09-104">다음 액세스 한정자를 사용하여 형식 또는 멤버를 선언할 때 해당 항목의 액세스 가능성을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ff09-104">You can use the following access modifiers to specify the accessibility of a type or member when you declare it:</span></span>  
  
 [<span data-ttu-id="3ff09-105">public</span><span class="sxs-lookup"><span data-stu-id="3ff09-105">public</span></span>](../../../csharp/language-reference/keywords/public.md)  
 <span data-ttu-id="3ff09-106">동일한 어셈블리의 다른 코드나 해당 어셈블리를 참조하는 다른 어셈블리의 코드에서 형식이나 멤버에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ff09-106">The type or member can be accessed by any other code in the same assembly or another assembly that references it.</span></span>  
  
 [<span data-ttu-id="3ff09-107">private</span><span class="sxs-lookup"><span data-stu-id="3ff09-107">private</span></span>](../../../csharp/language-reference/keywords/private.md)  
 <span data-ttu-id="3ff09-108">같은 클래스 또는 구조체의 코드에서만 형식 또는 멤버에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ff09-108">The type or member can be accessed only by code in the same class or struct.</span></span>  
  
 [<span data-ttu-id="3ff09-109">protected</span><span class="sxs-lookup"><span data-stu-id="3ff09-109">protected</span></span>](../../../csharp/language-reference/keywords/protected.md)  
 <span data-ttu-id="3ff09-110">같은 클래스나 구조체 또는 해당 클래스에서 파생 클래스의 코드에서만 형식 또는 멤버에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ff09-110">The type or member can be accessed only by code in the same class or struct, or in a class that is derived from that class.</span></span>  
  
 [<span data-ttu-id="3ff09-111">internal</span><span class="sxs-lookup"><span data-stu-id="3ff09-111">internal</span></span>](../../../csharp/language-reference/keywords/internal.md)  
 <span data-ttu-id="3ff09-112">동일한 어셈블리의 코드에서는 형식이나 멤버에 액세스할 수 있지만 다른 어셈블리의 코드에서는 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3ff09-112">The type or member can be accessed by any code in the same assembly, but not from another assembly.</span></span>  
  
 `protected internal`  
 <span data-ttu-id="3ff09-113">형식이나 멤버가 선언된 어셈블리의 모든 코드에서 또는 다른 어셈블리의 파생 클래스 내에서 형식 또는 멤버에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ff09-113">The type or member can be accessed by any code in the assembly in which it is declared, or from within a derived class in another assembly.</span></span> <span data-ttu-id="3ff09-114">다른 어셈블리로부터의 액세스는 반드시 protected internal 요소가 선언된 클래스에서 파생한 클래스 선언 내에서 발생해야 하며, 반드시 이렇게 파생된 클래스 형식의 인스턴스를 통해서 발생해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ff09-114">Access from another assembly must take place within a class declaration that derives from the class in which the protected internal element is declared, and it must take place through an instance of the derived class type.</span></span>  
  
 <span data-ttu-id="3ff09-115">다음 예제에서는 형식 및 멤버에 대해 액세스 한정자를 지정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3ff09-115">The following examples demonstrate how to specify access modifiers on a type and member:</span></span>  
  
 <span data-ttu-id="3ff09-116">[!code-cs[csProgGuideObjects#72](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/access-modifiers_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="3ff09-116">[!code-cs[csProgGuideObjects#72](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/access-modifiers_1.cs)]</span></span>  
  
 <span data-ttu-id="3ff09-117">모든 액세스 한정자를 모든 컨텍스트의 모든 형식이나 멤버에서 사용할 수 있는 것은 아니며, 경우에 따라 형식 멤버의 액세스 가능성이 포함하는 형식의 액세스 가능성에 의해 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="3ff09-117">Not all access modifiers can be used by all types or members in all contexts, and in some cases the accessibility of a type member is constrained by the accessibility of its containing type.</span></span> <span data-ttu-id="3ff09-118">다음 섹션에서는 액세스 가능성을 자세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3ff09-118">The following sections provide more details about accessibility.</span></span>  
  
## <a name="class-and-struct-accessibility"></a><span data-ttu-id="3ff09-119">클래스 및 구조체 액세스 가능성</span><span class="sxs-lookup"><span data-stu-id="3ff09-119">Class and Struct Accessibility</span></span>  
 <span data-ttu-id="3ff09-120">네임스페이스 내에서 직접 선언된(다른 클래스 또는 구조체 내에 중첩되지 않은) 클래스와 구조체는 public 또는 internal 중 하나일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ff09-120">Classes and structs that are declared directly within a namespace (in other words, that are not nested within other classes or structs) can be either public or internal.</span></span> <span data-ttu-id="3ff09-121">액세스 한정자가 지정되지 않은 경우 internal이 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="3ff09-121">Internal is the default if no access modifier is specified.</span></span>  
  
 <span data-ttu-id="3ff09-122">중첩 클래스 및 구조체를 포함한 구조체 멤버는 public, internal 또는 private으로 선언될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ff09-122">Struct members, including nested classes and structs, can be declared as public, internal, or private.</span></span> <span data-ttu-id="3ff09-123">중첩 클래스 및 구조체를 포함한 클래스 멤버는 public, protected internal, protected, internal 또는 private으로 선언될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ff09-123">Class members, including nested classes and structs, can be public, protected internal, protected, internal, or private.</span></span> <span data-ttu-id="3ff09-124">중첩 클래스 및 구조체를 포함한 클래스 멤버와 구조체 멤버의 액세스 수준은 기본적으로 private입니다.</span><span class="sxs-lookup"><span data-stu-id="3ff09-124">The access level for class members and struct members, including nested classes and structs, is private by default.</span></span> <span data-ttu-id="3ff09-125">포함하는 형식 외부에서는 private 중첩 형식에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3ff09-125">Private nested types are not accessible from outside the containing type.</span></span>  
  
 <span data-ttu-id="3ff09-126">파생 클래스는 기본 형식보다 큰 액세스 가능성을 가질 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3ff09-126">Derived classes cannot have greater accessibility than their base types.</span></span> <span data-ttu-id="3ff09-127">즉, public 클래스 `B`는 internal 클래스 `A`에서 파생될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3ff09-127">In other words, you cannot have a public class `B` that derives from an internal class `A`.</span></span> <span data-ttu-id="3ff09-128">파생될 수 있다면 파생 클래스에서 `A`의 모든 protected 또는 internal 멤버에 액세스할 수 있기 때문에 결과적으로 `A`가 public으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="3ff09-128">If this were allowed, it would have the effect of making `A` public, because all protected or internal members of `A` are accessible from the derived class.</span></span>  
  
 <span data-ttu-id="3ff09-129">다른 특정 어셈블리에서는 InternalsVisibleToAttribute를 사용하여 internal 형식에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ff09-129">You can enable specific other assemblies to access your internal types by using the InternalsVisibleToAttribute.</span></span> <span data-ttu-id="3ff09-130">자세한 내용은 [Friend Assemblies](http://msdn.microsoft.com/library/df0c70ea-2c2a-4bdc-9526-df951ad2d055)(Friend 어셈블리)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3ff09-130">For more information, see [Friend Assemblies](http://msdn.microsoft.com/library/df0c70ea-2c2a-4bdc-9526-df951ad2d055).</span></span>  
  
## <a name="class-and-struct-member-accessibility"></a><span data-ttu-id="3ff09-131">클래스 및 구조체 멤버 액세스 가능성</span><span class="sxs-lookup"><span data-stu-id="3ff09-131">Class and Struct Member Accessibility</span></span>  
 <span data-ttu-id="3ff09-132">중첩 클래스 및 구조체를 포함한 구조체 멤버는 5가지 액세스 형식으로 선언될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ff09-132">Class members (including nested classes and structs) can be declared with any of the five types of access.</span></span> <span data-ttu-id="3ff09-133">구조체는 상속을 지원하지 않으므로 구조체 멤버는 protected로 선언될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3ff09-133">Struct members cannot be declared as protected because structs do not support inheritance.</span></span>  
  
 <span data-ttu-id="3ff09-134">일반적으로 멤버의 액세스 가능성은 멤버를 포함하는 형식의 액세스 가능성보다 크지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3ff09-134">Normally, the accessibility of a member is not greater than the accessibility of the type that contains it.</span></span> <span data-ttu-id="3ff09-135">그러나 멤버가 인터페이스 메서드를 구현하거나 public 기본 클래스에 정의된 가상 메서드를 재정의하는 경우에는 어셈블리 외부에서 internal 클래스의 public 멤버에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ff09-135">However, a public member of an internal class might be accessible from outside the assembly if the member implements interface methods or overrides virtual methods that are defined in a public base class.</span></span>  
  
 <span data-ttu-id="3ff09-136">필드, 속성 또는 이벤트인 멤버의 형식은 최소한 멤버 자체만큼 액세스할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ff09-136">The type of any member that is a field, property, or event must be at least as accessible as the member itself.</span></span> <span data-ttu-id="3ff09-137">마찬가지로 메서드, 인덱서 또는 대리자인 멤버의 반환 형식과 매개 변수 형식은 최소한 멤버 자체만큼 액세스할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ff09-137">Similarly, the return type and the parameter types of any member that is a method, indexer, or delegate must be at least as accessible as the member itself.</span></span> <span data-ttu-id="3ff09-138">예를 들어 `C` 클래스도 public인 경우에만 public 메서드 `M`이 `C` 클래스를 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ff09-138">For example, you cannot have a public method `M` that returns a class `C` unless `C` is also public.</span></span> <span data-ttu-id="3ff09-139">마찬가지로 `A` 형식이 private으로 선언되면 `A` 형식에는 protected 속성은 있을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3ff09-139">Likewise, you cannot have a protected property of type `A` if `A` is declared as private.</span></span>  
  
 <span data-ttu-id="3ff09-140">사용자 정의 연산자는 public으로 선언되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ff09-140">User-defined operators must always be declared as public.</span></span> <span data-ttu-id="3ff09-141">자세한 내용은 [연산자(C# 참조)](../../../csharp/language-reference/keywords/operator.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3ff09-141">For more information, see [operator (C# Reference)](../../../csharp/language-reference/keywords/operator.md).</span></span>  
  
 <span data-ttu-id="3ff09-142">종료자에는 접근성 한정자를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3ff09-142">Finalizers cannot have accessibility modifiers.</span></span>  
  
 <span data-ttu-id="3ff09-143">클래스 또는 구조체 멤버의 액세스 수준을 설정하려면 다음 예제와 같이 멤버 선언에 해당 키워드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="3ff09-143">To set the access level for a class or struct member, add the appropriate keyword to the member declaration, as shown in the following example.</span></span>  
  
 <span data-ttu-id="3ff09-144">[!code-cs[csProgGuideObjects#73](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/access-modifiers_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="3ff09-144">[!code-cs[csProgGuideObjects#73](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/access-modifiers_2.cs)]</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3ff09-145">protected internal 액세스 가능성 수준은 protected 및 internal이 아니라 protected 또는 internal을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="3ff09-145">The protected internal accessibility level means protected OR internal, not protected AND internal.</span></span> <span data-ttu-id="3ff09-146">즉, 파생 클래스를 포함하여 같은 어셈블리의 모든 클래스에서 protected internal 멤버에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ff09-146">In other words, a protected internal member can be accessed from any class in the same assembly, including derived classes.</span></span> <span data-ttu-id="3ff09-147">액세스 가능성을 같은 어셈블리 파생 클래스로만 제한하려면 클래스 자체를 internal로 선언하고 해당 멤버를 protected로 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="3ff09-147">To limit accessibility to only derived classes in the same assembly, declare the class itself internal, and declare its members as protected.</span></span>  
  
## <a name="other-types"></a><span data-ttu-id="3ff09-148">기타 형식</span><span class="sxs-lookup"><span data-stu-id="3ff09-148">Other Types</span></span>  
 <span data-ttu-id="3ff09-149">네임스페이스 내에서 직접 선언된 인터페이스는 public 또는 internal로 선언될 수 있고 클래스 및 구조체처럼 인터페이스는 기본적으로 internal 액세스로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="3ff09-149">Interfaces declared directly within a namespace can be declared as public or internal and, just like classes and structs, interfaces default to internal access.</span></span> <span data-ttu-id="3ff09-150">인터페이스는 다른 형식이 클래스나 구조체에 액세스하는 데 사용되므로 인터페이스 멤버는 항상 public입니다.</span><span class="sxs-lookup"><span data-stu-id="3ff09-150">Interface members are always public because the purpose of an interface is to enable other types to access a class or struct.</span></span> <span data-ttu-id="3ff09-151">액세스 한정자는 인터페이스 멤버에 적용될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3ff09-151">No access modifiers can be applied to interface members.</span></span>  
  
 <span data-ttu-id="3ff09-152">열거형 멤버는 항상 public이고 액세스 한정자가 적용될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3ff09-152">Enumeration members are always public, and no access modifiers can be applied.</span></span>  
  
 <span data-ttu-id="3ff09-153">대리자는 클래스 및 구조체처럼 동작합니다.</span><span class="sxs-lookup"><span data-stu-id="3ff09-153">Delegates behave like classes and structs.</span></span> <span data-ttu-id="3ff09-154">기본적으로 대리자는 네임스페이스 내에서 직접 선언될 경우 internal 액세스를 가지고 중첩될 경우 private 액세스를 가집니다.</span><span class="sxs-lookup"><span data-stu-id="3ff09-154">By default, they have internal access when declared directly within a namespace, and private access when nested.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="3ff09-155">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="3ff09-155">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3ff09-156">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3ff09-156">See Also</span></span>  
 <span data-ttu-id="3ff09-157">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="3ff09-157">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="3ff09-158">[클래스 및 구조체](../../../csharp/programming-guide/classes-and-structs/index.md) </span><span class="sxs-lookup"><span data-stu-id="3ff09-158">[Classes and Structs](../../../csharp/programming-guide/classes-and-structs/index.md) </span></span>  
 <span data-ttu-id="3ff09-159">[인터페이스](../../../csharp/programming-guide/interfaces/index.md) </span><span class="sxs-lookup"><span data-stu-id="3ff09-159">[Interfaces](../../../csharp/programming-guide/interfaces/index.md) </span></span>  
 <span data-ttu-id="3ff09-160">[private](../../../csharp/language-reference/keywords/private.md) </span><span class="sxs-lookup"><span data-stu-id="3ff09-160">[private](../../../csharp/language-reference/keywords/private.md) </span></span>  
 <span data-ttu-id="3ff09-161">[public](../../../csharp/language-reference/keywords/public.md) </span><span class="sxs-lookup"><span data-stu-id="3ff09-161">[public](../../../csharp/language-reference/keywords/public.md) </span></span>  
 <span data-ttu-id="3ff09-162">[internal](../../../csharp/language-reference/keywords/internal.md) </span><span class="sxs-lookup"><span data-stu-id="3ff09-162">[internal](../../../csharp/language-reference/keywords/internal.md) </span></span>  
 <span data-ttu-id="3ff09-163">[protected](../../../csharp/language-reference/keywords/protected.md) </span><span class="sxs-lookup"><span data-stu-id="3ff09-163">[protected](../../../csharp/language-reference/keywords/protected.md) </span></span>  
 <span data-ttu-id="3ff09-164">[class](../../../csharp/language-reference/keywords/class.md) </span><span class="sxs-lookup"><span data-stu-id="3ff09-164">[class](../../../csharp/language-reference/keywords/class.md) </span></span>  
 <span data-ttu-id="3ff09-165">[struct](../../../csharp/language-reference/keywords/struct.md) </span><span class="sxs-lookup"><span data-stu-id="3ff09-165">[struct](../../../csharp/language-reference/keywords/struct.md) </span></span>  
 [<span data-ttu-id="3ff09-166">interface</span><span class="sxs-lookup"><span data-stu-id="3ff09-166">interface</span></span>](../../../csharp/language-reference/keywords/interface.md)

