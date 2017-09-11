---
title: "/vbruntime | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbruntime
- /vbruntime
dev_langs:
- VB
helpviewer_keywords:
- vbruntime compiler option [Visual Basic]
- -vbruntime compiler option [Visual Basic]
- /vbruntime compiler option [Visual Basic]
ms.assetid: 1aa0239e-511a-4c29-957d-fd72877b350a
caps.latest.revision: 17
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
ms.openlocfilehash: cb07ed8c2f6070079cc51c290ff5a61305c5a5d3
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="vbruntime"></a><span data-ttu-id="ae714-102">/vbruntime</span><span class="sxs-lookup"><span data-stu-id="ae714-102">/vbruntime</span></span>
<span data-ttu-id="ae714-103">컴파일러에서 Visual Basic 런타임 라이브러리에 대한 참조 없이 컴파일하거나 특정 런타임 라이브러리를 참조하여 컴파일하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ae714-103">Specifies that the compiler should compile without a reference to the Visual Basic Runtime Library, or with a reference to a specific runtime library.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae714-104">구문</span><span class="sxs-lookup"><span data-stu-id="ae714-104">Syntax</span></span>  
  
```  
/vbruntime:{ - | + | * | path }  
```  
  
## <a name="arguments"></a><span data-ttu-id="ae714-105">인수</span><span class="sxs-lookup"><span data-stu-id="ae714-105">Arguments</span></span>  
 \-  
 <span data-ttu-id="ae714-106">Visual Basic 런타임 라이브러리에 대 한 참조 없이 컴파일하십시오.</span><span class="sxs-lookup"><span data-stu-id="ae714-106">Compile without a reference to the Visual Basic Runtime Library.</span></span>  
  
 \+  
 <span data-ttu-id="ae714-107">기본 Visual Basic 런타임 라이브러리에 대 한 참조를 사용 하 여 컴파일하십시오.</span><span class="sxs-lookup"><span data-stu-id="ae714-107">Compile with a reference to the default Visual Basic Runtime Library.</span></span>  
  
 \*  
 <span data-ttu-id="ae714-108">Visual Basic 런타임 라이브러리에 대 한 참조 없이 컴파일하고 어셈블리를 Visual Basic 런타임 라이브러리에서 핵심 기능을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae714-108">Compile without a reference to the Visual Basic Runtime Library, and embed core functionality from the Visual Basic Runtime Library into the assembly.</span></span>  
  
 `path`  
 <span data-ttu-id="ae714-109">지정된 된 라이브러리 (DLL)에 대 한 참조를 사용 하 여 컴파일하십시오.</span><span class="sxs-lookup"><span data-stu-id="ae714-109">Compile with a reference to the specified library (DLL).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ae714-110">주의</span><span class="sxs-lookup"><span data-stu-id="ae714-110">Remarks</span></span>  
 <span data-ttu-id="ae714-111">`/vbruntime` 컴파일러 옵션을 사용 하면 컴파일러는 Visual Basic 런타임 라이브러리에 대 한 참조 없이 컴파일하도록를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae714-111">The `/vbruntime` compiler option enables you to specify that the compiler should compile without a reference to the Visual Basic Runtime Library.</span></span> <span data-ttu-id="ae714-112">Visual Basic 런타임 라이브러리에 대 한 참조 없이 컴파일하는 경우 Visual Basic 런타임 도우미에 대 한 호출을 생성 하는 코드 또는 언어 구문에 대해 오류 또는 경고가 기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae714-112">If you compile without a reference to the Visual Basic Runtime Library, errors or warnings are logged on code or language constructs that generate a call to a Visual Basic runtime helper.</span></span> <span data-ttu-id="ae714-113">(A *Visual Basic 런타임 도우미* 특정 언어 의미 체계를 실행 하는 런타임 시 호출 되는 Microsoft.VisualBasic.dll에 정의 된 함수입니다.)</span><span class="sxs-lookup"><span data-stu-id="ae714-113">(A *Visual Basic runtime helper* is a function defined in Microsoft.VisualBasic.dll that is called at runtime to execute a specific language semantic.)</span></span>  
  
 <span data-ttu-id="ae714-114">`/vbruntime+` 되지 않았을 때 발생 하는 동일한 동작을 생성 하는 옵션 `/vbruntime` 스위치를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae714-114">The `/vbruntime+` option produces the same behavior that occurs if no `/vbruntime` switch is specified.</span></span> <span data-ttu-id="ae714-115">사용할 수는 `/vbruntime+` 이전 재정의 하는 옵션 `/vbruntime` 스위치입니다.</span><span class="sxs-lookup"><span data-stu-id="ae714-115">You can use the `/vbruntime+` option to override previous `/vbruntime` switches.</span></span>  
  
 <span data-ttu-id="ae714-116">대부분의 개체는 `My` 형식을 사용할 수 없는 사용 하는 경우는 `/vbruntime-` 또는 `vbruntime:``path` 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="ae714-116">Most objects of the `My` type are unavailable when you use the `/vbruntime-` or `vbruntime:``path` options.</span></span>  
  
