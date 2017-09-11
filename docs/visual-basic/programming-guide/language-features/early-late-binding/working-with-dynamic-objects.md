---
title: "동적 개체 (Visual Basic) 작업 | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- dynamic objects [Visual Basic]
ms.assetid: bdee2a00-07ff-46f9-86dd-fdac9b99cc97
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: d1e1c4f7338daad0f1101f6e886eba6c37316b0e
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="working-with-dynamic-objects-visual-basic"></a><span data-ttu-id="fcdb5-102">동적 개체 작업(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fcdb5-102">Working with Dynamic Objects (Visual Basic)</span></span>
<span data-ttu-id="fcdb5-103">동적 개체는 또 다른 방법은 이외의 제공는 `Object` 에 런타임에 개체에 바인딩할 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="fcdb5-103">Dynamic objects provide another way, other than the `Object` type, to late bind to an object at run time.</span></span> <span data-ttu-id="fcdb5-104">동적 개체에 정의 된 동적 인터페이스를 사용 하 여 런타임에 속성 및 메서드 같은 멤버를 노출 된 <xref:System.Dynamic>네임 스페이스.</xref:System.Dynamic></span><span class="sxs-lookup"><span data-stu-id="fcdb5-104">A dynamic object exposes members such as properties and methods at run time by using dynamic interfaces that are defined in the <xref:System.Dynamic> namespace.</span></span> <span data-ttu-id="fcdb5-105">클래스를 사용할 수는 <xref:System.Dynamic>정적 형식 또는 형식 일치 하지 않는 데이터 구조를 사용 하는 개체를 만들 네임 스페이스.</xref:System.Dynamic></span><span class="sxs-lookup"><span data-stu-id="fcdb5-105">You can use the classes in the <xref:System.Dynamic> namespace to create objects that work with data structures that do not match a static type or format.</span></span> <span data-ttu-id="fcdb5-106">IronPython 및 IronRuby와 같은 동적 언어에 정의 된 동적 개체를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fcdb5-106">You can also use the dynamic objects that are defined in dynamic languages such as IronPython and IronRuby.</span></span> <span data-ttu-id="fcdb5-107">동적 개체를 만들거나 동적 언어에 정의 된 동적 개체를 사용 하는 방법을 보여 주는 예제를 보려면 [연습: 동적 개체 만들기 및 사용 하 여](../../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md), <xref:System.Dynamic.DynamicObject>, 또는 <xref:System.Dynamic.ExpandoObject>.</xref:System.Dynamic.ExpandoObject> </xref:System.Dynamic.DynamicObject></span><span class="sxs-lookup"><span data-stu-id="fcdb5-107">For examples that show how to create dynamic objects or use a dynamic object defined in a dynamic language, see [Walkthrough: Creating and Using Dynamic Objects](../../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md), <xref:System.Dynamic.DynamicObject>, or <xref:System.Dynamic.ExpandoObject>.</span></span>  
  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="fcdb5-108">동적 언어 런타임 및 IronPython 및 IronRuby와 같은 동적 언어에서 사용 하 여 개체에 바인딩하는 <xref:System.Dynamic.IDynamicMetaObjectProvider>인터페이스.</xref:System.Dynamic.IDynamicMetaObjectProvider></span><span class="sxs-lookup"><span data-stu-id="fcdb5-108"> binds to objects from the dynamic language runtime and dynamic languages such as IronPython and IronRuby by using the <xref:System.Dynamic.IDynamicMetaObjectProvider> interface.</span></span> <span data-ttu-id="fcdb5-109">구현 하는 클래스의 예는 `IDynamicMetaObjectProvider` 인터페이스는는 <xref:System.Dynamic.DynamicObject>및 <xref:System.Dynamic.ExpandoObject>클래스.</xref:System.Dynamic.ExpandoObject> </xref:System.Dynamic.DynamicObject></span><span class="sxs-lookup"><span data-stu-id="fcdb5-109">Examples of classes that implement the `IDynamicMetaObjectProvider` interface are the <xref:System.Dynamic.DynamicObject> and <xref:System.Dynamic.ExpandoObject> classes.</span></span>  
  
 <span data-ttu-id="fcdb5-110">런타임에 바인딩된 호출 하려고 구현 하는 개체는 `IDynamicMetaObjectProvider` 인터페이스를 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 해당 인터페이스를 사용 하 여 동적 개체에 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="fcdb5-110">If a late-bound call is made to an object that implements the `IDynamicMetaObjectProvider` interface, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] binds to the dynamic object by using that interface.</span></span> <span data-ttu-id="fcdb5-111">구현 하지 않는 개체에 런타임에 바인딩된 호출 하는 경우는 `IDynamicMetaObjectProvider` 인터페이스, 경우에 대 한 호출은 `IDynamicMetaObjectProvider` 실패 하면 인터페이스 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 의 런타임 바인딩 기능을 사용 하 여 개체에 바인딩합니다는 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 런타임입니다.</span><span class="sxs-lookup"><span data-stu-id="fcdb5-111">If a late-bound call is made to an object that does not implement the `IDynamicMetaObjectProvider` interface, or if the call to the `IDynamicMetaObjectProvider` interface fails, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] binds to the object by using the late-binding capabilities of the [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] runtime.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fcdb5-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fcdb5-112">See Also</span></span>  
 <span data-ttu-id="fcdb5-113"><xref:System.Dynamic.DynamicObject></xref:System.Dynamic.DynamicObject></span><span class="sxs-lookup"><span data-stu-id="fcdb5-113"><xref:System.Dynamic.DynamicObject></span></span>   
 <span data-ttu-id="fcdb5-114"><xref:System.Dynamic.ExpandoObject></xref:System.Dynamic.ExpandoObject></span><span class="sxs-lookup"><span data-stu-id="fcdb5-114"><xref:System.Dynamic.ExpandoObject></span></span>   
<span data-ttu-id="fcdb5-115"> [연습: 동적 개체를 사용 하 여 만들고](../../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md) </span><span class="sxs-lookup"><span data-stu-id="fcdb5-115"> [Walkthrough: Creating and Using Dynamic Objects](../../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md) </span></span>  
<span data-ttu-id="fcdb5-116"> [초기 바인딩 및 런타임에 바인딩](../../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)</span><span class="sxs-lookup"><span data-stu-id="fcdb5-116"> [Early and Late Binding](../../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)</span></span>
