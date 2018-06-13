---
title: '방법: Nullable 형식 식별(C# 프로그래밍 가이드)'
ms.date: 07/20/2015
helpviewer_keywords:
- nullable types [C#], identifying
ms.assetid: d4b67ee2-66e8-40c1-ae9d-545d32c71387
ms.openlocfilehash: f3ac4ebd77fc92a133eb326919d5ba55264ced97
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33333185"
---
# <a name="how-to-identify-a-nullable-type-c-programming-guide"></a><span data-ttu-id="60764-102">방법: Nullable 형식 식별(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="60764-102">How to: Identify a Nullable Type (C# Programming Guide)</span></span>
<span data-ttu-id="60764-103">C# [typeof](../../../csharp/language-reference/keywords/typeof.md) 연산자를 사용하여 Nullable 형식을 나타내는 <xref:System.Type> 개체를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60764-103">You can use the C# [typeof](../../../csharp/language-reference/keywords/typeof.md) operator to create a <xref:System.Type> object that represents a Nullable type:</span></span>  
  
```  
System.Type type = typeof(int?);  
```  
  
 <span data-ttu-id="60764-104"><xref:System.Reflection> 네임스페이스의 클래스와 메서드를 사용하여 Nullable 형식을 나타내는 <xref:System.Type> 개체를 생성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60764-104">You can also use the classes and methods of the <xref:System.Reflection> namespace to generate <xref:System.Type> objects that represent Nullable types.</span></span> <span data-ttu-id="60764-105">그러나 <xref:System.Object.GetType%2A> 메서드 또는 `is` 연산자를 사용하여 런타임에 Nullable 변수에서 형식 정보를 가져오려고 하면 그 결과로 Nullable 형식 자체가 아니라 내부 형식을 나타내는 <xref:System.Type> 개체가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="60764-105">However, if you try to obtain type information from Nullable variables at runtime by using the <xref:System.Object.GetType%2A> method or the `is` operator, the result is a <xref:System.Type> object that represents the underlying type, not the Nullable type itself.</span></span>  
  
 <span data-ttu-id="60764-106">Nullable 형식에서 `GetType`을 호출하면 형식이 <xref:System.Object>로 암시적으로 변환될 때 boxing 작업이 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="60764-106">Calling `GetType` on a Nullable type causes a boxing operation to be performed when the type is implicitly converted to <xref:System.Object>.</span></span> <span data-ttu-id="60764-107">따라서 <xref:System.Object.GetType%2A>은 항상 Nullable 형식이 아니라 내부 형식을 나타내는 <xref:System.Type> 개체를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="60764-107">Therefore <xref:System.Object.GetType%2A> always returns a <xref:System.Type> object that represents the underlying type, not the Nullable type.</span></span>  
  
```  
int? i = 5;  
Type t = i.GetType();  
Console.WriteLine(t.FullName); //"System.Int32"  
```  
  
 <span data-ttu-id="60764-108">C# [is](../../../csharp/language-reference/keywords/is.md) 연산자도 Nullable 내부 형식에서 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="60764-108">The C# [is](../../../csharp/language-reference/keywords/is.md) operator also operates on a Nullable's underlying type.</span></span> <span data-ttu-id="60764-109">따라서 `is`를 사용하여 변수가 Nullable 형식인지 여부를 확인할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="60764-109">Therefore you cannot use `is` to determine whether a variable is a Nullable type.</span></span> <span data-ttu-id="60764-110">다음 예제에서는 `is` 연산자가 Nullable\<int> 변수를 int 형식으로 처리함을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="60764-110">The following example shows that the `is` operator treats a Nullable\<int> variable as an int.</span></span>  
  
```  
static void Main(string[] args)  
{  
  int? i = 5;  
  if (i is int) // true  
    //…  
}  
```  
  
## <a name="example"></a><span data-ttu-id="60764-111">예</span><span class="sxs-lookup"><span data-stu-id="60764-111">Example</span></span>  
 <span data-ttu-id="60764-112">다음 코드를 사용하여 <xref:System.Type> 개체가 Nullable 형식을 나타내는지 여부를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60764-112">Use the following code to determine whether a <xref:System.Type> object represents a Nullable type.</span></span> <span data-ttu-id="60764-113">이 항목의 앞부분에서 설명한 것처럼 이 코드는 <xref:System.Object.GetType%2A> 호출에서 `Type` 개체가 반환된 경우 항상 false를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="60764-113">Remember that this code always returns false if the `Type` object was returned from a call to <xref:System.Object.GetType%2A>, as explained earlier in this topic.</span></span>  
  
```  
if (type.IsGenericType && type.GetGenericTypeDefinition() == typeof(Nullable<>)) {…}  
```  
  
## <a name="see-also"></a><span data-ttu-id="60764-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="60764-114">See Also</span></span>  
 [<span data-ttu-id="60764-115">Nullable 형식</span><span class="sxs-lookup"><span data-stu-id="60764-115">Nullable Types</span></span>](../../../csharp/programming-guide/nullable-types/index.md)  
 [<span data-ttu-id="60764-116">Nullable 형식 boxing</span><span class="sxs-lookup"><span data-stu-id="60764-116">Boxing Nullable Types</span></span>](../../../csharp/programming-guide/nullable-types/boxing-nullable-types.md)
