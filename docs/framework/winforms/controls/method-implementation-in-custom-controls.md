---
title: "사용자 지정 컨트롤에서 메서드 구현"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- user controls [Windows Forms], method implementation
- custom controls [Windows Forms], overloading methods
- custom controls [Windows Forms], method implementation
- methods [Windows Forms]
- methods [Windows Forms], custom controls
ms.assetid: 35d14fca-4bb4-4a27-8211-1f7a98ea27de
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e07d4a5f0a4e66e412b22e1f6cabd24cd81b5ea4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="method-implementation-in-custom-controls"></a><span data-ttu-id="83da8-102">사용자 지정 컨트롤에서 메서드 구현</span><span class="sxs-lookup"><span data-stu-id="83da8-102">Method Implementation in Custom Controls</span></span>
<span data-ttu-id="83da8-103">메서드는 다른 구성 요소에서 구현되는 것과 같은 방식으로 컨트롤에서 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="83da8-103">A method is implemented in a control in the same manner a method would be implemented in any other component.</span></span>  
  
 <span data-ttu-id="83da8-104">Visual Basic에서 값을 반환해야 하는 메서드는 `Public Function`으로 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="83da8-104">In Visual Basic, if a method is required to return a value, it is implemented as a `Public Function`.</span></span> <span data-ttu-id="83da8-105">값이 반환되지 않는 경우 메서드는 `Public Sub`로 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="83da8-105">If no value is returned, it is implemented as a `Public Sub`.</span></span> <span data-ttu-id="83da8-106">메서드는 다음 구문을 사용하여 선언됩니다.</span><span class="sxs-lookup"><span data-stu-id="83da8-106">Methods are declared using the following syntax:</span></span>  
  
```vb  
Public Function ConvertMatterToEnergy(Matter as Integer) As Integer  
   ' Conversion code goes here.  
End Function  
```  
  
 <span data-ttu-id="83da8-107">함수는 값을 반환하므로 정수, 문자열, 개체 등의 반환 형식을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="83da8-107">Because functions return a value, they must specify a return type, such as integer, string, object, and so on.</span></span> <span data-ttu-id="83da8-108">`Function` 또는 `Sub` 프로시저에서 사용하는 인수도 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="83da8-108">The arguments `Function` or `Sub` procedures take, if any, must also be specified.</span></span>  
  
 <span data-ttu-id="83da8-109">C#에서는 Visual Basic에서처럼 함수와 프로시저를 구분하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="83da8-109">C# makes no distinction between functions and procedures, as Visual Basic does.</span></span> <span data-ttu-id="83da8-110">메서드는 값이나 `void`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="83da8-110">A method either returns a value or returns `void`.</span></span> <span data-ttu-id="83da8-111">C# 공용 메서드를 선언하는 구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="83da8-111">The syntax for declaring a C# public method is:</span></span>  
  
```csharp  
public int ConvertMatterToEnergy(int matter)  
{  
   // Conversion code goes here.  
}  
```  
  
 <span data-ttu-id="83da8-112">메서드를 선언할 때는 가능하면 항상 모든 인수를 명시적 데이터 형식으로 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="83da8-112">When you declare a method, declare all of its arguments as explicit data types whenever possible.</span></span> <span data-ttu-id="83da8-113">개체 참조를 사용하는 인수는 `As Widget`가 아닌 `As Object`과 같이 특정 클래스 형식으로 선언해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="83da8-113">Arguments that take object references should be declared as specific class types — for example, `As Widget` instead of `As Object`.</span></span> <span data-ttu-id="83da8-114">Visual Basic에서 기본 설정인 `Option Strict`는 이 규칙을 자동으로 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="83da8-114">In Visual Basic, the default setting `Option Strict` automatically enforces this rule.</span></span>  
  
 <span data-ttu-id="83da8-115">형식이 지정된 인수를 사용하면 런타임이 아닌 컴파일러에서 대부분의 개발자 오류를 찾아낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83da8-115">Typed arguments allow many developer errors to be caught by the compiler, rather than at run time.</span></span> <span data-ttu-id="83da8-116">컴파일러는 항상 오류를 찾아내는 반면 런타임 테스트에서는 테스트 가능한 오류만 찾아낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83da8-116">The compiler always catches errors, whereas run-time testing is only as good as the test suite.</span></span>  
  
## <a name="overloaded-methods"></a><span data-ttu-id="83da8-117">오버로드된 메서드</span><span class="sxs-lookup"><span data-stu-id="83da8-117">Overloaded Methods</span></span>  
 <span data-ttu-id="83da8-118">컨트롤 사용자가 메서드에 서로 다른 매개 변수 조합을 제공할 수 있도록 하려면 명시적 데이터 형식을 사용하여 메서드의 여러 오버로드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="83da8-118">If you want to allow users of your control to supply different combinations of parameters to a method, provide multiple overloads of the method, using explicit data types.</span></span> <span data-ttu-id="83da8-119">모든 데이터 형식을 포함할 수 있는 `As Object`로 선언된 매개 변수는 만들지 않아야 합니다. 이러한 매개 변수를 만들면 오류가 발생해도 테스트에서 확인되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83da8-119">Avoid creating parameters declared `As Object` that can contain any data type, as this can lead to errors that might not be caught in testing.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="83da8-120">공용 언어 런타임의 유니버설 데이터 형식은 `Object`가 아닌 `Variant`입니다.</span><span class="sxs-lookup"><span data-stu-id="83da8-120">The universal data type in the common language runtime is `Object` rather than `Variant`.</span></span> <span data-ttu-id="83da8-121">`Variant`는 언어에서 제거되었습니다.</span><span class="sxs-lookup"><span data-stu-id="83da8-121">`Variant` has been removed from the language.</span></span>  
  
 <span data-ttu-id="83da8-122">예를 들어 가상 `Spin` 컨트롤의 `Widget` 메서드에서는 회전 방향과 속도를 직접 지정할 수도 있고 각운동량을 가져올 다른 `Widget` 개체를 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83da8-122">For example, the `Spin` method of a hypothetical `Widget` control might allow either direct specification of spin direction and speed, or specification of another `Widget` object from which angular momentum is to be absorbed:</span></span>  
  
```vb  
Overloads Public Sub Spin( _  
   ByVal SpinDirection As SpinDirectionsEnum, _  
   ByVal RevolutionsPerSecond As Double)  
   ' Implementation code here.  
End Sub  
Overloads Public Sub Spin(ByVal Driver As Widget) _  
   ' Implementation code here.  
End Sub  
```  
  
```csharp  
public void Spin(SpinDirectionsEnum spinDirection, double revolutionsPerSecond)  
{  
   // Implementation code here.  
}  
  
public void Spin(Widget driver)  
{  
   // Implementation code here.  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="83da8-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="83da8-123">See Also</span></span>  
 [<span data-ttu-id="83da8-124">이벤트</span><span class="sxs-lookup"><span data-stu-id="83da8-124">Events</span></span>](../../../../docs/standard/events/index.md)  
 [<span data-ttu-id="83da8-125">Windows Forms 컨트롤의 속성</span><span class="sxs-lookup"><span data-stu-id="83da8-125">Properties in Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/properties-in-windows-forms-controls.md)
