---
title: "Me, My, MyBase 및 MyClass Visual Basic의 | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- MyClass
- vb.Me
- MyBase
- vb.MyBase
- Me
- vb.MyClass
- vb.This
- vb.My
dev_langs:
- VB
helpviewer_keywords:
- My object
- self-reference, Me keyword
- MyClass keyword, relationship to similar programming elements
- Me keyword, relationship to similar programming elements
- Me keyword, referring to the current instance of an object
- Me keyword
- self-reference
- current instance, Me keyword
- MyBase keyword, relationship to similar programming elements
ms.assetid: f8e241ae-b1ed-4886-9aa0-08c632154029
caps.latest.revision: 15
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
ms.openlocfilehash: 3ba634eb28c25f47a0e88c856b916383b6ad15a2
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="me-my-mybase-and-myclass-in-visual-basic"></a><span data-ttu-id="4438d-102">Visual Basic의 Me, My, MyBase 및 MyClass</span><span class="sxs-lookup"><span data-stu-id="4438d-102">Me, My, MyBase, and MyClass in Visual Basic</span></span>
<span data-ttu-id="4438d-103">`Me``My`, `MyBase`, 및 `MyClass` 에서 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 유사한 이름에 있지만 서로 다른 목적으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="4438d-103">`Me`, `My`, `MyBase`, and `MyClass` in [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] have similar names, but different purposes.</span></span> <span data-ttu-id="4438d-104">이 항목에서는 구별할 수 있도록 이러한 각 엔터티를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="4438d-104">This topic describes each of these entities in order to distinguish them.</span></span>  
  
## <a name="me"></a><span data-ttu-id="4438d-105">Me</span><span class="sxs-lookup"><span data-stu-id="4438d-105">Me</span></span>  
 <span data-ttu-id="4438d-106">`Me` 키워드는 클래스 또는 구조체는 코드가 현재 실행 중인의 특정 인스턴스를 참조 하는 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4438d-106">The `Me` keyword provides a way to refer to the specific instance of a class or structure in which the code is currently executing.</span></span> <span data-ttu-id="4438d-107">`Me`현재 인스턴스 참조 구조 변수 또는 개체 변수 처럼 동작 합니다.</span><span class="sxs-lookup"><span data-stu-id="4438d-107">`Me` behaves like either an object variable or a structure variable referring to the current instance.</span></span> <span data-ttu-id="4438d-108">사용 하 여 `Me` 프로시저 다른 클래스, 구조체 또는 모듈에는 클래스 또는 구조체의 현재 실행 중인 인스턴스에 대 한 정보를 전달 하는 데 특히 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4438d-108">Using `Me` is particularly useful for passing information about the currently executing instance of a class or structure to a procedure in another class, structure, or module.</span></span>  
  
 <span data-ttu-id="4438d-109">예를 들어, 모듈에서 다음 절차를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4438d-109">For example, suppose you have the following procedure in a module.</span></span>  
  
```  
Sub ChangeFormColor(FormName As Form)  
   Randomize()  
   FormName.BackColor = Color.FromArgb(Rnd() * 256, Rnd() * 256, Rnd() * 256)  
End Sub  
```  
  
 <span data-ttu-id="4438d-110">이 프로시저를 호출 하 고의 현재 인스턴스를 전달할 수는 <xref:System.Windows.Forms.Form>클래스는 다음 문을 사용 하 여 인수로.</xref:System.Windows.Forms.Form></span><span class="sxs-lookup"><span data-stu-id="4438d-110">You can call this procedure and pass the current instance of the <xref:System.Windows.Forms.Form> class as an argument by using the following statement.</span></span>  
  
```  
ChangeFormColor(Me)  
```  
  
## <a name="my"></a><span data-ttu-id="4438d-111">My</span><span class="sxs-lookup"><span data-stu-id="4438d-111">My</span></span>  
 <span data-ttu-id="4438d-112">`My` 수의 쉽고 직관적인 액세스를 제공 하는 기능 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] 클래스에는 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 컴퓨터, 응용 프로그램, 설정, 리소스 및 등과 상호 작용 하는 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="4438d-112">The `My` feature provides easy and intuitive access to a number of [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] classes, enabling the [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] user to interact with the computer, application, settings, resources, and so on.</span></span>  
  
## <a name="mybase"></a><span data-ttu-id="4438d-113">MyBase</span><span class="sxs-lookup"><span data-stu-id="4438d-113">MyBase</span></span>  
 <span data-ttu-id="4438d-114">`MyBase` 키워드는 클래스의 현재 인스턴스는 기본 클래스를 참조 하는 개체 변수 처럼 동작 합니다.</span><span class="sxs-lookup"><span data-stu-id="4438d-114">The `MyBase` keyword behaves like an object variable referring to the base class of the current instance of a class.</span></span> <span data-ttu-id="4438d-115">`MyBase`일반적으로 재정의 되거나 파생된 클래스에서 숨겨진 하는 기본 클래스 멤버에 액세스 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4438d-115">`MyBase` is commonly used to access base class members that are overridden or shadowed in a derived class.</span></span> <span data-ttu-id="4438d-116">`MyBase.New`파생된 클래스 생성자에서 기본 클래스 생성자를 명시적으로 호출 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4438d-116">`MyBase.New` is used to explicitly call a base class constructor from a derived class constructor.</span></span>  
  
## <a name="myclass"></a><span data-ttu-id="4438d-117">MyClass</span><span class="sxs-lookup"><span data-stu-id="4438d-117">MyClass</span></span>  
 <span data-ttu-id="4438d-118">`MyClass` 키워드는 원래 구현 된 클래스의 현재 인스턴스를 참조 하는 개체 변수 처럼 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="4438d-118">The `MyClass` keyword behaves like an object variable referring to the current instance of a class as originally implemented.</span></span> <span data-ttu-id="4438d-119">`MyClass`비슷합니다 `Me`, 모든 메서드 호출에는 해당 메서드가 것 처럼 처리 됩니다 하지만 `NotOverridable`합니다.</span><span class="sxs-lookup"><span data-stu-id="4438d-119">`MyClass` is similar to `Me`, but all method calls on it are treated as if the method were `NotOverridable`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4438d-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4438d-120">See Also</span></span>  
 [<span data-ttu-id="4438d-121">상속 기본 사항</span><span class="sxs-lookup"><span data-stu-id="4438d-121">Inheritance Basics</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