## <a name="embedding-visual-basic-runtime-core-functionality"></a><span data-ttu-id="ae714-117">Visual Basic 런타임 핵심 기능을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="ae714-117">Embedding Visual Basic Runtime core functionality</span></span>  
 <span data-ttu-id="ae714-118">`/vbruntime*` 옵션을 사용 하면 런타임 라이브러리에 대 한 참조 없이 컴파일할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae714-118">The `/vbruntime*` option enables you to compile without a reference to a runtime library.</span></span> <span data-ttu-id="ae714-119">대신, Visual Basic 런타임 라이브러리의 핵심 기능을 사용자 어셈블리에 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae714-119">Instead, core functionality from the Visual Basic Runtime Library is embedded in the user assembly.</span></span> <span data-ttu-id="ae714-120">응용 프로그램이 Visual Basic 런타임 포함 하지 않는 플랫폼에서 실행 하는 경우이 옵션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae714-120">You can use this option if your application runs on platforms that do not contain the Visual Basic runtime.</span></span>  
  
 <span data-ttu-id="ae714-121">다음 런타임 멤버가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae714-121">The following runtime members are embedded:</span></span>  
  
-   <span data-ttu-id="ae714-122"><xref:Microsoft.VisualBasic.CompilerServices.Conversions>클래스</xref:Microsoft.VisualBasic.CompilerServices.Conversions></span><span class="sxs-lookup"><span data-stu-id="ae714-122"><xref:Microsoft.VisualBasic.CompilerServices.Conversions> class</span></span>  
  
-   <span data-ttu-id="ae714-123"><xref:Microsoft.VisualBasic.Strings.AscW%28System.Char%29>메서드</xref:Microsoft.VisualBasic.Strings.AscW%28System.Char%29></span><span class="sxs-lookup"><span data-stu-id="ae714-123"><xref:Microsoft.VisualBasic.Strings.AscW%28System.Char%29> method</span></span>  
  
-   <span data-ttu-id="ae714-124"><xref:Microsoft.VisualBasic.Strings.AscW%28System.String%29>메서드</xref:Microsoft.VisualBasic.Strings.AscW%28System.String%29></span><span class="sxs-lookup"><span data-stu-id="ae714-124"><xref:Microsoft.VisualBasic.Strings.AscW%28System.String%29> method</span></span>  
  
-   <span data-ttu-id="ae714-125"><xref:Microsoft.VisualBasic.Strings.ChrW%28System.Int32%29>메서드</xref:Microsoft.VisualBasic.Strings.ChrW%28System.Int32%29></span><span class="sxs-lookup"><span data-stu-id="ae714-125"><xref:Microsoft.VisualBasic.Strings.ChrW%28System.Int32%29> method</span></span>  
  
