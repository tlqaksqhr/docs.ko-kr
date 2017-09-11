---
title: "/link (Visual Basic) | Microsoft 문서"
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
- l compiler option [Visual Basic]
- EmbedInteropTypes
- embed interop types [COM Interop]
- -link compiler option [Visual Basic]
- /link compiler option [Visual Basic]
- link compiler option [Visual Basic]
- -l compiler option [Visual Basic]
- /l compiler option [Visual Basic]
ms.assetid: 1885f24a-86f5-486c-a064-9fb7e455ccec
caps.latest.revision: 27
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
ms.openlocfilehash: 71ecefc898ca37cbf7299d97518e1ce2547a58da
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="link-visual-basic"></a><span data-ttu-id="cf8c1-102">/link(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cf8c1-102">/link (Visual Basic)</span></span>
<span data-ttu-id="cf8c1-103">현재 컴파일 중인 프로젝트에 사용할 수 있는 지정된 된 어셈블리에서 COM 형식 정보를 확인 하는 컴파일러가 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf8c1-103">Causes the compiler to make COM type information in the specified assemblies available to the project that you are currently compiling.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf8c1-104">구문</span><span class="sxs-lookup"><span data-stu-id="cf8c1-104">Syntax</span></span>  
  
```  
/link:fileList  
' -or-  
/l:fileList  
```  
  
## <a name="arguments"></a><span data-ttu-id="cf8c1-105">인수</span><span class="sxs-lookup"><span data-stu-id="cf8c1-105">Arguments</span></span>  
  
|<span data-ttu-id="cf8c1-106">용어</span><span class="sxs-lookup"><span data-stu-id="cf8c1-106">Term</span></span>|<span data-ttu-id="cf8c1-107">정의</span><span class="sxs-lookup"><span data-stu-id="cf8c1-107">Definition</span></span>|  
|---|---|  
|`fileList`|<span data-ttu-id="cf8c1-108">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="cf8c1-108">Required.</span></span> <span data-ttu-id="cf8c1-109">어셈블리 파일 이름의 쉼표로 구분 된 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="cf8c1-109">Comma-delimited list of assembly file names.</span></span> <span data-ttu-id="cf8c1-110">파일 이름에 공백이 있으면 이름을 따옴표로 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="cf8c1-110">If the file name contains a space, enclose the name in quotation marks.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cf8c1-111">설명</span><span class="sxs-lookup"><span data-stu-id="cf8c1-111">Remarks</span></span>  
 <span data-ttu-id="cf8c1-112">`/link` 옵션을 사용 하면 형식 정보를 포함 하는 응용 프로그램을 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf8c1-112">The `/link` option enables you to deploy an application that has embedded type information.</span></span> <span data-ttu-id="cf8c1-113">응용 프로그램 런타임 어셈블리에 대 한 참조를 요구 하지 않고 포함된 된 형식 정보를 구현 하는 런타임 어셈블리의 형식을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf8c1-113">The application can then use types in a runtime assembly that implement the embedded type information without requiring a reference to the runtime assembly.</span></span> <span data-ttu-id="cf8c1-114">런타임 어셈블리의 여러 버전을 게시 하는 포함된 된 형식 정보를 포함 하는 응용 프로그램을 다시 컴파일하지 않고도 다양 한 버전 작업할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf8c1-114">If various versions of the runtime assembly are published, the application that contains the embedded type information can work with the various versions without having to be recompiled.</span></span> <span data-ttu-id="cf8c1-115">예를 들어 참조 [연습: 관리 되는 어셈블리의 형식 포함](http://msdn.microsoft.com/library/b28ec92c-1867-4847-95c0-61adfe095e21)합니다.</span><span class="sxs-lookup"><span data-stu-id="cf8c1-115">For an example, see [Walkthrough: Embedding Types from Managed Assemblies](http://msdn.microsoft.com/library/b28ec92c-1867-4847-95c0-61adfe095e21).</span></span>  
  
 <span data-ttu-id="cf8c1-116">사용 하 여 `/link` 옵션은 COM interop를 사용 하 여 작업할 때 특히 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf8c1-116">Using the `/link` option is especially useful when you are working with COM interop.</span></span> <span data-ttu-id="cf8c1-117">응용 프로그램에 더 이상 주 interop 어셈블리를 PIA ()는 대상 컴퓨터에 필요한 수 있도록 COM 형식을 포함할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cf8c1-117">You can embed COM types so that your application no longer requires a primary interop assembly (PIA) on the target computer.</span></span> <span data-ttu-id="cf8c1-118">`/link` 옵션 컴파일러가 결과 컴파일된 코드에 참조 된 interop 어셈블리에서 COM 형식 정보를 포함 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf8c1-118">The `/link` option instructs the compiler to embed the COM type information from the referenced interop assembly into the resulting compiled code.</span></span> <span data-ttu-id="cf8c1-119">COM 형식이 CLSID (GUID) 값으로 식별 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf8c1-119">The COM type is identified by the CLSID (GUID) value.</span></span> <span data-ttu-id="cf8c1-120">결과적으로, 응용 프로그램가 같은 COM 형식이 같은 CLSID 값으로 설치 하는 대상 컴퓨터에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf8c1-120">As a result, your application can run on a target computer that has installed the same COM types with the same CLSID values.</span></span> <span data-ttu-id="cf8c1-121">Microsoft Office를 자동화 하는 응용 프로그램은 좋은 예입니다.</span><span class="sxs-lookup"><span data-stu-id="cf8c1-121">Applications that automate Microsoft Office are a good example.</span></span> <span data-ttu-id="cf8c1-122">Office와 같은 응용 프로그램은 일반적으로 다양 한 버전에서 같은 CLSID 값 유지, 때문에 메서드, 속성 또는 이벤트가 참조 하는 COM 형식에 포함 된 응용 프로그램이 사용 하 고 대상 컴퓨터에.NET Framework 4 이상이 설치 되어 응용 프로그램 참조 된 COM 형식을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf8c1-122">Because applications like Office usually keep the same CLSID value across different versions, your application can use the referenced COM types as long as .NET Framework 4 or later is installed on the target computer and your application uses methods, properties, or events that are included in the referenced COM types.</span></span>  
  
 <span data-ttu-id="cf8c1-123">`/link` 옵션 인터페이스, 구조 및 대리자를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf8c1-123">The `/link` option embeds only interfaces, structures, and delegates.</span></span> <span data-ttu-id="cf8c1-124">COM 클래스를 포함 하는 것은 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cf8c1-124">Embedding COM classes is not supported.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cf8c1-125">코드에 포함 된 COM 형식의 인스턴스를 만들 때 적절 한 인터페이스를 사용 하 여 인스턴스를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf8c1-125">When you create an instance of an embedded COM type in your code, you must create the instance by using the appropriate interface.</span></span> <span data-ttu-id="cf8c1-126">CoClass를 사용 하 여 포함 된 COM 형식의 인스턴스를 만들려고 하면 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf8c1-126">Attempting to create an instance of an embedded COM type by using the CoClass causes an error.</span></span>  
  
 <span data-ttu-id="cf8c1-127">설정 하는 `/link` 옵션 [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)], 어셈블리 참조를 추가 하 고 설정의 `Embed Interop Types` 속성을 **true**합니다.</span><span class="sxs-lookup"><span data-stu-id="cf8c1-127">To set the `/link` option in [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)], add an assembly reference and set the `Embed Interop Types` property to **true**.</span></span> <span data-ttu-id="cf8c1-128">기본값은 `Embed Interop Types` 속성은 **false**합니다.</span><span class="sxs-lookup"><span data-stu-id="cf8c1-128">The default for the `Embed Interop Types` property is **false**.</span></span>  
  
 <span data-ttu-id="cf8c1-129">COM 어셈블리 (어셈블리 A)에 연결 되는 경우 다른 COM 어셈블리 (어셈블리 B)를 참조 하는데, 다음 중 하나에 해당 하는 경우 어셈블리 B에 연결 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf8c1-129">If you link to a COM assembly (Assembly A) which itself references another COM assembly (Assembly B), you also have to link to Assembly B if either of the following is true:</span></span>  
  
