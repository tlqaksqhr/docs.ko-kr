---
title: 대리자의 가변성 사용(C#)
ms.date: 07/20/2015
ms.assetid: 1638c95d-dc8b-40c1-972c-c2dcf84be55e
ms.openlocfilehash: 46c09da9adac7ed47c32b1fed4311dfedbf5764e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="using-variance-in-delegates-c"></a><span data-ttu-id="04c18-102">대리자의 가변성 사용(C#)</span><span class="sxs-lookup"><span data-stu-id="04c18-102">Using Variance in Delegates (C#)</span></span>
<span data-ttu-id="04c18-103">메서드를 대리자에 할당하면 *공변성(covariance)* 및 *반공변성(Contravariance)* 은 대리자 형식과 메서드 시그니처의 일치를 확인하는 유연성을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="04c18-103">When you assign a method to a delegate, *covariance* and *contravariance* provide flexibility for matching a delegate type with a method signature.</span></span> <span data-ttu-id="04c18-104">공변성(covariance)은 메서드가 대리자에 정의된 것보다 더 많은 수의 파생된 형식을 반환하도록 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="04c18-104">Covariance permits a method to have return type that is more derived than that defined in the delegate.</span></span> <span data-ttu-id="04c18-105">반공변성(contravariance)은 메서드가 대리자 형식보다 더 적은 수의 파생된 매개 변수 형식을 갖도록 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="04c18-105">Contravariance permits a method that has parameter types that are less derived than those in the delegate type.</span></span>  
  
## <a name="example-1-covariance"></a><span data-ttu-id="04c18-106">예제 1: 공변성(Covariance)</span><span class="sxs-lookup"><span data-stu-id="04c18-106">Example 1: Covariance</span></span>  
  
### <a name="description"></a><span data-ttu-id="04c18-107">설명</span><span class="sxs-lookup"><span data-stu-id="04c18-107">Description</span></span>  
 <span data-ttu-id="04c18-108">이 예제에서는 대리자를 대리자 시그니처의 반환 형식에서 파생된 반환 형식이 있는 메서드와 함께 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="04c18-108">This example demonstrates how delegates can be used with methods that have return types that are derived from the return type in the delegate signature.</span></span> <span data-ttu-id="04c18-109">`DogsHandler`에서 반환된 데이터 형식은 `Dogs`이고, 이 형식은 대리자에 정의된 `Mammals` 형식에서 파생됩니다.</span><span class="sxs-lookup"><span data-stu-id="04c18-109">The data type returned by `DogsHandler` is of type `Dogs`, which derives from the `Mammals` type that is defined in the delegate.</span></span>  
  
### <a name="code"></a><span data-ttu-id="04c18-110">코드</span><span class="sxs-lookup"><span data-stu-id="04c18-110">Code</span></span>  
  
```csharp  
class Mammals{}  
class Dogs : Mammals{}  
  
class Program  
{  
    // Define the delegate.  
    public delegate Mammals HandlerMethod();  
  
    public static Mammals MammalsHandler()  
    {  
        return null;  
    }  
  
    public static Dogs DogsHandler()  
    {  
        return null;  
    }  
  
    static void Test()  
    {  
        HandlerMethod handlerMammals = MammalsHandler;  
  
        // Covariance enables this assignment.  
        HandlerMethod handlerDogs = DogsHandler;  
    }  
}  
```  
  
## <a name="example-2-contravariance"></a><span data-ttu-id="04c18-111">예제 2: 반공변성(Contravariance)</span><span class="sxs-lookup"><span data-stu-id="04c18-111">Example 2: Contravariance</span></span>  
  
### <a name="description"></a><span data-ttu-id="04c18-112">설명</span><span class="sxs-lookup"><span data-stu-id="04c18-112">Description</span></span>  
 <span data-ttu-id="04c18-113">이 예제에서는 대리자를 대리자 시그니처 매개 변수 형식의 기본 형식인 형식 매개 변수를 가지고 있는 메서드와 함께 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="04c18-113">This example demonstrates how delegates can be used with methods that have parameters of a type that are base types of the delegate signature parameter type.</span></span> <span data-ttu-id="04c18-114">반공변성(contravariance)에서는 별도의 여러 처리기 대신 하나의 이벤트 처리기를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04c18-114">With contravariance, you can use one event handler instead of separate handlers.</span></span> <span data-ttu-id="04c18-115">예를 들어 `EventArgs` 입력 매개 변수를 수락하고, 매개 변수로서 `MouseEventArgs` 형식을 전송하는 `Button.MouseClick` 이벤트 및 `KeyEventArgs` 매개 변수를 전송하는 `TextBox.KeyDown` 이벤트와 함께 사용하는 이벤트 처리기를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04c18-115">For example, you can create an event handler that accepts an `EventArgs` input parameter and use it with a `Button.MouseClick` event that sends a `MouseEventArgs` type as a parameter, and also with a `TextBox.KeyDown` event that sends a `KeyEventArgs` parameter.</span></span>  
  
### <a name="code"></a><span data-ttu-id="04c18-116">코드</span><span class="sxs-lookup"><span data-stu-id="04c18-116">Code</span></span>  
  
```csharp  
// Event handler that accepts a parameter of the EventArgs type.  
private void MultiHandler(object sender, System.EventArgs e)  
{  
    label1.Text = System.DateTime.Now.ToString();  
}  
  
public Form1()  
{  
    InitializeComponent();  
  
    // You can use a method that has an EventArgs parameter,  
    // although the event expects the KeyEventArgs parameter.  
    this.button1.KeyDown += this.MultiHandler;  
  
    // You can use the same method   
    // for an event that expects the MouseEventArgs parameter.  
    this.button1.MouseClick += this.MultiHandler;  
  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="04c18-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="04c18-117">See Also</span></span>  
 [<span data-ttu-id="04c18-118">대리자의 가변성(C#)</span><span class="sxs-lookup"><span data-stu-id="04c18-118">Variance in Delegates (C#)</span></span>](../../../../csharp/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md)  
 [<span data-ttu-id="04c18-119">Func 및 Action 제네릭 대리자에 가변성 사용(C#)</span><span class="sxs-lookup"><span data-stu-id="04c18-119">Using Variance for Func and Action Generic Delegates (C#)</span></span>](../../../../csharp/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md)
