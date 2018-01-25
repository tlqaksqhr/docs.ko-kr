---
title: "-link(C# 컴파일러 옵션)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- /l compiler option [C#]
- /link compiler option [C#]
- -l compiler option [C#]
- EmbedInteropTypes
- l compiler option [C#]
- embed interop types [COM Interop]
- -link compiler option [C#]
- link compiler option [C#]
ms.assetid: 00da70c6-9ea1-43c2-86f2-aa7f26c03475
caps.latest.revision: "13"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 12ba3762a1c514c52b844a30efc9f49648c51b46
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="-link-c-compiler-options"></a><span data-ttu-id="63305-102">-link(C# 컴파일러 옵션)</span><span class="sxs-lookup"><span data-stu-id="63305-102">-link (C# Compiler Options)</span></span>
<span data-ttu-id="63305-103">컴파일러에서 지정된 어셈블리의 COM 형식 정보를 현재 컴파일하고 있는 프로젝트에 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="63305-103">Causes the compiler to make COM type information in the specified assemblies available to the project that you are currently compiling.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63305-104">구문</span><span class="sxs-lookup"><span data-stu-id="63305-104">Syntax</span></span>  
  
```console  
-link:fileList  
// -or-  
-l:fileList  
```  
  
## <a name="arguments"></a><span data-ttu-id="63305-105">인수</span><span class="sxs-lookup"><span data-stu-id="63305-105">Arguments</span></span>  
 `fileList`  
 <span data-ttu-id="63305-106">필수.</span><span class="sxs-lookup"><span data-stu-id="63305-106">Required.</span></span> <span data-ttu-id="63305-107">쉼표로 구분된 어셈블리 파일 이름 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="63305-107">Comma-delimited list of assembly file names.</span></span> <span data-ttu-id="63305-108">파일 이름에 공백이 있으면 이름을 따옴표로 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="63305-108">If the file name contains a space, enclose the name in quotation marks.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="63305-109">설명</span><span class="sxs-lookup"><span data-stu-id="63305-109">Remarks</span></span>  
 <span data-ttu-id="63305-110">`-link` 옵션을 사용하면 포함된 형식 정보가 있는 응용 프로그램을 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63305-110">The `-link` option enables you to deploy an application that has embedded type information.</span></span> <span data-ttu-id="63305-111">그러면 응용 프로그램은 런타임 어셈블리에 대한 참조를 요구하지 않고 포함된 형식 정보를 구현하는 형식을 런타임 어셈블리에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63305-111">The application can then use types in a runtime assembly that implement the embedded type information without requiring a reference to the runtime assembly.</span></span> <span data-ttu-id="63305-112">다양한 버전의 런타임 어셈블리가 게시된 경우 포함된 형식 정보를 포함하는 응용 프로그램은 다시 컴파일하지 않아도 다양한 버전에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63305-112">If various versions of the runtime assembly are published, the application that contains the embedded type information can work with the various versions without having to be recompiled.</span></span> <span data-ttu-id="63305-113">예제를 보려면 [연습: 관리되는 어셈블리의 형식 포함](../../programming-guide/concepts/assemblies-gac/walkthrough-embedding-types-from-managed-assemblies-in-visual-studio.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="63305-113">For an example, see [Walkthrough: Embedding Types from Managed Assemblies](../../programming-guide/concepts/assemblies-gac/walkthrough-embedding-types-from-managed-assemblies-in-visual-studio.md).</span></span>  
  
 <span data-ttu-id="63305-114">`-link` 옵션을 사용하면 COM interop를 사용하여 작업할 때 특히 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="63305-114">Using the `-link` option is especially useful when you are working with COM interop.</span></span> <span data-ttu-id="63305-115">응용 프로그램에 대상 컴퓨터의 PIA(주 interop 어셈블리)가 더 이상 필요하지 않도록 COM 형식을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63305-115">You can embed COM types so that your application no longer requires a primary interop assembly (PIA) on the target computer.</span></span> <span data-ttu-id="63305-116">`-link` 옵션은 참조된 interop 어셈블리의 COM 형식 정보를 컴파일된 결과 코드에 포함하도록 컴파일러에 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="63305-116">The `-link` option instructs the compiler to embed the COM type information from the referenced interop assembly into the resulting compiled code.</span></span> <span data-ttu-id="63305-117">COM 형식은 CLSID(GUID) 값으로 식별됩니다.</span><span class="sxs-lookup"><span data-stu-id="63305-117">The COM type is identified by the CLSID (GUID) value.</span></span> <span data-ttu-id="63305-118">따라서 동일한 CLSID 값을 갖는 동일한 COM 형식이 설치된 대상 컴퓨터에서 응용 프로그램을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63305-118">As a result, your application can run on a target computer that has installed the same COM types with the same CLSID values.</span></span> <span data-ttu-id="63305-119">Microsoft Office를 자동화하는 응용 프로그램이 좋은 예입니다.</span><span class="sxs-lookup"><span data-stu-id="63305-119">Applications that automate Microsoft Office are a good example.</span></span> <span data-ttu-id="63305-120">Office와 같은 응용 프로그램은 일반적으로 여러 버전에서 동일한 CLSID 값을 유지하지 때문에 .NET Framework 4 이상이 대상 컴퓨터에 설치되어 있고 응용 프로그램이 참조된 COM 형식에 포함된 메서드, 속성 또는 이벤트를 사용하는 한 응용 프로그램에서 참조된 COM 형식을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63305-120">Because applications like Office usually keep the same CLSID value across different versions, your application can use the referenced COM types as long as .NET Framework 4 or later is installed on the target computer and your application uses methods, properties, or events that are included in the referenced COM types.</span></span>  
  
 <span data-ttu-id="63305-121">`-link` 옵션은 인터페이스, 구조체 및 대리자만 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="63305-121">The `-link` option embeds only interfaces, structures, and delegates.</span></span> <span data-ttu-id="63305-122">COM 클래스는 포함할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="63305-122">Embedding COM classes is not supported.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="63305-123">코드에서 포함된 COM 형식의 인스턴스를 만드는 경우 적절한 인터페이스를 사용하여 인스턴스를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="63305-123">When you create an instance of an embedded COM type in your code, you must create the instance by using the appropriate interface.</span></span> <span data-ttu-id="63305-124">CoClass를 사용하여 포함된 COM 형식의 인스턴스를 만들려고 하면 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="63305-124">Attempting to create an instance of an embedded COM type by using the CoClass causes an error.</span></span>  
  
 <span data-ttu-id="63305-125">[!INCLUDE[vsprvs](~/includes/vsprvs-md.md)]에서 `-link` 옵션을 설정하려면 어셈블리 참조를 추가하고 `Embed Interop Types` 속성을 **true**로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="63305-125">To set the `-link` option in [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)], add an assembly reference and set the `Embed Interop Types` property to **true**.</span></span> <span data-ttu-id="63305-126">`Embed Interop Types` 속성의 기본값은 **false**입니다.</span><span class="sxs-lookup"><span data-stu-id="63305-126">The default for the `Embed Interop Types` property is **false**.</span></span>  
  
 <span data-ttu-id="63305-127">COM 어셈블리 자체가 또 다른 COM 어셈블리(어셈블리 B)를 참조하는 COM 어셈블리(어셈블리 A)에 연결하는 경우 다음 중 하나에 해당되면 어셈블리 B에도 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="63305-127">If you link to a COM assembly (Assembly A) which itself references another COM assembly (Assembly B), you also have to link to Assembly B if either of the following is true:</span></span>  
  
-   <span data-ttu-id="63305-128">어셈블리 A의 형식은 형식에서 상속되거나 어셈블리 B의 인터페이스를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="63305-128">A type from Assembly A inherits from a type or implements an interface from Assembly B.</span></span>  
  
-   <span data-ttu-id="63305-129">어셈블리 B의 반환 형식이나 매개 변수 형식을 사용하는 필드, 속성, 이벤트 또는 메서드가 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="63305-129">A field, property, event, or method that has a return type or parameter type from Assembly B is invoked.</span></span>  
  
 <span data-ttu-id="63305-130">[-reference](../../../csharp/language-reference/compiler-options/reference-compiler-option.md) 컴파일러 옵션과 마찬가지로 `-link` 컴파일러 옵션은 Csc.rsp 지시 파일을 사용하며, 자주 사용되는 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 어셈블리를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="63305-130">Like the [-reference](../../../csharp/language-reference/compiler-options/reference-compiler-option.md) compiler option, the `-link` compiler option uses the Csc.rsp response file, which references frequently used [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] assemblies.</span></span> <span data-ttu-id="63305-131">컴파일러에서 Csc.rsp 파일을 사용하지 않도록 하려면 [-noconfig](../../../csharp/language-reference/compiler-options/noconfig-compiler-option.md) 컴파일러 옵션을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="63305-131">Use the [-noconfig](../../../csharp/language-reference/compiler-options/noconfig-compiler-option.md) compiler option if you do not want the compiler to use the Csc.rsp file.</span></span>  
  
 <span data-ttu-id="63305-132">`-link`의 약식은 `-l`입니다.</span><span class="sxs-lookup"><span data-stu-id="63305-132">The short form of `-link` is `-l`.</span></span>  
  
## <a name="generics-and-embedded-types"></a><span data-ttu-id="63305-133">제네릭 및 포함된 형식</span><span class="sxs-lookup"><span data-stu-id="63305-133">Generics and Embedded Types</span></span>  
 <span data-ttu-id="63305-134">다음 섹션에서는 interop 형식을 포함하는 응용 프로그램에서 제네릭 형식을 사용할 경우의 제한 사항에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="63305-134">The following sections describe the limitations on using generic types in applications that embed interop types.</span></span>  
  
### <a name="generic-interfaces"></a><span data-ttu-id="63305-135">제네릭 인터페이스</span><span class="sxs-lookup"><span data-stu-id="63305-135">Generic Interfaces</span></span>  
 <span data-ttu-id="63305-136">interop 어셈블리에서 포함되는 제네릭 인터페이스는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="63305-136">Generic interfaces that are embedded from an interop assembly cannot be used.</span></span> <span data-ttu-id="63305-137">다음 예제에서 이를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63305-137">This is shown in the following example.</span></span>  
  
 [!code-csharp[VbLinkCompilerCS#1](../../../csharp/language-reference/compiler-options/codesnippet/CSharp/link-compiler-option_1.cs)]  
  
### <a name="types-that-have-generic-parameters"></a><span data-ttu-id="63305-138">제네릭 매개 변수가 있는 형식</span><span class="sxs-lookup"><span data-stu-id="63305-138">Types That Have Generic Parameters</span></span>  
 <span data-ttu-id="63305-139">형식이 interop 어셈블리에서 포함된 제네릭 매개 변수가 있는 형식은 해당 형식이 외부 어셈블리에서 제공된 경우 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="63305-139">Types that have a generic parameter whose type is embedded from an interop assembly cannot be used if that type is from an external assembly.</span></span> <span data-ttu-id="63305-140">인터페이스에는 이 제한이 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="63305-140">This restriction does not apply to interfaces.</span></span> <span data-ttu-id="63305-141">예를 들어 <xref:Microsoft.Office.Interop.Excel> 어셈블리에 정의된 <xref:Microsoft.Office.Interop.Excel.Range> 인터페이스를 살펴보세요.</span><span class="sxs-lookup"><span data-stu-id="63305-141">For example, consider the <xref:Microsoft.Office.Interop.Excel.Range> interface that is defined in the <xref:Microsoft.Office.Interop.Excel> assembly.</span></span> <span data-ttu-id="63305-142">다음 코드 예제와 같이 라이브러리가 <xref:Microsoft.Office.Interop.Excel> 어셈블리의 interop 형식을 포함하고 형식이 <xref:Microsoft.Office.Interop.Excel.Range> 인터페이스인 매개 변수가 있는 제네릭 형식을 반환하는 메서드를 노출하는 경우 해당 메서드는 제네릭 인터페이스를 반환해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="63305-142">If a library embeds interop types from the <xref:Microsoft.Office.Interop.Excel> assembly and exposes a method that returns a generic type that has a parameter whose type is the <xref:Microsoft.Office.Interop.Excel.Range> interface, that method must return a generic interface, as shown in the following code example.</span></span>  
  
 [!code-csharp[VbLinkCompilerCS#2](../../../csharp/language-reference/compiler-options/codesnippet/CSharp/link-compiler-option_2.cs)]  
[!code-csharp[VbLinkCompilerCS#3](../../../csharp/language-reference/compiler-options/codesnippet/CSharp/link-compiler-option_3.cs)]  
[!code-csharp[VbLinkCompilerCS#4](../../../csharp/language-reference/compiler-options/codesnippet/CSharp/link-compiler-option_4.cs)]  
  
 <span data-ttu-id="63305-143">다음 예제에서 클라이언트 코드는 <xref:System.Collections.IList> 제네릭 인터페이스를 반환하는 메서드를 오류 없이 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63305-143">In the following example, client code can call the method that returns the <xref:System.Collections.IList> generic interface without error.</span></span>  
  
 [!code-csharp[VbLinkCompilerCS#5](../../../csharp/language-reference/compiler-options/codesnippet/CSharp/link-compiler-option_5.cs)]  
  
## <a name="example"></a><span data-ttu-id="63305-144">예</span><span class="sxs-lookup"><span data-stu-id="63305-144">Example</span></span>  
 <span data-ttu-id="63305-145">다음 코드는 소스 파일 `OfficeApp.cs`와 `COMData1.dll` 및 `COMData2.dll`의 참조 어셈블리를 컴파일하여 `OfficeApp.exe`를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="63305-145">The following code compiles source file `OfficeApp.cs` and reference assemblies from `COMData1.dll` and `COMData2.dll` to produce `OfficeApp.exe`.</span></span>  
  
```csharp  
csc -link:COMData1.dll,COMData2.dll -out:OfficeApp.exe OfficeApp.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="63305-146">참고 항목</span><span class="sxs-lookup"><span data-stu-id="63305-146">See Also</span></span>  
 [<span data-ttu-id="63305-147">C# 컴파일러 옵션</span><span class="sxs-lookup"><span data-stu-id="63305-147">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
 [<span data-ttu-id="63305-148">연습: 관리되는 어셈블리의 형식 포함</span><span class="sxs-lookup"><span data-stu-id="63305-148">Walkthrough: Embedding Types from Managed Assemblies</span></span>](../../programming-guide/concepts/assemblies-gac/walkthrough-embedding-types-from-managed-assemblies-in-visual-studio.md)  
 [<span data-ttu-id="63305-149">-reference(C# 컴파일러 옵션)</span><span class="sxs-lookup"><span data-stu-id="63305-149">-reference (C# Compiler Options)</span></span>](../../../csharp/language-reference/compiler-options/reference-compiler-option.md)  
 [<span data-ttu-id="63305-150">-noconfig(C# 컴파일러 옵션)</span><span class="sxs-lookup"><span data-stu-id="63305-150">-noconfig (C# Compiler Options)</span></span>](../../../csharp/language-reference/compiler-options/noconfig-compiler-option.md)  
 [<span data-ttu-id="63305-151">csc.exe를 사용한 명령줄 빌드</span><span class="sxs-lookup"><span data-stu-id="63305-151">Command-line Building With csc.exe</span></span>](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)  
 [<span data-ttu-id="63305-152">상호 운용성 개요</span><span class="sxs-lookup"><span data-stu-id="63305-152">Interoperability Overview</span></span>](../../../csharp/programming-guide/interop/interoperability-overview.md)