-   <span data-ttu-id="ae714-126"><xref:Microsoft.VisualBasic.Constants.vbBack>상수</xref:Microsoft.VisualBasic.Constants.vbBack></span><span class="sxs-lookup"><span data-stu-id="ae714-126"><xref:Microsoft.VisualBasic.Constants.vbBack> constant</span></span>  
  
-   <span data-ttu-id="ae714-127"><xref:Microsoft.VisualBasic.Constants.vbCr>상수</xref:Microsoft.VisualBasic.Constants.vbCr></span><span class="sxs-lookup"><span data-stu-id="ae714-127"><xref:Microsoft.VisualBasic.Constants.vbCr> constant</span></span>  
  
-   <span data-ttu-id="ae714-128"><xref:Microsoft.VisualBasic.Constants.vbCrLf>상수</xref:Microsoft.VisualBasic.Constants.vbCrLf></span><span class="sxs-lookup"><span data-stu-id="ae714-128"><xref:Microsoft.VisualBasic.Constants.vbCrLf> constant</span></span>  
  
-   <span data-ttu-id="ae714-129"><xref:Microsoft.VisualBasic.Constants.vbFormFeed>상수</xref:Microsoft.VisualBasic.Constants.vbFormFeed></span><span class="sxs-lookup"><span data-stu-id="ae714-129"><xref:Microsoft.VisualBasic.Constants.vbFormFeed> constant</span></span>  
  
-   <span data-ttu-id="ae714-130"><xref:Microsoft.VisualBasic.Constants.vbLf>상수</xref:Microsoft.VisualBasic.Constants.vbLf></span><span class="sxs-lookup"><span data-stu-id="ae714-130"><xref:Microsoft.VisualBasic.Constants.vbLf> constant</span></span>  
  
-   <span data-ttu-id="ae714-131"><xref:Microsoft.VisualBasic.Constants.vbNewLine>상수</xref:Microsoft.VisualBasic.Constants.vbNewLine></span><span class="sxs-lookup"><span data-stu-id="ae714-131"><xref:Microsoft.VisualBasic.Constants.vbNewLine> constant</span></span>  
  
-   <span data-ttu-id="ae714-132"><xref:Microsoft.VisualBasic.Constants.vbNullChar>상수</xref:Microsoft.VisualBasic.Constants.vbNullChar></span><span class="sxs-lookup"><span data-stu-id="ae714-132"><xref:Microsoft.VisualBasic.Constants.vbNullChar> constant</span></span>  
  
-   <span data-ttu-id="ae714-133"><xref:Microsoft.VisualBasic.Constants.vbNullString>상수</xref:Microsoft.VisualBasic.Constants.vbNullString></span><span class="sxs-lookup"><span data-stu-id="ae714-133"><xref:Microsoft.VisualBasic.Constants.vbNullString> constant</span></span>  
  
-   <span data-ttu-id="ae714-134"><xref:Microsoft.VisualBasic.Constants.vbTab>상수</xref:Microsoft.VisualBasic.Constants.vbTab></span><span class="sxs-lookup"><span data-stu-id="ae714-134"><xref:Microsoft.VisualBasic.Constants.vbTab> constant</span></span>  
  
-   <span data-ttu-id="ae714-135"><xref:Microsoft.VisualBasic.Constants.vbVerticalTab>상수</xref:Microsoft.VisualBasic.Constants.vbVerticalTab></span><span class="sxs-lookup"><span data-stu-id="ae714-135"><xref:Microsoft.VisualBasic.Constants.vbVerticalTab> constant</span></span>  
  
-   <span data-ttu-id="ae714-136">일부 개체는 `My` 형식</span><span class="sxs-lookup"><span data-stu-id="ae714-136">Some objects of the `My` type</span></span>  
  
 <span data-ttu-id="ae714-137">사용 하 여 컴파일하는 경우는 `/vbruntime*` 옵션 및 코드의 핵심 기능이 포함 되지 않은 Visual Basic 런타임 라이브러리에서 멤버 참조, 컴파일러는 멤버를 사용할 수 없다는 나타내는 오류를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae714-137">If you compile using the `/vbruntime*` option and your code references a member from the Visual Basic Runtime Library that is not embedded with the core functionality, the compiler returns an error that indicates that the member is not available.</span></span>  
  