-   <span data-ttu-id="cf8c1-130">어셈블리 A에서에서 형식을 형식에서 상속 되거나 어셈블리 B의 인터페이스 구현</span><span class="sxs-lookup"><span data-stu-id="cf8c1-130">A type from Assembly A inherits from a type or implements an interface from Assembly B.</span></span>  
  
-   <span data-ttu-id="cf8c1-131">필드, 속성, 이벤트 또는 어셈블리 B의 반환 형식이 나 매개 변수 형식의 변수가 있는 메서드가 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf8c1-131">A field, property, event, or method that has a return type or parameter type from Assembly B is invoked.</span></span>  
  
 <span data-ttu-id="cf8c1-132">사용 하 여 [/libpath](../../../visual-basic/reference/command-line-compiler/libpath.md) 어셈블리 참조 중 하나 이상이 있는 디렉터리를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf8c1-132">Use [/libpath](../../../visual-basic/reference/command-line-compiler/libpath.md) to specify the directory in which one or more of your assembly references is located.</span></span>  
  
 <span data-ttu-id="cf8c1-133">마찬가지로 [/reference](../../../visual-basic/reference/command-line-compiler/reference.md) 컴파일러 옵션은 `/link` 컴파일러 옵션 참조 자주 사용 되는 Vbc.rsp 지시 파일을 사용 하 여 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] 어셈블리.</span><span class="sxs-lookup"><span data-stu-id="cf8c1-133">Like the [/reference](../../../visual-basic/reference/command-line-compiler/reference.md) compiler option, the `/link` compiler option uses the Vbc.rsp response file, which references frequently used [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] assemblies.</span></span> <span data-ttu-id="cf8c1-134">사용 하 여 [/noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md) Vbc.rsp 파일을 사용 하도록 컴파일러에 원하지 않는 경우 컴파일러 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="cf8c1-134">Use the [/noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md) compiler option if you do not want the compiler to use the Vbc.rsp file.</span></span>  
  
 <span data-ttu-id="cf8c1-135">약식 `/link` 는 `/l`합니다.</span><span class="sxs-lookup"><span data-stu-id="cf8c1-135">The short form of `/link` is `/l`.</span></span>  
  
