---
title: "선언된 요소 (Visual Basic)에 대 한 참조 | Microsoft 문서"
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
- declared elements
- references, declared elements
- qualified names
ms.assetid: d6301709-f4cc-4b7a-b8ba-80898f14ab46
caps.latest.revision: 19
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
ms.openlocfilehash: 5de39ac5c30b1cff2a8bfd0cd606dee33c078514
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="references-to-declared-elements-visual-basic"></a><span data-ttu-id="51e7a-102">선언된 요소 참조(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="51e7a-102">References to Declared Elements (Visual Basic)</span></span>
<span data-ttu-id="51e7a-103">코드에서 선언 된 요소를 참조 하는 경우는 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 컴파일러에서 참조를 해당 이름의 적절 한 선언에 있는 이름과 일치 합니다.</span><span class="sxs-lookup"><span data-stu-id="51e7a-103">When your code refers to a declared element, the [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler matches the name in your reference to the appropriate declaration of that name.</span></span> <span data-ttu-id="51e7a-104">둘 이상의 요소가 동일한 이름으로 선언 되는 경우이 참조 하는 요소 제어할 수 있습니다 *조건에 맞는* 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="51e7a-104">If more than one element is declared with the same name, you can control which of those elements is to be referenced by *qualifying* its name.</span></span>  
  
 <span data-ttu-id="51e7a-105">컴파일러는 이름 선언에 대 한 이름 참조를 찾으려고 시도 *가장 좁은 범위*합니다.</span><span class="sxs-lookup"><span data-stu-id="51e7a-105">The compiler attempts to match a name reference to a name declaration with the *narrowest scope*.</span></span> <span data-ttu-id="51e7a-106">즉, 코드 참조를 만들기 시작 하 고 요소를 포함 하는 연속적인 수준의 바깥쪽으로 진행 합니다.</span><span class="sxs-lookup"><span data-stu-id="51e7a-106">This means it starts with the code making the reference and works outward through successive levels of containing elements.</span></span>  
  
 <span data-ttu-id="51e7a-107">다음 예제에서는 이름이 같은 두 변수에 대 한 참조를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="51e7a-107">The following example shows references to two variables with the same name.</span></span> <span data-ttu-id="51e7a-108">이 예제에서는 두 개의 변수를 선언한, 각각의 명명 된 `totalCount`, 서로 다른 수준의 모듈의 범위에서 `container`합니다.</span><span class="sxs-lookup"><span data-stu-id="51e7a-108">The example declares two variables, each named `totalCount`, at different levels of scope in module `container`.</span></span> <span data-ttu-id="51e7a-109">때 프로시저 `showCount` 표시 `totalCount` 한정자 없이 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 내 로컬 선언 즉 가장 좁은 범위에서 선언에 대 한 참조를 확인 하는 컴파일러 `showCount`합니다.</span><span class="sxs-lookup"><span data-stu-id="51e7a-109">When the procedure `showCount` displays `totalCount` without qualification, the [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler resolves the reference to the declaration with the narrowest scope, namely the local declaration inside `showCount`.</span></span> <span data-ttu-id="51e7a-110">모듈인 `totalCount` 포함 하는 모듈와 `container`, 컴파일러는 더 넓은 범위에서 선언에 대 한 참조를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="51e7a-110">When it qualifies `totalCount` with the containing module `container`, the compiler resolves the reference to the declaration with the broader scope.</span></span>  
  
```vb  
' Assume these two modules are both in the same assembly.  
Module container  
    Public totalCount As Integer = 1  
    Public Sub showCount()  
        Dim totalCount As Integer = 6000  
        ' The following statement displays the local totalCount (6000).  
        MsgBox("Unqualified totalCount is " & CStr(totalCount))  
        ' The following statement displays the module's totalCount (1).  
        MsgBox("container.totalCount is " & CStr(container.totalCount))  
    End Sub  
End Module  
Module callingModule  
    Public Sub displayCount()  
        container.showCount()  
        ' The following statement displays the containing module's totalCount (1).  
        MsgBox("container.totalCount is " & CStr(container.totalCount))  
    End Sub  
End Module  
```  
  
## <a name="qualifying-an-element-name"></a><span data-ttu-id="51e7a-111">요소 이름 한정</span><span class="sxs-lookup"><span data-stu-id="51e7a-111">Qualifying an Element Name</span></span>  
 <span data-ttu-id="51e7a-112">이 검색 프로세스를 재정의 하 고 해야 더 넓은 범위에 선언 된 이름을 지정 하려는 경우 *한정* 더 넓은 범위의 포함 하는 요소 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="51e7a-112">If you want to override this search process and specify a name declared in a broader scope, you must *qualify* the name with the containing element of the broader scope.</span></span> <span data-ttu-id="51e7a-113">일부 경우에 포함 하는 요소를 정해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51e7a-113">In some cases, you might also have to qualify the containing element.</span></span>  
  
 <span data-ttu-id="51e7a-114">하면 이름이 한정 앞에 대상 요소 정의 된 위치를 식별 하는 정보 소스 문의 합니다.</span><span class="sxs-lookup"><span data-stu-id="51e7a-114">Qualifying a name means preceding it in your source statement with information that identifies where the target element is defined.</span></span> <span data-ttu-id="51e7a-115">이 정보 라고는 *한정 문자열*합니다.</span><span class="sxs-lookup"><span data-stu-id="51e7a-115">This information is called a *qualification string*.</span></span> <span data-ttu-id="51e7a-116">하나를 포함 하거나 자세한 네임 스페이스 및 모듈의 경우, 클래스 또는 구조체입니다.</span><span class="sxs-lookup"><span data-stu-id="51e7a-116">It can include one or more namespaces and a module, class, or structure.</span></span>  
  
 <span data-ttu-id="51e7a-117">정규화 문자열 모듈, 클래스 또는 구조체를 포함 하는 대상 요소에 명확 하 게 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="51e7a-117">The qualification string should unambiguously specify the module, class, or structure containing the target element.</span></span> <span data-ttu-id="51e7a-118">컨테이너 수에 다른 포함 하는 요소의 네임 스페이스에 일반적으로에 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51e7a-118">The container might in turn be located in another containing element, usually a namespace.</span></span> <span data-ttu-id="51e7a-119">정규화 문자열에 여러 요소를 포함 하를 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="51e7a-119">You might need to include several containing elements in the qualification string.</span></span>  
  
#### <a name="to-access-a-declared-element-by-qualifying-its-name"></a><span data-ttu-id="51e7a-120">해당 이름을 정규화 하 여 선언 된 요소에 액세스 하려면</span><span class="sxs-lookup"><span data-stu-id="51e7a-120">To access a declared element by qualifying its name</span></span>  
  
1.  <span data-ttu-id="51e7a-121">요소는 정의 된 위치를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="51e7a-121">Determine the location in which the element has been defined.</span></span> <span data-ttu-id="51e7a-122">여기에 네임 스페이스 또는 네임 스페이스의 계층 구조가 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51e7a-122">This might include a namespace, or even a hierarchy of namespaces.</span></span> <span data-ttu-id="51e7a-123">가장 낮은 수준의 네임 스페이스 내에서 요소는 모듈, 클래스 또는 구조체에 포함 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="51e7a-123">Within the lowest-level namespace, the element must be contained in a module, class, or structure.</span></span>  
  
    ```vb  
    ' Assume the following hierarchy exists outside your code.  
    Namespace outerSpace  
        Namespace innerSpace  
            Module holdsTotals  
                Public Structure totals  
                    Public thisTotal As Integer  
                    Public Shared grandTotal As Long  
                End Structure  
            End Module  
        End Namespace  
    End Namespace  
    ```  
  
2.  <span data-ttu-id="51e7a-124">대상 요소의 위치에 따라 한정 경로 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="51e7a-124">Determine a qualification path based on the target element's location.</span></span> <span data-ttu-id="51e7a-125">최상위 수준 네임 스페이스, 가장 낮은 수준의 네임 스페이스를 진행 시작한 모듈, 클래스 또는 구조체를 포함 하는 대상 요소 끝나야 합니다.</span><span class="sxs-lookup"><span data-stu-id="51e7a-125">Start with the highest-level namespace, proceed to the lowest-level namespace, and end with the module, class, or structure containing the target element.</span></span> <span data-ttu-id="51e7a-126">경로 있는 각 요소에는 뒤에 오는 요소가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="51e7a-126">Each element in the path must contain the element that follows it.</span></span>  
  
     <span data-ttu-id="51e7a-127">`outerSpace` → `innerSpace` → `holdsTotals` → `totals`</span><span class="sxs-lookup"><span data-stu-id="51e7a-127">`outerSpace` → `innerSpace` → `holdsTotals` → `totals`</span></span>  
  
3.  <span data-ttu-id="51e7a-128">대상 요소에 대 한 한정 문자열을 준비 합니다.</span><span class="sxs-lookup"><span data-stu-id="51e7a-128">Prepare the qualification string for the target element.</span></span> <span data-ttu-id="51e7a-129">에 마침표 (`.`) 경로 있는 모든 요소 뒤 합니다.</span><span class="sxs-lookup"><span data-stu-id="51e7a-129">Place a period (`.`) after every element in the path.</span></span> <span data-ttu-id="51e7a-130">응용 프로그램에서 한정 문자열의 모든 요소에 액세스할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="51e7a-130">Your application must have access to every element in your qualification string.</span></span>  
  
    ```vb  
    outerSpace.innerSpace.holdsTotals.totals.  
    ```  
  
4.  <span data-ttu-id="51e7a-131">식 또는 일반적인 방법으로 대상 요소를 참조 하는 대입문을 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="51e7a-131">Write the expression or assignment statement referring to the target element in the normal way.</span></span>  
  
    ```vb  
    grandTotal = 9000  
    ```  
  
5.  <span data-ttu-id="51e7a-132">대상 요소 이름 한정 문자열 앞에 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="51e7a-132">Precede the target element name with the qualification string.</span></span> <span data-ttu-id="51e7a-133">이름은 마침표 바로 다음에 나와야 (`.`) 모듈, 클래스 또는 요소가 포함 된 구조를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="51e7a-133">The name should immediately follow the period (`.`) that follows the module, class, or structure that contains the element.</span></span>  
  
    ```vb  
    ' Assume the following module is part of your code.  
    Module accessGrandTotal  
        Public Sub setGrandTotal()  
            outerSpace.innerSpace.holdsTotals.totals.grandTotal = 9000  
        End Sub  
    End Module  
    ```  
  
6.  <span data-ttu-id="51e7a-134">컴파일러를 대상 요소 참조 일치 시킬 수는 명확 하 고 모호 하지 않은 선언의 찾을 한정 문자열을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="51e7a-134">The compiler uses the qualification string to find a clear, unambiguous declaration to which it can match the target element reference.</span></span>  
  
 <span data-ttu-id="51e7a-135">응용 프로그램에 동일한 이름을 가진 둘 이상의 프로그래밍 요소에 액세스할 경우 이름 참조를 정규화 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51e7a-135">You might also have to qualify a name reference if your application has access to more than one programming element that has the same name.</span></span> <span data-ttu-id="51e7a-136">예를 들어는 <xref:System.Windows.Forms>및 <xref:System.Web.UI.WebControls>두 네임 스페이스를 포함 한 `Label` 클래스 (<xref:System.Windows.Forms.Label?displayProperty=fullName> 및 <xref:System.Web.UI.WebControls.Label?displayProperty=fullName>).</xref:System.Web.UI.WebControls.Label?displayProperty=fullName> </xref:System.Windows.Forms.Label?displayProperty=fullName> </xref:System.Web.UI.WebControls> </xref:System.Windows.Forms></span><span class="sxs-lookup"><span data-stu-id="51e7a-136">For example, the <xref:System.Windows.Forms> and <xref:System.Web.UI.WebControls> namespaces both contain a `Label` class (<xref:System.Windows.Forms.Label?displayProperty=fullName> and <xref:System.Web.UI.WebControls.Label?displayProperty=fullName>).</span></span> <span data-ttu-id="51e7a-137">응용 프로그램 모두를 사용 하거나 자체 정의 하는 경우 `Label` 클래스를 서로 다른 구별 해야 `Label` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="51e7a-137">If your application uses both, or if it defines its own `Label` class, you must distinguish the different `Label` objects.</span></span> <span data-ttu-id="51e7a-138">변수 선언에 네임 스페이스 또는 가져오기 별칭을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="51e7a-138">Include the namespace or import alias in the variable declaration.</span></span> <span data-ttu-id="51e7a-139">다음 예제에서는 가져오기 별칭을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="51e7a-139">The following example uses the import alias.</span></span>  
  
```vb  
' The following statement must precede all your declarations.  
Imports win = System.Windows.Forms, web = System.Web.UI.WebControls  
' The following statement references the Windows.Forms.Label class.  
Dim winLabel As New win.Label()  
```  
  
## <a name="members-of-other-containing-elements"></a><span data-ttu-id="51e7a-140">포함 된 요소의 다른 멤버</span><span class="sxs-lookup"><span data-stu-id="51e7a-140">Members of Other Containing Elements</span></span>  
 <span data-ttu-id="51e7a-141">다른 클래스 또는 구조체의 공유 되지 않는 멤버를 사용 하면 먼저 변수 또는 클래스 또는 구조체의 인스턴스를 가리키는 식으로 멤버 이름을 정규화 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="51e7a-141">When you use a nonshared member of another class or structure, you must first qualify the member name with a variable or expression that points to an instance of the class or structure.</span></span> <span data-ttu-id="51e7a-142">다음 예에서 `demoClass` 라는 클래스의 인스턴스가 `class1`합니다.</span><span class="sxs-lookup"><span data-stu-id="51e7a-142">In the following example, `demoClass` is an instance of a class named `class1`.</span></span>  
  
```vb  
Dim demoClass As class1 = New class1()  
demoClass.someSub[(argumentlist)]  
```  
  
 <span data-ttu-id="51e7a-143">한정 되지 않는 멤버를 클래스 이름 자체를 사용할 수 없습니다 [공유](../../../../visual-basic/language-reference/modifiers/shared.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="51e7a-143">You cannot use the class name itself to qualify a member that is not [Shared](../../../../visual-basic/language-reference/modifiers/shared.md).</span></span> <span data-ttu-id="51e7a-144">개체 변수에서 인스턴스를 먼저 만들어야 (이 경우 `demoClass`) 변수 이름으로 참조 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="51e7a-144">You must first create an instance in an object variable (in this case `demoClass`) and then reference it by the variable name.</span></span>  
  
 <span data-ttu-id="51e7a-145">클래스 또는 구조체에는 `Shared` 멤버 클래스 또는 구조체 이름 또는 변수 또는 인스턴스를 가리키는 식으로 해당 멤버를 한정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51e7a-145">If a class or structure has a `Shared` member, you can qualify that member either with the class or structure name or with a variable or expression that points to an instance.</span></span>  
  
 <span data-ttu-id="51e7a-146">모듈에는 별도 모든 인스턴스가 및 모든 해당 멤버는 `Shared` 기본적으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="51e7a-146">A module does not have any separate instances, and all its members are `Shared` by default.</span></span> <span data-ttu-id="51e7a-147">따라서 모듈 이름을 모듈 멤버를 정규화 합니다.</span><span class="sxs-lookup"><span data-stu-id="51e7a-147">Therefore, you qualify a module member with the module name.</span></span>  
  
 <span data-ttu-id="51e7a-148">다음 예제에서는 모듈 멤버 프로시저에 대 한 정규화 된 참조를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="51e7a-148">The following example shows qualified references to module member procedures.</span></span> <span data-ttu-id="51e7a-149">이 예제에서는 두 개의 선언한 `Sub` 이라는 프로시저 `perform`, 프로젝트에서 서로 다른 모듈에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51e7a-149">The example declares two `Sub` procedures, both named `perform`, in different modules in a project.</span></span> <span data-ttu-id="51e7a-150">각 모듈 자체 내에서 한정 하지 않고 지정할 수 있지만 다른 곳에서 참조 하는 경우에 한정 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="51e7a-150">Each one can be specified without qualification within its own module but must be qualified if referenced from anywhere else.</span></span> <span data-ttu-id="51e7a-151">마지막에 참조 하기 때문에 `module3` 한정 하지 않으므로 `perform`, 컴파일러는 해당 참조를 확인할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="51e7a-151">Because the final reference in `module3` does not qualify `perform`, the compiler cannot resolve that reference.</span></span>  
  
```vb  
' Assume these three modules are all in the same assembly.  
Module module1  
    Public Sub perform()  
        MsgBox("module1.perform() now returning")  
    End Sub  
End Module  
Module module2  
    Public Sub perform()  
        MsgBox("module2.perform() now returning")  
    End Sub  
    Public Sub doSomething()  
        ' The following statement calls perform in module2, the active module.  
        perform()  
        ' The following statement calls perform in module1.  
        module1.perform()  
    End Sub  
End Module  
Module module3  
    Public Sub callPerform()  
        ' The following statement calls perform in module1.  
        module1.perform()  
        ' The following statement makes an unresolvable name reference  
        ' and therefore generates a COMPILER ERROR.  
        perform() ' INVALID statement  
    End Sub  
End Module  
```  
  
## <a name="references-to-projects"></a><span data-ttu-id="51e7a-152">프로젝트에 대 한 참조</span><span class="sxs-lookup"><span data-stu-id="51e7a-152">References to Projects</span></span>  
 <span data-ttu-id="51e7a-153">사용 하 여 [공용](../../../../visual-basic/language-reference/modifiers/public.md) 다른 프로젝트에 정의 된 요소를 먼저 설정 해야는 *참조* 해당 프로젝트의 어셈블리 또는 형식 라이브러리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51e7a-153">To use [Public](../../../../visual-basic/language-reference/modifiers/public.md) elements defined in another project, you must first set a *reference* to that project's assembly or type library.</span></span> <span data-ttu-id="51e7a-154">참조를 설정 하려면 클릭 **참조 추가** 에 **프로젝트** 메뉴를 사용 하거나 사용 하는 [/reference (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/reference.md) 명령줄 컴파일러 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="51e7a-154">To set a reference, click **Add Reference** on the **Project** menu, or use the [/reference (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/reference.md) command-line compiler option.</span></span>  
  
 <span data-ttu-id="51e7a-155">XML 개체 모델을 사용할 수는 예를 들어는 [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="51e7a-155">For example, you can use the XML object model of the [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)].</span></span> <span data-ttu-id="51e7a-156">대 한 참조를 설정 하는 경우는 <xref:System.Xml>네임 스페이스를 선언 하 고 <xref:System.Xml.XmlDocument>.</xref:System.Xml.XmlDocument> 같은 해당 클래스를 사용 하 여</xref:System.Xml></span><span class="sxs-lookup"><span data-stu-id="51e7a-156">If you set a reference to the <xref:System.Xml> namespace, you can declare and use any of its classes, such as <xref:System.Xml.XmlDocument>.</span></span> <span data-ttu-id="51e7a-157">다음 예제에서는 <xref:System.Xml.XmlDocument>.</xref:System.Xml.XmlDocument></span><span class="sxs-lookup"><span data-stu-id="51e7a-157">The following example uses <xref:System.Xml.XmlDocument>.</span></span>  
  
```vb  
' Assume this project has a reference to System.Xml  
' The following statement creates xDoc as an XML document object.  
Dim xDoc As System.Xml.XmlDocument  
```  
  
## <a name="importing-containing-elements"></a><span data-ttu-id="51e7a-158">요소를 포함 하는 가져오기</span><span class="sxs-lookup"><span data-stu-id="51e7a-158">Importing Containing Elements</span></span>  
 <span data-ttu-id="51e7a-159">사용할 수는 [Imports 문 (.NET Namespace 및 형식)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) 를 *가져올* 모듈이 나 사용 하 여 원하는 클래스를 포함 하는 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="51e7a-159">You can use the [Imports Statement (.NET Namespace and Type)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) to *import* the namespaces that contain the modules or classes that you want to use.</span></span> <span data-ttu-id="51e7a-160">이 이름을 정규화 하지 않고 가져온된 네임 스페이스에 정의 된 요소를 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51e7a-160">This enables you to refer to the elements defined in an imported namespace without fully qualifying their names.</span></span> <span data-ttu-id="51e7a-161">다음 예제에서는 이전 예제를 가져오려면 다시 작성 한는 <xref:System.Xml>네임 스페이스.</xref:System.Xml></span><span class="sxs-lookup"><span data-stu-id="51e7a-161">The following example rewrites the previous example to import the <xref:System.Xml> namespace.</span></span>  
  
```vb  
' Assume this project has a reference to System.Xml  
' The following statement must precede all your declarations.  
Imports System.Xml  
' The following statement creates xDoc as an XML document object.  
Dim xDoc As XmlDocument  
```  
  
 <span data-ttu-id="51e7a-162">또한는 `Imports` 문을 정의할 수는 *가져오기 별칭* 각 가져온된 네임 스페이스에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="51e7a-162">In addition, the `Imports` statement can define an *import alias* for each imported namespace.</span></span> <span data-ttu-id="51e7a-163">소스 코드가 더 간결 하 고 읽기 쉽게 크기 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51e7a-163">This can make the source code shorter and easier to read.</span></span> <span data-ttu-id="51e7a-164">다음 예제에서는 사용 하 여 이전 예제를 다시 작성 `xD` 별칭으로는 <xref:System.Xml>네임 스페이스.</xref:System.Xml></span><span class="sxs-lookup"><span data-stu-id="51e7a-164">The following example rewrites the previous example to use `xD` as an alias for the <xref:System.Xml> namespace.</span></span>  
  
```vb  
' Assume this project has a reference to System.Xml  
' The following statement must precede all your declarations.  
Imports xD = System.Xml  
' The following statement creates xDoc as an XML document object.  
Dim xDoc As xD.XmlDocument  
```  
  
 <span data-ttu-id="51e7a-165">`Imports` 문으로 하지 요소 만들 다른 프로젝트에서 응용 프로그램에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51e7a-165">The `Imports` statement does not make elements from other projects available to your application.</span></span> <span data-ttu-id="51e7a-166">즉, 참조 설정의 위치를 가지 지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="51e7a-166">That is, it does not take the place of setting a reference.</span></span> <span data-ttu-id="51e7a-167">방금 네임 스페이스를 가져오면 해당 네임 스페이스에 정의 된 이름을 정규화 하는 요구 사항을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="51e7a-167">Importing a namespace just removes the requirement to qualify the names defined in that namespace.</span></span>  
  
 <span data-ttu-id="51e7a-168">사용할 수도 있습니다는 `Imports` 을 모듈, 클래스, 구조체 및 열거형을 가져오기 위한 문입니다.</span><span class="sxs-lookup"><span data-stu-id="51e7a-168">You can also use the `Imports` statement to import modules, classes, structures, and enumerations.</span></span> <span data-ttu-id="51e7a-169">다음 한정자 없이 가져온 요소의 멤버를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51e7a-169">You can then use the members of such imported elements without qualification.</span></span> <span data-ttu-id="51e7a-170">그러나 클래스와 클래스 또는 구조체의 인스턴스로 반환 식 또는 변수를 사용 하 여 구조의 공유 되지 않는 멤버 항상 정규화 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="51e7a-170">However, you must always qualify nonshared members of classes and structures with a variable or expression that evaluates to an instance of the class or structure.</span></span>  
  
## <a name="naming-guidelines"></a><span data-ttu-id="51e7a-171">명명 지침</span><span class="sxs-lookup"><span data-stu-id="51e7a-171">Naming Guidelines</span></span>  
 <span data-ttu-id="51e7a-172">동일한 이름을 가진 두 개 이상의 프로그래밍 요소를 정의 하는 경우는 *이름 모호성* 컴파일러에서이 이름에 대 한 참조를 확인 하려고 할 때 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51e7a-172">When you define two or more programming elements that have the same name, a *name ambiguity* can result when the compiler attempts to resolve a reference to that name.</span></span> <span data-ttu-id="51e7a-173">둘 이상의 정의가 두 개는 범위 또는 정의가 없는 범위에 있으면 참조를 해결할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="51e7a-173">If more than one definition is in scope, or if no definition is in scope, the reference is irresolvable.</span></span> <span data-ttu-id="51e7a-174">예를 들어이 도움말 페이지에 "정규화 된 참조 예제"를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="51e7a-174">For an example, see "Qualified Reference Example" on this Help page.</span></span>  
  
 <span data-ttu-id="51e7a-175">모든 요소에 고유한 이름을 지정 하 여 이름 모호성을 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51e7a-175">You can avoid name ambiguity by giving all your elements unique names.</span></span> <span data-ttu-id="51e7a-176">다음 네임 스페이스, 모듈 또는 클래스를 사용 하 여 이름을 한정 하지 않고도 요소에 대 한 참조를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51e7a-176">Then you can make reference to any element without having to qualify its name with a namespace, module, or class.</span></span> <span data-ttu-id="51e7a-177">실수로 잘못 된 요소를 가리키는 가능성이 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51e7a-177">You also reduce the chances of accidentally referring to the wrong element.</span></span>  
  
## <a name="shadowing"></a><span data-ttu-id="51e7a-178">숨기기</span><span class="sxs-lookup"><span data-stu-id="51e7a-178">Shadowing</span></span>  
 <span data-ttu-id="51e7a-179">동일한 이름을 공유 하는 두 가지 프로그래밍 요소를 숨길 수 중 하나, 또는 *섀도*, 다른 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="51e7a-179">When two programming elements share the same name, one of them can hide, or *shadow*, the other one.</span></span> <span data-ttu-id="51e7a-180">숨겨진된 요소는 참조;에 사용할 수 없습니다. 대신 코드에서 숨겨진된 요소 이름을 사용은 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 컴파일러 숨기는 요소를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="51e7a-180">A shadowed element is not available for reference; instead, when your code uses the shadowed element name, the [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler resolves it to the shadowing element.</span></span> <span data-ttu-id="51e7a-181">더 자세한 내용 및 예제를 참조 하십시오. [Visual Basic의 숨김 기능](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="51e7a-181">For a more detailed explanation with examples, see [Shadowing in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51e7a-182">참고 항목</span><span class="sxs-lookup"><span data-stu-id="51e7a-182">See Also</span></span>  
 <span data-ttu-id="51e7a-183">[선언된 요소 이름](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md) </span><span class="sxs-lookup"><span data-stu-id="51e7a-183">[Declared Element Names](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md) </span></span>  
<span data-ttu-id="51e7a-184"> [선언된 요소의 특징](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md) </span><span class="sxs-lookup"><span data-stu-id="51e7a-184"> [Declared Element Characteristics](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md) </span></span>  
<span data-ttu-id="51e7a-185"> [NIB 하는 방법: 프로젝트 속성 및 구성 설정 수정](http://msdn.microsoft.com/en-us/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67) </span><span class="sxs-lookup"><span data-stu-id="51e7a-185"> [NIB How to: Modify Project Properties and Configuration Settings](http://msdn.microsoft.com/en-us/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67) </span></span>  
<span data-ttu-id="51e7a-186"> [변수](../../../../visual-basic/programming-guide/language-features/variables/index.md) </span><span class="sxs-lookup"><span data-stu-id="51e7a-186"> [Variables](../../../../visual-basic/programming-guide/language-features/variables/index.md) </span></span>  
<span data-ttu-id="51e7a-187"> [Imports 문(.NET 네임스페이스 및 형식)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) </span><span class="sxs-lookup"><span data-stu-id="51e7a-187"> [Imports Statement (.NET Namespace and Type)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) </span></span>  
<span data-ttu-id="51e7a-188"> [New 연산자](../../../../visual-basic/language-reference/operators/new-operator.md) </span><span class="sxs-lookup"><span data-stu-id="51e7a-188"> [New Operator](../../../../visual-basic/language-reference/operators/new-operator.md) </span></span>  
<span data-ttu-id="51e7a-189"> [공용](../../../../visual-basic/language-reference/modifiers/public.md)</span><span class="sxs-lookup"><span data-stu-id="51e7a-189"> [Public](../../../../visual-basic/language-reference/modifiers/public.md)</span></span>