## <a name="referencing-a-specified-library"></a><span data-ttu-id="ae714-138">지정된 된 라이브러리를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="ae714-138">Referencing a specified library</span></span>  
 <span data-ttu-id="ae714-139">사용할 수는 `path` 인수를 기본 Visual Basic 런타임 라이브러리 대신 사용자 지정 런타임 라이브러리에 대 한 참조를 사용 하 여 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="ae714-139">You can use the `path` argument to compile with a reference to a custom runtime library instead of the default Visual Basic Runtime Library.</span></span>  
  
 <span data-ttu-id="ae714-140">경우에 대 한 값은 `path` 인수는 DLL에는 정규화 된 경로, 컴파일러는 런타임 라이브러리와 해당 파일을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae714-140">If the value for the `path` argument is a fully qualified path to a DLL, the compiler will use that file as the runtime library.</span></span> <span data-ttu-id="ae714-141">경우에 대 한 값은 `path` 인수를 DLL로 정규화 된 경로가 아닙니다, Visual Basic 컴파일러가 현재 폴더에서 식별 된 DLL에 대 한 가장 먼저 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae714-141">If the value for the `path` argument is not a fully qualified path to a DLL, the Visual Basic compiler will search for the identified DLL in the current folder first.</span></span> <span data-ttu-id="ae714-142">사용 하 여 지정 된 경로에서 검색 한 다음는 [/sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md) 컴파일러 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="ae714-142">It will then search in the path that you have specified by using the [/sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md) compiler option.</span></span> <span data-ttu-id="ae714-143">하는 경우는 `/sdkpath` 컴파일러 옵션이 사용 되지 않으면, 컴파일러는.NET Framework 폴더에 식별 된 DLL에 대 한 검색 (`%systemroot%\Microsoft.NET\Framework\versionNumber`).</span><span class="sxs-lookup"><span data-stu-id="ae714-143">If the `/sdkpath` compiler option is not used, the compiler will search for the identified DLL in the .NET Framework folder (`%systemroot%\Microsoft.NET\Framework\versionNumber`).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ae714-144">예제</span><span class="sxs-lookup"><span data-stu-id="ae714-144">Example</span></span>  
 <span data-ttu-id="ae714-145">다음 예제를 사용 하는 방법을 보여 줍니다는 `/vbruntime` 옵션을 사용자 지정 라이브러리에 대 한 참조를 사용 하 여 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="ae714-145">The following example shows how to use the `/vbruntime` option to compile with a reference to a custom library.</span></span>  
  
```  
vbc /vbruntime:C:\VBLibraries\CustomVBLibrary.dll  
```  
  
## <a name="see-also"></a><span data-ttu-id="ae714-146">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ae714-146">See Also</span></span>  
 <span data-ttu-id="ae714-147">[Visual Basic 코어 – Visual Studio 2010 s p 1의 새로운 컴파일 모드](http://blogs.msdn.com/b/vbteam/archive/2011/01/10/vb-core-new-compilation-mode-in-visual-studio-2010-sp1.aspx) </span><span class="sxs-lookup"><span data-stu-id="ae714-147">[Visual Basic Core – New compilation mode in Visual Studio 2010 SP1](http://blogs.msdn.com/b/vbteam/archive/2011/01/10/vb-core-new-compilation-mode-in-visual-studio-2010-sp1.aspx) </span></span>  
<span data-ttu-id="ae714-148"> [Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="ae714-148"> [Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="ae714-149"> [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span><span class="sxs-lookup"><span data-stu-id="ae714-149"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span></span>  
<span data-ttu-id="ae714-150"> [/sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md)</span><span class="sxs-lookup"><span data-stu-id="ae714-150"> [/sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md)</span></span>