## <a name="generics-and-embedded-types"></a><span data-ttu-id="cf8c1-136">제네릭 및 포함 된 형식</span><span class="sxs-lookup"><span data-stu-id="cf8c1-136">Generics and Embedded Types</span></span>  
 <span data-ttu-id="cf8c1-137">다음 섹션에서는 interop 형식 포함 하는 응용 프로그램에서 제네릭 형식 사용에 제한 사항에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf8c1-137">The following sections describe the limitations on using generic types in applications that embed interop types.</span></span>  
  
### <a name="generic-interfaces"></a><span data-ttu-id="cf8c1-138">제네릭 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cf8c1-138">Generic Interfaces</span></span>  
 <span data-ttu-id="cf8c1-139">Interop 어셈블리를 포함 하는 제네릭 인터페이스를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cf8c1-139">Generic interfaces that are embedded from an interop assembly cannot be used.</span></span> <span data-ttu-id="cf8c1-140">다음 예제에서 이를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf8c1-140">This is shown in the following example.</span></span>  
  
 <span data-ttu-id="cf8c1-141">[!code-vb[VbLinkCompiler #&1;](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/link_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="cf8c1-141">[!code-vb[VbLinkCompiler#1](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/link_1.vb)]</span></span>  
  
### <a name="types-that-have-generic-parameters"></a><span data-ttu-id="cf8c1-142">제네릭 매개 변수가 있는 형식</span><span class="sxs-lookup"><span data-stu-id="cf8c1-142">Types That Have Generic Parameters</span></span>  
 <span data-ttu-id="cf8c1-143">Interop 어셈블리에서 해당 형식이 포함 된 제네릭 매개 변수를 가진 형식에 사용할 수 없습니다 경우 외부 어셈블리의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="cf8c1-143">Types that have a generic parameter whose type is embedded from an interop assembly cannot be used if that type is from an external assembly.</span></span> <span data-ttu-id="cf8c1-144">인터페이스에는이 제한이 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cf8c1-144">This restriction does not apply to interfaces.</span></span> <span data-ttu-id="cf8c1-145">예를 들어는 <xref:Microsoft.Office.Interop.Excel.Range>에 정의 된 인터페이스는 <xref:Microsoft.Office.Interop.Excel>어셈블리.</xref:Microsoft.Office.Interop.Excel> </xref:Microsoft.Office.Interop.Excel.Range></span><span class="sxs-lookup"><span data-stu-id="cf8c1-145">For example, consider the <xref:Microsoft.Office.Interop.Excel.Range> interface that is defined in the <xref:Microsoft.Office.Interop.Excel> assembly.</span></span> <span data-ttu-id="cf8c1-146">라이브러리의 interop 형식을 포함 하는 경우는 <xref:Microsoft.Office.Interop.Excel>어셈블리 및 형식을 갖는 매개 변수가 있는 제네릭 형식을 반환 하는 메서드는 노출 된 <xref:Microsoft.Office.Interop.Excel.Range>인터페이스 메서드에 다음 코드 예제와 같이 제네릭 인터페이스를 반환 해야 함을.</xref:Microsoft.Office.Interop.Excel.Range> </xref:Microsoft.Office.Interop.Excel></span><span class="sxs-lookup"><span data-stu-id="cf8c1-146">If a library embeds interop types from the <xref:Microsoft.Office.Interop.Excel> assembly and exposes a method that returns a generic type that has a parameter whose type is the <xref:Microsoft.Office.Interop.Excel.Range> interface, that method must return a generic interface, as shown in the following code example.</span></span>  
  
 <span data-ttu-id="cf8c1-147">[!code-vb[VbLinkCompiler #&2;](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/link_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="cf8c1-147">[!code-vb[VbLinkCompiler#2](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/link_2.vb)]</span></span>  
<span data-ttu-id="cf8c1-148">[!code-vb[VbLinkCompiler #&3;](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/link_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="cf8c1-148">[!code-vb[VbLinkCompiler#3](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/link_3.vb)]</span></span>  
<span data-ttu-id="cf8c1-149">[!code-vb[VbLinkCompiler #&4;](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/link_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="cf8c1-149">[!code-vb[VbLinkCompiler#4](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/link_4.vb)]</span></span>  
  
 <span data-ttu-id="cf8c1-150">다음 예제에서는 클라이언트 코드를 반환 하는 메서드를 호출할 수는 <xref:System.Collections.IList>오류 없이 제네릭 인터페이스.</xref:System.Collections.IList></span><span class="sxs-lookup"><span data-stu-id="cf8c1-150">In the following example, client code can call the method that returns the <xref:System.Collections.IList> generic interface without error.</span></span>  
  
 <span data-ttu-id="cf8c1-151">[!code-vb[VbLinkCompiler #&5;](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/link_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="cf8c1-151">[!code-vb[VbLinkCompiler#5](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/link_5.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="cf8c1-152">예제</span><span class="sxs-lookup"><span data-stu-id="cf8c1-152">Example</span></span>  
 <span data-ttu-id="cf8c1-153">다음 코드는 소스 파일을 컴파일하 `OfficeApp.vb` 의 어셈블리를 참조 하 고 `COMData1.dll` 및 `COMData2.dll` 생성 `OfficeApp.exe`합니다.</span><span class="sxs-lookup"><span data-stu-id="cf8c1-153">The following code compiles source file `OfficeApp.vb` and reference assemblies from `COMData1.dll` and `COMData2.dll` to produce `OfficeApp.exe`.</span></span>  
  
```vb  
vbc /link:COMData1.dll,COMData2.dll /out:OfficeApp.exe OfficeApp.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="cf8c1-154">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cf8c1-154">See Also</span></span>  
 <span data-ttu-id="cf8c1-155">[Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="cf8c1-155">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="cf8c1-156"> [연습: 관리 되는 어셈블리의 형식 포함](http://msdn.microsoft.com/library/b28ec92c-1867-4847-95c0-61adfe095e21) </span><span class="sxs-lookup"><span data-stu-id="cf8c1-156"> [Walkthrough: Embedding Types from Managed Assemblies](http://msdn.microsoft.com/library/b28ec92c-1867-4847-95c0-61adfe095e21) </span></span>  
<span data-ttu-id="cf8c1-157"> [/reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md) </span><span class="sxs-lookup"><span data-stu-id="cf8c1-157"> [/reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md) </span></span>  
<span data-ttu-id="cf8c1-158"> [/noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md) </span><span class="sxs-lookup"><span data-stu-id="cf8c1-158"> [/noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md) </span></span>  
<span data-ttu-id="cf8c1-159"> [/libpath](../../../visual-basic/reference/command-line-compiler/libpath.md) </span><span class="sxs-lookup"><span data-stu-id="cf8c1-159"> [/libpath](../../../visual-basic/reference/command-line-compiler/libpath.md) </span></span>  
<span data-ttu-id="cf8c1-160"> [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span><span class="sxs-lookup"><span data-stu-id="cf8c1-160"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span></span>  
<span data-ttu-id="cf8c1-161"> [COM Interop 소개](../../../visual-basic/programming-guide/com-interop/introduction-to-com-interop.md)</span><span class="sxs-lookup"><span data-stu-id="cf8c1-161"> [Introduction to COM Interop](../../../visual-basic/programming-guide/com-interop/introduction-to-com-interop.md)</span></span>
