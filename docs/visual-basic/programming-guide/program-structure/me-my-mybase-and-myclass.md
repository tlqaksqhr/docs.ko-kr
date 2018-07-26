---
title: Visual Basic의 Me, My, MyBase 및 MyClass
ms.date: 07/20/2015
f1_keywords:
- MyClass
- vb.Me
- MyBase
- vb.MyBase
- Me
- vb.MyClass
- vb.This
- vb.My
helpviewer_keywords:
- My object
- self-reference [Visual Basic], Me keyword
- MyClass keyword [Visual Basic], relationship to similar programming elements
- Me keyword [Visual Basic], relationship to similar programming elements
- Me keyword [Visual Basic], referring to the current instance of an object
- Me keyword [Visual Basic]
- self-reference
- current instance [Visual Basic], Me keyword
- MyBase keyword [Visual Basic], relationship to similar programming elements
ms.assetid: f8e241ae-b1ed-4886-9aa0-08c632154029
ms.openlocfilehash: f3db5f8f6688e68992f683ac1b1465078aa41231
ms.sourcegitcommit: 70c76a12449439bac0f7a359866be5a0311ce960
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/25/2018
ms.locfileid: "39244714"
---
# <a name="me-my-mybase-and-myclass-in-visual-basic"></a><span data-ttu-id="141c3-102">Visual Basic의 Me, My, MyBase 및 MyClass</span><span class="sxs-lookup"><span data-stu-id="141c3-102">Me, My, MyBase, and MyClass in Visual Basic</span></span>
<span data-ttu-id="141c3-103">`Me`를 `My`, `MyBase`, 및 `MyClass` Visual Basic에는 비슷한 이름 이지만 다른 목적으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="141c3-103">`Me`, `My`, `MyBase`, and `MyClass` in Visual Basic have similar names, but different purposes.</span></span> <span data-ttu-id="141c3-104">이 항목에서는 구별할 수 있도록 이러한 각 엔터티를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="141c3-104">This topic describes each of these entities in order to distinguish them.</span></span>  
  
## <a name="me"></a><span data-ttu-id="141c3-105">Me</span><span class="sxs-lookup"><span data-stu-id="141c3-105">Me</span></span>  
 <span data-ttu-id="141c3-106">`Me` 키워드를 클래스 또는 구조 코드는 현재 실행 중인 특정 인스턴스를 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="141c3-106">The `Me` keyword provides a way to refer to the specific instance of a class or structure in which the code is currently executing.</span></span> <span data-ttu-id="141c3-107">`Me` 개체 변수 또는 현재 인스턴스를 참조 하는 구조 변수 처럼 동작 합니다.</span><span class="sxs-lookup"><span data-stu-id="141c3-107">`Me` behaves like either an object variable or a structure variable referring to the current instance.</span></span> <span data-ttu-id="141c3-108">사용 하 여 `Me` 프로시저 다른 클래스, 구조체 또는 모듈에는 클래스 또는 구조체의 현재 실행 중인 인스턴스에 대 한 정보를 전달 하는 데 특히 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="141c3-108">Using `Me` is particularly useful for passing information about the currently executing instance of a class or structure to a procedure in another class, structure, or module.</span></span>  
  
 <span data-ttu-id="141c3-109">예를 들어, 모듈의 다음 절차를 있다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="141c3-109">For example, suppose you have the following procedure in a module.</span></span>  
  
```  
Sub ChangeFormColor(FormName As Form)  
   Randomize()  
   FormName.BackColor = Color.FromArgb(Rnd() * 256, Rnd() * 256, Rnd() * 256)  
End Sub  
```  
  
 <span data-ttu-id="141c3-110">이 프로시저를 호출 하는의 현재 인스턴스를 전달 합니다 <xref:System.Windows.Forms.Form> 다음 문을 사용 하 여 인수로 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="141c3-110">You can call this procedure and pass the current instance of the <xref:System.Windows.Forms.Form> class as an argument by using the following statement.</span></span>  
  
```  
ChangeFormColor(Me)  
```  
  
## <a name="my"></a><span data-ttu-id="141c3-111">My</span><span class="sxs-lookup"><span data-stu-id="141c3-111">My</span></span>  
 <span data-ttu-id="141c3-112">합니다 `My` 다양 한 쉽고 직관적인 액세스를 제공 하는 기능 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 클래스, Visual Basic 사용자의 컴퓨터, 응용 프로그램, 설정, 리소스 및 등을 사용 하 여 상호 작용 하도록 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="141c3-112">The `My` feature provides easy and intuitive access to a number of [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] classes, enabling the Visual Basic user to interact with the computer, application, settings, resources, and so on.</span></span>  
  
## <a name="mybase"></a><span data-ttu-id="141c3-113">MyBase</span><span class="sxs-lookup"><span data-stu-id="141c3-113">MyBase</span></span>  
 <span data-ttu-id="141c3-114">`MyBase` 키워드는 클래스의 현재 인스턴스의 기본 클래스를 참조 하는 개체 변수 처럼 동작 합니다.</span><span class="sxs-lookup"><span data-stu-id="141c3-114">The `MyBase` keyword behaves like an object variable referring to the base class of the current instance of a class.</span></span> <span data-ttu-id="141c3-115">`MyBase` 파생된 클래스에서 섀도 처리 되거나 재정의 되는 기본 클래스 멤버 액세스를 주로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="141c3-115">`MyBase` is commonly used to access base class members that are overridden or shadowed in a derived class.</span></span> <span data-ttu-id="141c3-116">`MyBase.New` 파생된 클래스 생성자에서 기본 클래스 생성자를 명시적으로 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="141c3-116">`MyBase.New` is used to explicitly call a base class constructor from a derived class constructor.</span></span>  
  
## <a name="myclass"></a><span data-ttu-id="141c3-117">MyClass</span><span class="sxs-lookup"><span data-stu-id="141c3-117">MyClass</span></span>  
 <span data-ttu-id="141c3-118">`MyClass` 키워드 원래 구현 된 클래스의 현재 인스턴스를 참조 하는 개체 변수 처럼 동작 합니다.</span><span class="sxs-lookup"><span data-stu-id="141c3-118">The `MyClass` keyword behaves like an object variable referring to the current instance of a class as originally implemented.</span></span> <span data-ttu-id="141c3-119">`MyClass` 비슷합니다 `Me`, 되지만에 대 한 모든 메서드 호출이 메서드 것 처럼 처리 됩니다 `NotOverridable`합니다.</span><span class="sxs-lookup"><span data-stu-id="141c3-119">`MyClass` is similar to `Me`, but all method calls on it are treated as if the method were `NotOverridable`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="141c3-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="141c3-120">See Also</span></span>  
 [<span data-ttu-id="141c3-121">상속 기본 사항</span><span class="sxs-lookup"><span data-stu-id="141c3-121">Inheritance Basics</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
