---
title: "속성 vs입니다. 인수"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 14651389-4a49-4cbb-9ddf-c83fdc155df1
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 9b3f06cf91591a373550f876f7b2111159067ba3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="properties-vs-arguments"></a><span data-ttu-id="8c631-102">속성 vs입니다. 인수</span><span class="sxs-lookup"><span data-stu-id="8c631-102">Properties vs. Arguments</span></span>
<span data-ttu-id="8c631-103">데이터를 작업으로 전달하는 데 사용할 수 있는 여러 가지 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c631-103">There are several options available for passing data into an activity.</span></span> <span data-ttu-id="8c631-104"><xref:System.Activities.InArgument>를 사용하는 것 외에 표준 CLR 속성이나 공용 <xref:System.Activities.ActivityAction> 속성을 사용하여 데이터를 받는 작업을 개발할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c631-104">In addition to using <xref:System.Activities.InArgument>, activities can also be developed that receive data using either standard CLR Properties or public <xref:System.Activities.ActivityAction> properties.</span></span> <span data-ttu-id="8c631-105">이 항목에서는 적절한 메서드 형식을 선택하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8c631-105">This topic discusses how to select the appropriate method type.</span></span>  
  
## <a name="using-clr-properties"></a><span data-ttu-id="8c631-106">CLR 속성 사용</span><span class="sxs-lookup"><span data-stu-id="8c631-106">Using CLR Properties</span></span>  
 <span data-ttu-id="8c631-107">데이터를 작업에 전달할 때 CLR 속성(즉, Get 및 Set 루틴을 사용하여 데이터를 노출하는 공용 메서드)은 가장 제한적인 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="8c631-107">When passing data into an activity, CLR properties (that is, public methods that use Get and Set routines to expose data) are the option that has the most restrictions.</span></span> <span data-ttu-id="8c631-108">솔루션을 컴파일할 때 CLR 속성에 전달되는 매개 변수 값을 알고 있어야 합니다. 이 값은 모든 워크플로 인스턴스에서 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="8c631-108">The value of a parameter passed into a CLR property must be known when the solution is compiled; this value will be the same for every instance of the workflow.</span></span> <span data-ttu-id="8c631-109">이 방식에서 CLR 속성에 전달되는 값은 코드로 정의되는 상수와 유사합니다. 이 값은 작업 수명 동안 변경될 수 없으며 작업의 다른 인스턴스에 대해 변경할 수도 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8c631-109">In this way, a value passed into a CLR property is similar to a constant defined in code; this value can’t change for the life of the activity, and can’t be changed for different instances of the activity.</span></span> <span data-ttu-id="8c631-110"><xref:System.Activities.Expressions.InvokeMethod%601.MethodName%2A>은 작업에서 노출되는 CLR 속성의 한 예입니다. 작업에서 호출하는 메서드 이름은 런타임 조건에 따라 변경될 수 없으며 작업의 모든 인스턴스에서 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="8c631-110"><xref:System.Activities.Expressions.InvokeMethod%601.MethodName%2A> is an example of a CLR property exposed by an activity; the method name that the activity calls can’t be changed based on runtime conditions, and will be the same for every instance of the activity.</span></span>  
  
## <a name="using-arguments"></a><span data-ttu-id="8c631-111">인수 사용</span><span class="sxs-lookup"><span data-stu-id="8c631-111">Using Arguments</span></span>  
 <span data-ttu-id="8c631-112">작업의 수명 동안 한 번만 데이터가 평가되는 경우 인수를 사용해야 합니다. 즉, 인수 값은 작업 수명 동안 변경되지 않지만 작업 인스턴스마다 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c631-112">Arguments should be used when data is only evaluated once during the lifetime of the activity; that is, its value will not change during the lifetime of the activity, but the value can be different for different instances of the activity.</span></span> <span data-ttu-id="8c631-113"><xref:System.Activities.Statements.If.Condition%2A>은 실행되는 동안 한 번만 평가되기 때문에 인수로 정의되어야 하는 값의 또 다른 예입니다.</span><span class="sxs-lookup"><span data-stu-id="8c631-113"><xref:System.Activities.Statements.If.Condition%2A> is an example of a value that gets evaluated once; therefore it is defined as an argument.</span></span> <span data-ttu-id="8c631-114"><xref:System.Activities.Statements.WriteLine.Text%2A>는 작업이 실행되는 동안 한 번만 평가되기 때문에 인수로 정의되어야 하는 메서드의 또 다른 예이지만 작업 인스턴스마다 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c631-114"><xref:System.Activities.Statements.WriteLine.Text%2A> is another example of a method that should be defined as an argument, since it is only evaluated once during the activity’s execution, but it can be different for different instances of the activity.</span></span>  
  
## <a name="using-activityaction"></a><span data-ttu-id="8c631-115">ActivityAction 사용</span><span class="sxs-lookup"><span data-stu-id="8c631-115">Using ActivityAction</span></span>  
 <span data-ttu-id="8c631-116">작업이 실행되는 동안 데이터를 여러 번 평가해야 하는 경우 <xref:System.Activities.ActivityAction>을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c631-116">When data needs to be evaluated multiple times during the lifetime of an activity’s execution, an <xref:System.Activities.ActivityAction> should be used.</span></span> <span data-ttu-id="8c631-117">예를 들어, <xref:System.Activities.Statements.While.Condition%2A> 속성은 <xref:System.Activities.Statements.While> 루프를 반복할 때마다 평가됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c631-117">For example, the <xref:System.Activities.Statements.While.Condition%2A> property is evaluated for each iteration of the <xref:System.Activities.Statements.While> loop.</span></span> <span data-ttu-id="8c631-118"><xref:System.Activities.InArgument>를 이런 용도로 사용한 경우 각 반복에 대해 인수가 다시 평가되지 않고 항상 동일한 결과를 반환하기 때문에 루프가 종료되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8c631-118">If an <xref:System.Activities.InArgument> were used for this purpose, the loop would never exit, since the argument would not be reevaluated for each iteration, and would always return the same result.</span></span>
