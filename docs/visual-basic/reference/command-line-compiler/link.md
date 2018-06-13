---
title: -링크 (Visual Basic)
ms.date: 03/10/2018
helpviewer_keywords:
- l compiler option [Visual Basic]
- EmbedInteropTypes
- embed interop types [COM Interop]
- -link compiler option [Visual Basic]
- /link compiler option [Visual Basic]
- link compiler option [Visual Basic]
- -l compiler option [Visual Basic]
- /l compiler option [Visual Basic]
ms.assetid: 1885f24a-86f5-486c-a064-9fb7e455ccec
ms.openlocfilehash: 95c528c4d686c44d0d77d1f55833be75ab14f8bf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33656271"
---
# <a name="-link-visual-basic"></a><span data-ttu-id="9a6ba-102">-링크 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9a6ba-102">-link (Visual Basic)</span></span>
<span data-ttu-id="9a6ba-103">컴파일러에서 지정된 어셈블리의 COM 형식 정보를 현재 컴파일하고 있는 프로젝트에 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a6ba-103">Causes the compiler to make COM type information in the specified assemblies available to the project that you are currently compiling.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a6ba-104">구문</span><span class="sxs-lookup"><span data-stu-id="9a6ba-104">Syntax</span></span>  
  
```  
-link:fileList  
' -or-  
-l:fileList  
```  
  
## <a name="arguments"></a><span data-ttu-id="9a6ba-105">인수</span><span class="sxs-lookup"><span data-stu-id="9a6ba-105">Arguments</span></span>  
  
