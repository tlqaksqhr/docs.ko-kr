---
title: "특성 개요(Visual Basic)"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 1449f69b-c063-41de-8d89-f0bbdcf96ac6
caps.latest.revision: 4
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 0464de06390a9899cbe312b16cbad41d0b6639eb
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="attributes-overview-visual-basic"></a><span data-ttu-id="c371d-102">특성 개요(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c371d-102">Attributes overview (Visual Basic)</span></span>
<span data-ttu-id="c371d-103">특성은 메타데이터 또는 선언적 정보를 코드(어셈블리, 형식, 메서드, 속성 등)에 연결하는 강력한 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c371d-103">Attributes provide a powerful method of associating metadata, or declarative information, with code (assemblies, types, methods, properties, and so forth).</span></span> <span data-ttu-id="c371d-104">특성이 프로그램 엔터티와 연결되면 *리플렉션*이라는 기법을 사용하여 런타임에 특성이 쿼리될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c371d-104">After an attribute is associated with a program entity, the attribute can be queried at run time by using a technique called *reflection*.</span></span> <span data-ttu-id="c371d-105">자세한 내용은 [리플렉션(Visual Basic)](../../../../visual-basic/programming-guide/concepts/reflection.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c371d-105">For more information, see [Reflection (Visual Basic)](../../../../visual-basic/programming-guide/concepts/reflection.md).</span></span>  
  
 <span data-ttu-id="c371d-106">특성에는 다음과 같은 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c371d-106">Attributes have the following properties:</span></span>  
  
-   <span data-ttu-id="c371d-107">특성은 프로그램에 메타데이터를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="c371d-107">Attributes add metadata to your program.</span></span> <span data-ttu-id="c371d-108">*메타데이터*는 프로그램에 정의된 형식에 대한 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="c371d-108">*Metadata* is information about the types defined in a program.</span></span> <span data-ttu-id="c371d-109">모든 .NET 어셈블리에는 어셈블리에 정의된 형식 및 형식 멤버를 설명하는 지정된 메타데이터 집합이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="c371d-109">All .NET assemblies contain a specified set of metadata that describes the types and type members defined in the assembly.</span></span> <span data-ttu-id="c371d-110">필요한 추가 정보를 지정하는 사용자 지정 특성을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c371d-110">You can add custom attributes to specify any additional information that is required.</span></span> <span data-ttu-id="c371d-111">자세한 내용은 [사용자 지정 특성 만들기(Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/creating-custom-attributes.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c371d-111">For more information, see, [Creating Custom Attributes (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/creating-custom-attributes.md).</span></span>  
  
-   <span data-ttu-id="c371d-112">전체 어셈블리, 모듈 또는 좀 더 작은 프로그램 요소(예: 클래스 및 속성)에 하나 이상의 특성을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c371d-112">You can apply one or more attributes to entire assemblies, modules, or smaller program elements such as classes and properties.</span></span>  
  
-   <span data-ttu-id="c371d-113">메서드 및 속성의 경우와 같은 방식으로 특성은 인수를 수락할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c371d-113">Attributes can accept arguments in the same way as methods and properties.</span></span>  
  
-   <span data-ttu-id="c371d-114">프로그램은 리플렉션을 사용하여 자체 메타데이터 또는 다른 프로그램의 메타데이터를 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c371d-114">Your program can examine its own metadata or the metadata in other programs by using reflection.</span></span> <span data-ttu-id="c371d-115">자세한 내용은 [리플렉션을 사용하여 특성 액세스(Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c371d-115">For more information, see [Accessing Attributes by Using Reflection (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md).</span></span>  
  
## <a name="using-attributes"></a><span data-ttu-id="c371d-116">특성 사용</span><span class="sxs-lookup"><span data-stu-id="c371d-116">Using Attributes</span></span>  
 <span data-ttu-id="c371d-117">특정 특성이 유효한 선언 형식을 제한할 수  있지만 거의 모든 선언에 특성을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c371d-117">Attributes can be placed on most any declaration, though a specific attribute might restrict the types of declarations on which it is valid.</span></span> <span data-ttu-id="c371d-118">Visual Basic의 경우 특성은 꺾쇠 괄호(\<>) 안에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="c371d-118">In Visual Basic, an attribute is enclosed in angle brackets (\< >).</span></span> <span data-ttu-id="c371d-119">특성은 적용되는 요소 바로 앞에 표시되어야 하며 같은 줄에 위치합니다.</span><span class="sxs-lookup"><span data-stu-id="c371d-119">It must appear immediately before the element to which it is applied, on the same line.</span></span>  
  
 <span data-ttu-id="c371d-120">이 예제에서 <xref:System.SerializableAttribute> 특성은 클래스에 특정 특성을 적용하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c371d-120">In this example, the <xref:System.SerializableAttribute> attribute is used to apply a specific characteristic to a class:</span></span>  
  
```vb  
<System.Serializable()> Public Class SampleClass  
    ' Objects of this type can be serialized.  
End Class  
```  
  
 <span data-ttu-id="c371d-121"><xref:System.Runtime.InteropServices.DllImportAttribute> 특성을 사용하는 메서드는 다음과 같이 선언됩니다.</span><span class="sxs-lookup"><span data-stu-id="c371d-121">A method with the attribute <xref:System.Runtime.InteropServices.DllImportAttribute> is declared like this:</span></span>  
  
```vb  
Imports System.Runtime.InteropServices  
```  
  
```vb  
<System.Runtime.InteropServices.DllImport("user32.dll")>   
Sub SampleMethod()  
End Sub  
```  
  
 <span data-ttu-id="c371d-122">둘 이상의 특성을 하나의 선언에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c371d-122">More than one attribute can be placed on a declaration:</span></span>  
  
```vb  
Imports System.Runtime.InteropServices  
```  
  
```vb  
Sub MethodA(<[In](), Out()> ByVal x As Double)  
End Sub  
Sub MethodB(<Out(), [In]()> ByVal x As Double)  
End Sub  
```  
  
 <span data-ttu-id="c371d-123">지정된 엔터티에 대해 일부 특성을 두 번 이상 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c371d-123">Some attributes can be specified more than once for a given entity.</span></span> <span data-ttu-id="c371d-124">이러한 다용도 특성의 예로 <xref:System.Diagnostics.ConditionalAttribute>가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c371d-124">An example of such a multiuse attribute is <xref:System.Diagnostics.ConditionalAttribute>:</span></span>  
  
```vb  
<Conditional("DEBUG"), Conditional("TEST1")>   
Sub TraceMethod()  
End Sub  
```  
  
> [!NOTE]
>  <span data-ttu-id="c371d-125">규칙에 따라 모든 특성 이름은 .NET Framework의 다른 항목과 구분하기 위해 단어 "Attribute"로 끝납니다.</span><span class="sxs-lookup"><span data-stu-id="c371d-125">By convention, all attribute names end with the word "Attribute" to distinguish them from other items in the .NET Framework.</span></span> <span data-ttu-id="c371d-126">그러나 코드에서 특성을 사용하는 경우 특성 접미사를 지정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c371d-126">However, you do not need to specify the attribute suffix when using attributes in code.</span></span> <span data-ttu-id="c371d-127">예를 들어 `[DllImport]`는 `[DllImportAttribute]`와 같지만 `DllImportAttribute`는 .NET Framework에서 특성의 실제 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="c371d-127">For example, `[DllImport]` is equivalent to `[DllImportAttribute]`, but `DllImportAttribute` is the attribute's actual name in the .NET Framework.</span></span>  
  
### <a name="attribute-parameters"></a><span data-ttu-id="c371d-128">특성 매개 변수</span><span class="sxs-lookup"><span data-stu-id="c371d-128">Attribute Parameters</span></span>  
 <span data-ttu-id="c371d-129">많은 특성에는 매개 변수를 위치, 명명되지 않은 또는 명명된 상태의 매개 변수가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c371d-129">Many attributes have parameters, which can be positional, unnamed, or named.</span></span> <span data-ttu-id="c371d-130">모든 위치 매개 변수는 특정 순서로 지정해야 하며 생략할 수 없습니다. 명명된 매개 변수는 선택적이며 순서에 관계 없이 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c371d-130">Any positional parameters must be specified in a certain order and cannot be omitted; named parameters are optional and can be specified in any order.</span></span> <span data-ttu-id="c371d-131">위치 매개 변수가 가장 먼저 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="c371d-131">Positional parameters are specified first.</span></span> <span data-ttu-id="c371d-132">예를 들어 다음 세 가지 특성은 동급입니다.</span><span class="sxs-lookup"><span data-stu-id="c371d-132">For example, these three attributes are equivalent:</span></span>  
  
```vb  
<DllImport("user32.dll")>  
<DllImport("user32.dll", SetLastError:=False, ExactSpelling:=False)>  
<DllImport("user32.dll", ExactSpelling:=False, SetLastError:=False)>  
```  
  
 <span data-ttu-id="c371d-133">첫 번째 매개 변수인 DLL 이름은 위치 매개 변수이므로 항상 맨 먼저 오고 나머지 매개 변수가 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="c371d-133">The first parameter, the DLL name, is positional and always comes first; the others are named.</span></span> <span data-ttu-id="c371d-134">이 경우 명명된 두 매개 변수는 기본적으로 false이므로 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c371d-134">In this case, both named parameters default to false, so they can be omitted.</span></span> <span data-ttu-id="c371d-135">기본 매개 변수 값에 대한 자세한 내용은 개별 특성의 설명서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c371d-135">Refer to the individual attribute's documentation for information on default parameter values.</span></span>  
  
### <a name="attribute-targets"></a><span data-ttu-id="c371d-136">특성 대상</span><span class="sxs-lookup"><span data-stu-id="c371d-136">Attribute Targets</span></span>  
 <span data-ttu-id="c371d-137">특성의 *대상*은 특성이 적용되는 엔터티입니다.</span><span class="sxs-lookup"><span data-stu-id="c371d-137">The *target* of an attribute is the entity to which the attribute applies.</span></span> <span data-ttu-id="c371d-138">예를 들어 특성은 클래스, 특정 메서드 또는 전체 어셈블리에 적용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c371d-138">For example, an attribute may apply to a class, a particular method, or an entire assembly.</span></span> <span data-ttu-id="c371d-139">기본적으로 특성은 그 앞에 오는 요소에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c371d-139">By default, an attribute applies to the element that it precedes.</span></span> <span data-ttu-id="c371d-140">하지만 특성이 메서드, 해당 매개 변수 또는 해당 반환 값 중 어디에 적용될지를 명시적으로 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c371d-140">But you can also explicitly identify, for example, whether an attribute is applied to a method, or to its parameter, or to its return value.</span></span>  
  
 <span data-ttu-id="c371d-141">특성 대상을 명시적으로 식별하려면 다음 구문을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c371d-141">To explicitly identify an attribute target, use the following syntax:</span></span>  
  
```vb  
<target : attribute-list>  
```  
  
 <span data-ttu-id="c371d-142">가능한 `target` 값 목록은 다음 표에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c371d-142">The list of possible `target` values is shown in the following table.</span></span>  
  
|<span data-ttu-id="c371d-143">대상 값</span><span class="sxs-lookup"><span data-stu-id="c371d-143">Target value</span></span>|<span data-ttu-id="c371d-144">적용 대상</span><span class="sxs-lookup"><span data-stu-id="c371d-144">Applies to</span></span>|  
|------------------|----------------|  
|`assembly`|<span data-ttu-id="c371d-145">전체 어셈블리</span><span class="sxs-lookup"><span data-stu-id="c371d-145">Entire assembly</span></span>|  
|`module`|<span data-ttu-id="c371d-146">현재 어셈블리 모듈(Visual Basic 모듈과는 다름)</span><span class="sxs-lookup"><span data-stu-id="c371d-146">Current assembly module (which is different from a Visual Basic Module)</span></span>|  
  
 <span data-ttu-id="c371d-147">다음 예제에서는 어셈블리와 모듈에 특성을 적용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c371d-147">The following example shows how to apply attributes to assemblies and modules.</span></span> <span data-ttu-id="c371d-148">자세한 내용은 [사용자 지정 특성(Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/common-attributes.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c371d-148">For more information, see [Common Attributes (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/common-attributes.md).</span></span>  
  
```vb  
Imports System.Reflection  
<Assembly: AssemblyTitleAttribute("Production assembly 4"),   
Module: CLSCompliant(True)>   
```  
  
## <a name="common-uses-for-attributes"></a><span data-ttu-id="c371d-149">특성의 일반적인 용도</span><span class="sxs-lookup"><span data-stu-id="c371d-149">Common Uses for Attributes</span></span>  
 <span data-ttu-id="c371d-150">다음 목록에는 코드에서 특성이 사용되는 일반적인 경우가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c371d-150">The following list includes a few of the common uses of attributes in code:</span></span>  
  
-   <span data-ttu-id="c371d-151">SOAP 프로토콜을 통해 메서드를 호출할 수 있음을 나타내기 위해 웹 서비스에서 `WebMethod` 특성을 사용하여 메서드에 표시.</span><span class="sxs-lookup"><span data-stu-id="c371d-151">Marking methods using the `WebMethod` attribute in Web services to indicate that the method should be callable over the SOAP protocol.</span></span> <span data-ttu-id="c371d-152">자세한 내용은 <xref:System.Web.Services.WebMethodAttribute>을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="c371d-152">For more information, see <xref:System.Web.Services.WebMethodAttribute>.</span></span>  
  
-   <span data-ttu-id="c371d-153">네이티브 코드와 상호 운용될 경우 메서드 매개 변수를 마샬링하는 방법 설명.</span><span class="sxs-lookup"><span data-stu-id="c371d-153">Describing how to marshal method parameters when interoperating with native code.</span></span> <span data-ttu-id="c371d-154">자세한 내용은 <xref:System.Runtime.InteropServices.MarshalAsAttribute>을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="c371d-154">For more information, see <xref:System.Runtime.InteropServices.MarshalAsAttribute>.</span></span>  
  
-   <span data-ttu-id="c371d-155">클래스, 메서드 및 인터페이스에 대한 COM 속성 설명</span><span class="sxs-lookup"><span data-stu-id="c371d-155">Describing the COM properties for classes, methods, and interfaces.</span></span>  
  
-   <span data-ttu-id="c371d-156"><xref:System.Runtime.InteropServices.DllImportAttribute> 클래스를 사용하는 비관리 코드 호출</span><span class="sxs-lookup"><span data-stu-id="c371d-156">Calling unmanaged code using the <xref:System.Runtime.InteropServices.DllImportAttribute> class.</span></span>  
  
-   <span data-ttu-id="c371d-157">제목, 버전, 설명 또는 상표를 기준으로 어셈블리 설명</span><span class="sxs-lookup"><span data-stu-id="c371d-157">Describing your assembly in terms of title, version, description, or trademark.</span></span>  
  
-   <span data-ttu-id="c371d-158">지속성을 위해 serialize할 클래스의 멤버 설명</span><span class="sxs-lookup"><span data-stu-id="c371d-158">Describing which members of a class to serialize for persistence.</span></span>  
  
-   <span data-ttu-id="c371d-159">XML serialization를 위해 클래스 멤버 및 XML 노드 간을 매핑하는 방법 설명</span><span class="sxs-lookup"><span data-stu-id="c371d-159">Describing how to map between class members and XML nodes for XML serialization.</span></span>  
  
-   <span data-ttu-id="c371d-160">메서드에 대한 보안 요구 사항 설명</span><span class="sxs-lookup"><span data-stu-id="c371d-160">Describing the security requirements for methods.</span></span>  
  
-   <span data-ttu-id="c371d-161">보안을 적용하는 데 사용되는 특징 지정</span><span class="sxs-lookup"><span data-stu-id="c371d-161">Specifying characteristics used to enforce security.</span></span>  
  
-   <span data-ttu-id="c371d-162">코드를 쉽게 디버그할 수 있도록 하기 위해 JIT(Just-In-Time) 컴파일러를 통해 최적화 제어</span><span class="sxs-lookup"><span data-stu-id="c371d-162">Controlling optimizations by the just-in-time (JIT) compiler so the code remains easy to debug.</span></span>  
  
-   <span data-ttu-id="c371d-163">메서드 호출자에 대한 정보 얻기</span><span class="sxs-lookup"><span data-stu-id="c371d-163">Obtaining information about the caller to a method.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="c371d-164">관련 단원</span><span class="sxs-lookup"><span data-stu-id="c371d-164">Related Sections</span></span>  
 <span data-ttu-id="c371d-165">자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c371d-165">For more information, see:</span></span>  
  
-   [<span data-ttu-id="c371d-166">사용자 지정 특성 만들기(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c371d-166">Creating Custom Attributes (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/attributes/creating-custom-attributes.md)  
  
-   [<span data-ttu-id="c371d-167">리플렉션을 사용하여 특성 액세스(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c371d-167">Accessing Attributes by Using Reflection (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md)  
  
-   [<span data-ttu-id="c371d-168">방법: 특성을 사용하여 C/C++ 공용 구조체 만들기(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c371d-168">How to: Create a C/C++ Union by Using Attributes (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/attributes/how-to-create-a-c-cpp-union-by-using-attributes.md)  
  
-   [<span data-ttu-id="c371d-169">일반 특성(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c371d-169">Common Attributes (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/attributes/common-attributes.md)  
  
-   [<span data-ttu-id="c371d-170">호출자 정보(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c371d-170">Caller Information (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/caller-information.md)  
  
## <a name="see-also"></a><span data-ttu-id="c371d-171">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c371d-171">See Also</span></span>  
 <span data-ttu-id="c371d-172">[Visual Basic 프로그래밍 가이드](../../../../visual-basic/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="c371d-172">[Visual Basic Programming Guide](../../../../visual-basic/programming-guide/index.md) </span></span>  
 <span data-ttu-id="c371d-173">[리플렉션(Visual Basic)](../../../../visual-basic/programming-guide/concepts/reflection.md) </span><span class="sxs-lookup"><span data-stu-id="c371d-173">[Reflection (Visual Basic)](../../../../visual-basic/programming-guide/concepts/reflection.md) </span></span>  
 [<span data-ttu-id="c371d-174">특성</span><span class="sxs-lookup"><span data-stu-id="c371d-174">Attributes</span></span>](https://msdn.microsoft.com/library/5x6cd29c)

