---
title: "@(C# 참조)"
ms.date: 2017-02-09
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '@_CSharpKeyword'
- '@'
dev_langs:
- CSharp
helpviewer_keywords:
- '@ special character [C#]'
- '@ language element [C#]'
ms.assetid: 89bc7e53-85f5-478a-866d-1cca003c4e8c
author: rpetrusha
ms.author: ronpet
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
ms.openlocfilehash: 08e3da6aaeee037d7272ea8cddc4382a436b683b
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="-c-reference"></a><span data-ttu-id="0ca20-102">@(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="0ca20-102">@ (C# Reference)</span></span>

<span data-ttu-id="0ca20-103">`@` 특수 문자는 축자 식별자로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ca20-103">The `@` special character serves as a verbatim identifier.</span></span> <span data-ttu-id="0ca20-104">다음과 같은 방법으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ca20-104">It can be used in the following ways:</span></span>

1. <span data-ttu-id="0ca20-105">C# 키워드를 식별자로 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="0ca20-105">To enable C# keywords to be used as identifiers.</span></span> <span data-ttu-id="0ca20-106">`@` 문자는 컴파일러가 C# 키워드가 아닌 식별자로 해석할 코드 요소의 접두사입니다.</span><span class="sxs-lookup"><span data-stu-id="0ca20-106">The `@` character prefixes a code element that the compiler is to interpret as an identifier rather than a C# keyword.</span></span> <span data-ttu-id="0ca20-107">다음 예제에서는 `@` 문자를 사용하여 `for` 루프에서 사용되는 `for`라는 이름의 식별자를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="0ca20-107">The following example uses the `@` character to define an identifier named `for` that it uses in a `for` loop.</span></span>

   <span data-ttu-id="0ca20-108">[!code-cs[verbatim1](../../../../samples/snippets/csharp/language-reference/keywords/verbatim1.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="0ca20-108">[!code-cs[verbatim1](../../../../samples/snippets/csharp/language-reference/keywords/verbatim1.cs#1)]</span></span>

1. <span data-ttu-id="0ca20-109">문자열 리터럴이 축자로 해석될 것임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0ca20-109">To indicate that a string literal is to be interpreted verbatim.</span></span> <span data-ttu-id="0ca20-110">이 인스턴스의 `@` 문자는 *축자 문자 문자열*을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="0ca20-110">The `@` character in this instance defines a *verbatim string literal*.</span></span> <span data-ttu-id="0ca20-111">단순 이스케이프 시퀀스(예: 백슬래시에 `"\\"`), 16진수 이스케이프 시퀀스(예: 대문자 A에 `"\x0041"`), 유니코드 이스케이프 시퀀스(예: 대문자 A에 `"\u0041"`)는 문자 그대로 해석됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ca20-111">Simple escape sequences (such as `"\\"` for a backslash), hexadecimal escape sequences (such as `"\x0041"` for an uppercase A, and Unicode escape sequences, such as `"\u0041"` for an uppercase A, are interpreted literally.</span></span> <span data-ttu-id="0ca20-112">인용 부호 이스케이프 시퀀스(`""`)만 문자 그대로 해석되지 않고, 단일 작은따옴표를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="0ca20-112">Only a quote escape sequence (`""`) is not interpreted literally; it produces a single quotation mark.</span></span> <span data-ttu-id="0ca20-113">다음 예제에서는 각각 일반 문자열 리터럴 및 축자 문자열 리터럴을 사용하여 두 개의 동일한 파일 경로를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="0ca20-113">The following example defines two identical file paths, one by using a regular string literal and the other by using a verbatim string literal.</span></span> <span data-ttu-id="0ca20-114">이것은 축자 문자열 리터럴의 일반적인 사용법 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="0ca20-114">This is one of the more common uses of verbatim string literals.</span></span>

   <span data-ttu-id="0ca20-115">[!code-cs[verbatim2](../../../../samples/snippets/csharp/language-reference/keywords/verbatim1.cs#2)]</span><span class="sxs-lookup"><span data-stu-id="0ca20-115">[!code-cs[verbatim2](../../../../samples/snippets/csharp/language-reference/keywords/verbatim1.cs#2)]</span></span>

   <span data-ttu-id="0ca20-116">다음 예제에서는 동일한 문자 시퀀스를 포함한 일반 문자열 리터럴 및 축자 문자열 리터럴의 효과를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0ca20-116">The following example illustrates the effect of defining a regular string literal and a verbatim string literal that contain identical character sequences.</span></span>

   <span data-ttu-id="0ca20-117">[!code-cs[verbatim3](../../../../samples/snippets/csharp/language-reference/keywords/verbatim1.cs#3)]</span><span class="sxs-lookup"><span data-stu-id="0ca20-117">[!code-cs[verbatim3](../../../../samples/snippets/csharp/language-reference/keywords/verbatim1.cs#3)]</span></span>

1. <span data-ttu-id="0ca20-118">이름이 서로 충돌하는 경우 특성 간에 구분하기 위해 컴파일러를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0ca20-118">To enable the compiler to distinguish between attributes in cases of a naming conflict.</span></span> <span data-ttu-id="0ca20-119">특성은 @System.Attribute 에서 파생되는 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="0ca20-119">An attribute is a type that derives from @System.Attribute.</span></span> <span data-ttu-id="0ca20-120">컴파일러는 이 규칙을 적용하지 않지만, 형식 이름에는 일반적으로 **Attribute** 접미사가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ca20-120">Its type name typically includes the suffix **Attribute**, although the compiler does not enforce this convention.</span></span> <span data-ttu-id="0ca20-121">전체 이름(예: `[InfoAttribute]`) 또는 약식 이름(예: `[Info]`)으로 코드에서 특성을 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ca20-121">The attribute can then be referenced in code either by its full type name (for example, `[InfoAttribute]` or its shortened name (for example, `[Info]`).</span></span> <span data-ttu-id="0ca20-122">그러나 두 개의 약식 특성 유형 이름이 동일하고 한 유형 이름에만 **Attribute** 접미사가 포함된 경우 이름 충돌이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="0ca20-122">However, a naming conflict occurs if two shortened attribute type names are identical, and one type name includes the **Attribute** suffix but the other does not.</span></span> <span data-ttu-id="0ca20-123">다음 예에서는 컴파일러가 `Info` 및 `InfoAttribute` 특성 중 무엇을 `Main` 메서드에 적용할지 결정할 수 없으므로 코드가 컴파일되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0ca20-123">For example, the following code fails to compile because the compiler cannot determine whether the `Info` or `InfoAttribute` attribute is applied to the `Main` method.</span></span>

   ```csharp
   using System;

   [AttributeUsage(AttributeTargets.Class)]
   public class Info : Attribute
   {
      private string information;
      
      public Info(string info)
      {
          information = info;
      }
   }

   [AttributeUsage(AttributeTargets.Method)]
   public class InfoAttribute : Attribute
   {
      private string information;
      
      public InfoAttribute(string info)
      {
          information = info;
      }
   }

   [Info("A simple executable.")]
   public class Example
   {
      [InfoAttribute("The entry point.")]
      public static void Main()
      {
      }
   }
   ```  

   <span data-ttu-id="0ca20-124">축자 식별자를 사용하여 `Info` 특성을 식별하는 경우에는 성공적으로 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ca20-124">If the verbatim identifier is used to identify the `Info` attribute, the example compiles successfully.</span></span>

   <span data-ttu-id="0ca20-125">[!code-cs[verbatim4](../../../../samples/snippets/csharp/language-reference/keywords/verbatim4.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="0ca20-125">[!code-cs[verbatim4](../../../../samples/snippets/csharp/language-reference/keywords/verbatim4.cs#1)]</span></span>

## <a name="see-also"></a><span data-ttu-id="0ca20-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0ca20-126">See Also</span></span>  
 <span data-ttu-id="0ca20-127">[C# 참조](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="0ca20-127">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="0ca20-128">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="0ca20-128">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="0ca20-129">C# 특수 문자</span><span class="sxs-lookup"><span data-stu-id="0ca20-129">C# Special Characters</span></span>](../../../csharp/language-reference/tokens/index.md)