|<span data-ttu-id="9a6ba-106">용어</span><span class="sxs-lookup"><span data-stu-id="9a6ba-106">Term</span></span>|<span data-ttu-id="9a6ba-107">정의</span><span class="sxs-lookup"><span data-stu-id="9a6ba-107">Definition</span></span>|  
|---|---|  
|`fileList`|<span data-ttu-id="9a6ba-108">필수.</span><span class="sxs-lookup"><span data-stu-id="9a6ba-108">Required.</span></span> <span data-ttu-id="9a6ba-109">쉼표로 구분된 어셈블리 파일 이름 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="9a6ba-109">Comma-delimited list of assembly file names.</span></span> <span data-ttu-id="9a6ba-110">파일 이름에 공백이 있으면 이름을 따옴표로 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="9a6ba-110">If the file name contains a space, enclose the name in quotation marks.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9a6ba-111">설명</span><span class="sxs-lookup"><span data-stu-id="9a6ba-111">Remarks</span></span>  
 <span data-ttu-id="9a6ba-112">`-link` 옵션을 사용하면 포함된 형식 정보가 있는 응용 프로그램을 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a6ba-112">The `-link` option enables you to deploy an application that has embedded type information.</span></span> <span data-ttu-id="9a6ba-113">그러면 응용 프로그램은 런타임 어셈블리에 대한 참조를 요구하지 않고 포함된 형식 정보를 구현하는 형식을 런타임 어셈블리에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a6ba-113">The application can then use types in a runtime assembly that implement the embedded type information without requiring a reference to the runtime assembly.</span></span> <span data-ttu-id="9a6ba-114">다양한 버전의 런타임 어셈블리가 게시된 경우 포함된 형식 정보를 포함하는 응용 프로그램은 다시 컴파일하지 않아도 다양한 버전에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a6ba-114">If various versions of the runtime assembly are published, the application that contains the embedded type information can work with the various versions without having to be recompiled.</span></span> <span data-ttu-id="9a6ba-115">예제를 보려면 [연습: 관리되는 어셈블리의 형식 포함](http://msdn.microsoft.com/library/b28ec92c-1867-4847-95c0-61adfe095e21)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9a6ba-115">For an example, see [Walkthrough: Embedding Types from Managed Assemblies](http://msdn.microsoft.com/library/b28ec92c-1867-4847-95c0-61adfe095e21).</span></span>  
  
 <span data-ttu-id="9a6ba-116">`-link` 옵션을 사용하면 COM interop를 사용하여 작업할 때 특히 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="9a6ba-116">Using the `-link` option is especially useful when you are working with COM interop.</span></span> <span data-ttu-id="9a6ba-117">응용 프로그램에 대상 컴퓨터의 PIA(주 interop 어셈블리)가 더 이상 필요하지 않도록 COM 형식을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a6ba-117">You can embed COM types so that your application no longer requires a primary interop assembly (PIA) on the target computer.</span></span> <span data-ttu-id="9a6ba-118">`-link` 옵션은 참조된 interop 어셈블리의 COM 형식 정보를 컴파일된 결과 코드에 포함하도록 컴파일러에 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="9a6ba-118">The `-link` option instructs the compiler to embed the COM type information from the referenced interop assembly into the resulting compiled code.</span></span> <span data-ttu-id="9a6ba-119">COM 형식은 CLSID(GUID) 값으로 식별됩니다.</span><span class="sxs-lookup"><span data-stu-id="9a6ba-119">The COM type is identified by the CLSID (GUID) value.</span></span> <span data-ttu-id="9a6ba-120">따라서 동일한 CLSID 값을 갖는 동일한 COM 형식이 설치된 대상 컴퓨터에서 응용 프로그램을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a6ba-120">As a result, your application can run on a target computer that has installed the same COM types with the same CLSID values.</span></span> <span data-ttu-id="9a6ba-121">Microsoft Office를 자동화하는 응용 프로그램이 좋은 예입니다.</span><span class="sxs-lookup"><span data-stu-id="9a6ba-121">Applications that automate Microsoft Office are a good example.</span></span> <span data-ttu-id="9a6ba-122">Office와 같은 응용 프로그램은 일반적으로 여러 버전에서 동일한 CLSID 값을 유지하지 때문에 .NET Framework 4 이상이 대상 컴퓨터에 설치되어 있고 응용 프로그램이 참조된 COM 형식에 포함된 메서드, 속성 또는 이벤트를 사용하는 한 응용 프로그램에서 참조된 COM 형식을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a6ba-122">Because applications like Office usually keep the same CLSID value across different versions, your application can use the referenced COM types as long as .NET Framework 4 or later is installed on the target computer and your application uses methods, properties, or events that are included in the referenced COM types.</span></span>  
  
 <span data-ttu-id="9a6ba-123">`-link` 옵션은 인터페이스, 구조체 및 대리자만 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="9a6ba-123">The `-link` option embeds only interfaces, structures, and delegates.</span></span> <span data-ttu-id="9a6ba-124">COM 클래스는 포함할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9a6ba-124">Embedding COM classes is not supported.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9a6ba-125">코드에서 포함된 COM 형식의 인스턴스를 만드는 경우 적절한 인터페이스를 사용하여 인스턴스를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a6ba-125">When you create an instance of an embedded COM type in your code, you must create the instance by using the appropriate interface.</span></span> <span data-ttu-id="9a6ba-126">CoClass를 사용하여 포함된 COM 형식의 인스턴스를 만들려고 하면 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="9a6ba-126">Attempting to create an instance of an embedded COM type by using the CoClass causes an error.</span></span>  
  
 <span data-ttu-id="9a6ba-127">Visual Studio에서 `-link` 옵션을 설정하려면 어셈블리 참조를 추가하고 `Embed Interop Types` 속성을 **true**로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9a6ba-127">To set the `-link` option in Visual Studio, add an assembly reference and set the `Embed Interop Types` property to **true**.</span></span> <span data-ttu-id="9a6ba-128">`Embed Interop Types` 속성의 기본값은 **false**입니다.</span><span class="sxs-lookup"><span data-stu-id="9a6ba-128">The default for the `Embed Interop Types` property is **false**.</span></span>  
  
 <span data-ttu-id="9a6ba-129">COM 어셈블리 자체가 또 다른 COM 어셈블리(어셈블리 B)를 참조하는 COM 어셈블리(어셈블리 A)에 연결하는 경우 다음 중 하나에 해당되면 어셈블리 B에도 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a6ba-129">If you link to a COM assembly (Assembly A) which itself references another COM assembly (Assembly B), you also have to link to Assembly B if either of the following is true:</span></span>  
  
-   <span data-ttu-id="9a6ba-130">어셈블리 A의 형식은 형식에서 상속되거나 어셈블리 B의 인터페이스를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="9a6ba-130">A type from Assembly A inherits from a type or implements an interface from Assembly B.</span></span>  
  
-   <span data-ttu-id="9a6ba-131">어셈블리 B의 반환 형식이나 매개 변수 형식을 사용하는 필드, 속성, 이벤트 또는 메서드가 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="9a6ba-131">A field, property, event, or method that has a return type or parameter type from Assembly B is invoked.</span></span>  
  
 <span data-ttu-id="9a6ba-132">사용 하 여 [-libpath](../../../visual-basic/reference/command-line-compiler/libpath.md) 어셈블리 참조 중 하나 이상이 있는 디렉터리를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a6ba-132">Use [-libpath](../../../visual-basic/reference/command-line-compiler/libpath.md) to specify the directory in which one or more of your assembly references is located.</span></span>  
  
 <span data-ttu-id="9a6ba-133">와 같은 [/참조](../../../visual-basic/reference/command-line-compiler/reference.md) 컴파일러 옵션은 `-link` 컴파일러 옵션 참조 자주 사용 되는 Vbc.rsp 지시 파일을 사용 하 여 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 어셈블리입니다.</span><span class="sxs-lookup"><span data-stu-id="9a6ba-133">Like the [/reference](../../../visual-basic/reference/command-line-compiler/reference.md) compiler option, the `-link` compiler option uses the Vbc.rsp response file, which references frequently used [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] assemblies.</span></span> <span data-ttu-id="9a6ba-134">사용 하 여는 [-noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md) Vbc.rsp 파일을 사용 하도록 컴파일러에 하지 않을 경우 컴파일러 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="9a6ba-134">Use the [-noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md) compiler option if you do not want the compiler to use the Vbc.rsp file.</span></span>  
  
 <span data-ttu-id="9a6ba-135">`-link`의 약식은 `-l`입니다.</span><span class="sxs-lookup"><span data-stu-id="9a6ba-135">The short form of `-link` is `-l`.</span></span>  
  
## <a name="generics-and-embedded-types"></a><span data-ttu-id="9a6ba-136">제네릭 및 포함된 형식</span><span class="sxs-lookup"><span data-stu-id="9a6ba-136">Generics and Embedded Types</span></span>  
 <span data-ttu-id="9a6ba-137">다음 섹션에서는 interop 형식을 포함하는 응용 프로그램에서 제네릭 형식을 사용할 경우의 제한 사항에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9a6ba-137">The following sections describe the limitations on using generic types in applications that embed interop types.</span></span>  
  
### <a name="generic-interfaces"></a><span data-ttu-id="9a6ba-138">제네릭 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9a6ba-138">Generic Interfaces</span></span>  
 <span data-ttu-id="9a6ba-139">interop 어셈블리에서 포함되는 제네릭 인터페이스는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9a6ba-139">Generic interfaces that are embedded from an interop assembly cannot be used.</span></span> <span data-ttu-id="9a6ba-140">다음 예제에서 이를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a6ba-140">This is shown in the following example.</span></span>  
  
 [!code-vb[VbLinkCompiler#1](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/link_1.vb)]  
  
### <a name="types-that-have-generic-parameters"></a><span data-ttu-id="9a6ba-141">제네릭 매개 변수가 있는 형식</span><span class="sxs-lookup"><span data-stu-id="9a6ba-141">Types That Have Generic Parameters</span></span>  
 <span data-ttu-id="9a6ba-142">형식이 interop 어셈블리에서 포함된 제네릭 매개 변수가 있는 형식은 해당 형식이 외부 어셈블리에서 제공된 경우 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9a6ba-142">Types that have a generic parameter whose type is embedded from an interop assembly cannot be used if that type is from an external assembly.</span></span> <span data-ttu-id="9a6ba-143">인터페이스에는 이 제한이 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9a6ba-143">This restriction does not apply to interfaces.</span></span> <span data-ttu-id="9a6ba-144">예를 들어 <xref:Microsoft.Office.Interop.Excel> 어셈블리에 정의된 <xref:Microsoft.Office.Interop.Excel.Range> 인터페이스를 살펴보세요.</span><span class="sxs-lookup"><span data-stu-id="9a6ba-144">For example, consider the <xref:Microsoft.Office.Interop.Excel.Range> interface that is defined in the <xref:Microsoft.Office.Interop.Excel> assembly.</span></span> <span data-ttu-id="9a6ba-145">다음 코드 예제와 같이 라이브러리가 <xref:Microsoft.Office.Interop.Excel> 어셈블리의 interop 형식을 포함하고 형식이 <xref:Microsoft.Office.Interop.Excel.Range> 인터페이스인 매개 변수가 있는 제네릭 형식을 반환하는 메서드를 노출하는 경우 해당 메서드는 제네릭 인터페이스를 반환해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a6ba-145">If a library embeds interop types from the <xref:Microsoft.Office.Interop.Excel> assembly and exposes a method that returns a generic type that has a parameter whose type is the <xref:Microsoft.Office.Interop.Excel.Range> interface, that method must return a generic interface, as shown in the following code example.</span></span>  
  
 [!code-vb[VbLinkCompiler#2](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/link_2.vb)]  
[!code-vb[VbLinkCompiler#3](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/link_3.vb)]  
[!code-vb[VbLinkCompiler#4](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/link_4.vb)]  
  
 <span data-ttu-id="9a6ba-146">다음 예제에서 클라이언트 코드는 <xref:System.Collections.IList> 제네릭 인터페이스를 반환하는 메서드를 오류 없이 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a6ba-146">In the following example, client code can call the method that returns the <xref:System.Collections.IList> generic interface without error.</span></span>  
  
 [!code-vb[VbLinkCompiler#5](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/link_5.vb)]  
  
## <a name="example"></a><span data-ttu-id="9a6ba-147">예제</span><span class="sxs-lookup"><span data-stu-id="9a6ba-147">Example</span></span>  
 <span data-ttu-id="9a6ba-148">다음 명령줄은 소스 파일을 컴파일하 `OfficeApp.vb` 의 어셈블리를 참조 하 고 `COMData1.dll` 및 `COMData2.dll` 되려면 `OfficeApp.exe`합니다.</span><span class="sxs-lookup"><span data-stu-id="9a6ba-148">The following command line compiles source file `OfficeApp.vb` and reference assemblies from `COMData1.dll` and `COMData2.dll` to produce `OfficeApp.exe`.</span></span>  
  
```console  
vbc -link:COMData1.dll,COMData2.dll /out:OfficeApp.exe OfficeApp.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="9a6ba-149">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9a6ba-149">See Also</span></span>  
 [<span data-ttu-id="9a6ba-150">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="9a6ba-150">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="9a6ba-151">연습: 관리되는 어셈블리의 형식 포함</span><span class="sxs-lookup"><span data-stu-id="9a6ba-151">Walkthrough: Embedding Types from Managed Assemblies</span></span>](http://msdn.microsoft.com/library/b28ec92c-1867-4847-95c0-61adfe095e21)  
 [<span data-ttu-id="9a6ba-152">-참조 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9a6ba-152">-reference (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/reference.md)  
 [<span data-ttu-id="9a6ba-153">-noconfig</span><span class="sxs-lookup"><span data-stu-id="9a6ba-153">-noconfig</span></span>](../../../visual-basic/reference/command-line-compiler/noconfig.md)  
 [<span data-ttu-id="9a6ba-154">-libpath</span><span class="sxs-lookup"><span data-stu-id="9a6ba-154">-libpath</span></span>](../../../visual-basic/reference/command-line-compiler/libpath.md)  
 [<span data-ttu-id="9a6ba-155">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="9a6ba-155">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [<span data-ttu-id="9a6ba-156">COM Interop 소개</span><span class="sxs-lookup"><span data-stu-id="9a6ba-156">Introduction to COM Interop</span></span>](../../../visual-basic/programming-guide/com-interop/introduction-to-com-interop.md)
