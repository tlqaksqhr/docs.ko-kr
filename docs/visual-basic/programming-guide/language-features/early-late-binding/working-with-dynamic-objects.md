---
title: 동적 개체 작업(Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- dynamic objects [Visual Basic]
ms.assetid: bdee2a00-07ff-46f9-86dd-fdac9b99cc97
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0f00c57107da5e6ea428e14964d8fa4a870bc96c
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="working-with-dynamic-objects-visual-basic"></a><span data-ttu-id="d96f1-102">동적 개체 작업(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d96f1-102">Working with Dynamic Objects (Visual Basic)</span></span>
<span data-ttu-id="d96f1-103">동적 개체는 또 다른 방법은 이외의 `Object` 에 바인딩할 수 있는 개체 런타임 시 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="d96f1-103">Dynamic objects provide another way, other than the `Object` type, to late bind to an object at run time.</span></span> <span data-ttu-id="d96f1-104">동적 개체에 정의 된 동적 인터페이스를 사용 하 여 런타임 시 속성 및 메서드와 같은 멤버를 노출 된 <xref:System.Dynamic> 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="d96f1-104">A dynamic object exposes members such as properties and methods at run time by using dynamic interfaces that are defined in the <xref:System.Dynamic> namespace.</span></span> <span data-ttu-id="d96f1-105">클래스를 사용할 수는 <xref:System.Dynamic> 정적 유형 또는 응답 형식이 일치 하지 않는 데이터 구조를 사용 하는 개체를 만들려는 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="d96f1-105">You can use the classes in the <xref:System.Dynamic> namespace to create objects that work with data structures that do not match a static type or format.</span></span> <span data-ttu-id="d96f1-106">IronPython 및 IronRuby과 같은 동적 언어에서 정의 된 동적 개체를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d96f1-106">You can also use the dynamic objects that are defined in dynamic languages such as IronPython and IronRuby.</span></span> <span data-ttu-id="d96f1-107">동적 개체를 만들거나 동적 언어로 정의 된 동적 개체를 사용 하는 방법을 보여 주는 예제를 보려면 [연습: 동적 개체 만들기 및 사용 하 여](../../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md), <xref:System.Dynamic.DynamicObject>, 또는 <xref:System.Dynamic.ExpandoObject>합니다.</span><span class="sxs-lookup"><span data-stu-id="d96f1-107">For examples that show how to create dynamic objects or use a dynamic object defined in a dynamic language, see [Walkthrough: Creating and Using Dynamic Objects](../../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md), <xref:System.Dynamic.DynamicObject>, or <xref:System.Dynamic.ExpandoObject>.</span></span>  
  
 <span data-ttu-id="d96f1-108">Visual Basic 개체에 동적 언어 런타임 및 IronPython 및 IronRuby과 같은 동적 언어에서 사용 하 여 바인딩합니다는 <xref:System.Dynamic.IDynamicMetaObjectProvider> 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="d96f1-108">Visual Basic binds to objects from the dynamic language runtime and dynamic languages such as IronPython and IronRuby by using the <xref:System.Dynamic.IDynamicMetaObjectProvider> interface.</span></span> <span data-ttu-id="d96f1-109">구현 하는 클래스의 예는 `IDynamicMetaObjectProvider` 인터페이스는 <xref:System.Dynamic.DynamicObject> 및 <xref:System.Dynamic.ExpandoObject> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="d96f1-109">Examples of classes that implement the `IDynamicMetaObjectProvider` interface are the <xref:System.Dynamic.DynamicObject> and <xref:System.Dynamic.ExpandoObject> classes.</span></span>  
  
 <span data-ttu-id="d96f1-110">구현 하는 개체는 런타임에 바인딩된 호출 된 경우는 `IDynamicMetaObjectProvider` 인터페이스, 해당 인터페이스를 사용 하 여 동적 개체에 대 한 Visual Basic 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="d96f1-110">If a late-bound call is made to an object that implements the `IDynamicMetaObjectProvider` interface, Visual Basic binds to the dynamic object by using that interface.</span></span> <span data-ttu-id="d96f1-111">런타임에 바인딩된 호출을 구현 하지 않는 개체에 만들어질 경우는 `IDynamicMetaObjectProvider` 인터페이스를 경우에 대 한 호출에서 `IDynamicMetaObjectProvider` 인터페이스 실패, Visual Basic의 Visual Basic 런타임에 런타임에 바인딩 기능을 사용 하 여 개체에 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="d96f1-111">If a late-bound call is made to an object that does not implement the `IDynamicMetaObjectProvider` interface, or if the call to the `IDynamicMetaObjectProvider` interface fails, Visual Basic binds to the object by using the late-binding capabilities of the Visual Basic runtime.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d96f1-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d96f1-112">See Also</span></span>  
 <xref:System.Dynamic.DynamicObject>  
 <xref:System.Dynamic.ExpandoObject>  
 [<span data-ttu-id="d96f1-113">연습: 동적 개체 만들기 및 사용</span><span class="sxs-lookup"><span data-stu-id="d96f1-113">Walkthrough: Creating and Using Dynamic Objects</span></span>](../../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md)  
 [<span data-ttu-id="d96f1-114">초기 바인딩 및 런타임에 바인딩</span><span class="sxs-lookup"><span data-stu-id="d96f1-114">Early and Late Binding</span></span>](../../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)
