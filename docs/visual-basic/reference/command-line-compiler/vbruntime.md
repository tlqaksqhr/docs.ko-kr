---
title: /vbruntime
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbruntime
- /vbruntime
helpviewer_keywords:
- vbruntime compiler option [Visual Basic]
- -vbruntime compiler option [Visual Basic]
- /vbruntime compiler option [Visual Basic]
ms.assetid: 1aa0239e-511a-4c29-957d-fd72877b350a
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: dda8ea7285a748bac53e30af8bd7a60099fe7411
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="vbruntime"></a><span data-ttu-id="468fe-102">/vbruntime</span><span class="sxs-lookup"><span data-stu-id="468fe-102">/vbruntime</span></span>
<span data-ttu-id="468fe-103">컴파일러에서 Visual Basic 런타임 라이브러리에 대한 참조 없이 컴파일하거나 특정 런타임 라이브러리를 참조하여 컴파일하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="468fe-103">Specifies that the compiler should compile without a reference to the Visual Basic Runtime Library, or with a reference to a specific runtime library.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="468fe-104">구문</span><span class="sxs-lookup"><span data-stu-id="468fe-104">Syntax</span></span>  
  
```  
/vbruntime:{ - | + | * | path }  
```  
  
## <a name="arguments"></a><span data-ttu-id="468fe-105">인수</span><span class="sxs-lookup"><span data-stu-id="468fe-105">Arguments</span></span>  
 \-  
 <span data-ttu-id="468fe-106">Visual Basic 런타임 라이브러리에 대 한 참조 없이 컴파일하십시오.</span><span class="sxs-lookup"><span data-stu-id="468fe-106">Compile without a reference to the Visual Basic Runtime Library.</span></span>  
  
 \+  
 <span data-ttu-id="468fe-107">기본 Visual Basic 런타임 라이브러리에 대 한 참조를 사용 하 여 컴파일하십시오.</span><span class="sxs-lookup"><span data-stu-id="468fe-107">Compile with a reference to the default Visual Basic Runtime Library.</span></span>  
  
 \*  
 <span data-ttu-id="468fe-108">Visual Basic 런타임 라이브러리에 대 한 참조 없이 컴파일하고 어셈블리를 Visual Basic 런타임 라이브러리에서 core 기능을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="468fe-108">Compile without a reference to the Visual Basic Runtime Library, and embed core functionality from the Visual Basic Runtime Library into the assembly.</span></span>  
  
 `path`  
 <span data-ttu-id="468fe-109">지정된 된 라이브러리 (DLL)에 대 한 참조를 사용 하 여 컴파일하십시오.</span><span class="sxs-lookup"><span data-stu-id="468fe-109">Compile with a reference to the specified library (DLL).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="468fe-110">설명</span><span class="sxs-lookup"><span data-stu-id="468fe-110">Remarks</span></span>  
 <span data-ttu-id="468fe-111">`/vbruntime` 컴파일러 옵션을 사용 하면 컴파일러는 Visual Basic 런타임 라이브러리에 대 한 참조 없이 컴파일하도록 할지 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="468fe-111">The `/vbruntime` compiler option enables you to specify that the compiler should compile without a reference to the Visual Basic Runtime Library.</span></span> <span data-ttu-id="468fe-112">Visual Basic 런타임 라이브러리에 대 한 참조 없이 컴파일하는 경우 Visual Basic 런타임 도우미에 대 한 호출을 생성 하는 코드 또는 언어 구문에 대해 오류 또는 경고가 기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="468fe-112">If you compile without a reference to the Visual Basic Runtime Library, errors or warnings are logged on code or language constructs that generate a call to a Visual Basic runtime helper.</span></span> <span data-ttu-id="468fe-113">(A *Visual Basic 런타임 도우미* 는 특정 언어 의미 체계를 실행 하는 런타임 시 호출 되는 Microsoft.VisualBasic.dll에 정의 된 함수입니다.)</span><span class="sxs-lookup"><span data-stu-id="468fe-113">(A *Visual Basic runtime helper* is a function defined in Microsoft.VisualBasic.dll that is called at runtime to execute a specific language semantic.)</span></span>  
  
 <span data-ttu-id="468fe-114">`/vbruntime+` 옵션 생성 되지 않았을 때 발생 하는 동작과 같습니다 `/vbruntime` 스위치를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="468fe-114">The `/vbruntime+` option produces the same behavior that occurs if no `/vbruntime` switch is specified.</span></span> <span data-ttu-id="468fe-115">사용할 수는 `/vbruntime+` 이전 재정의 하는 옵션 `/vbruntime` 스위치입니다.</span><span class="sxs-lookup"><span data-stu-id="468fe-115">You can use the `/vbruntime+` option to override previous `/vbruntime` switches.</span></span>  
  
 <span data-ttu-id="468fe-116">대부분의 개체는 `My` 형식을 사용할 수 없는 사용 하는 경우는 `/vbruntime-` 또는 `vbruntime:``path` 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="468fe-116">Most objects of the `My` type are unavailable when you use the `/vbruntime-` or `vbruntime:``path` options.</span></span>  
  
## <a name="embedding-visual-basic-runtime-core-functionality"></a><span data-ttu-id="468fe-117">Visual Basic 런타임 핵심 기능을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="468fe-117">Embedding Visual Basic Runtime core functionality</span></span>  
 <span data-ttu-id="468fe-118">`/vbruntime*` 옵션을 사용 하면 런타임 라이브러리에 대 한 참조 없이 컴파일할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="468fe-118">The `/vbruntime*` option enables you to compile without a reference to a runtime library.</span></span> <span data-ttu-id="468fe-119">대신, Visual Basic 런타임 라이브러리의 핵심 기능을 사용자 어셈블리에 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="468fe-119">Instead, core functionality from the Visual Basic Runtime Library is embedded in the user assembly.</span></span> <span data-ttu-id="468fe-120">응용 프로그램이 Visual Basic 런타임에 포함 하지 않는 플랫폼에서 실행 하는 경우이 옵션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="468fe-120">You can use this option if your application runs on platforms that do not contain the Visual Basic runtime.</span></span>  
  
 <span data-ttu-id="468fe-121">다음 런타임 멤버가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="468fe-121">The following runtime members are embedded:</span></span>  
  
-   <span data-ttu-id="468fe-122"><xref:Microsoft.VisualBasic.CompilerServices.Conversions> 클래스</span><span class="sxs-lookup"><span data-stu-id="468fe-122"><xref:Microsoft.VisualBasic.CompilerServices.Conversions> class</span></span>  
  
-   <span data-ttu-id="468fe-123"><xref:Microsoft.VisualBasic.Strings.AscW%28System.Char%29> 메서드</span><span class="sxs-lookup"><span data-stu-id="468fe-123"><xref:Microsoft.VisualBasic.Strings.AscW%28System.Char%29> method</span></span>  
  
-   <span data-ttu-id="468fe-124"><xref:Microsoft.VisualBasic.Strings.AscW%28System.String%29> 메서드</span><span class="sxs-lookup"><span data-stu-id="468fe-124"><xref:Microsoft.VisualBasic.Strings.AscW%28System.String%29> method</span></span>  
  
-   <span data-ttu-id="468fe-125"><xref:Microsoft.VisualBasic.Strings.ChrW%28System.Int32%29> 메서드</span><span class="sxs-lookup"><span data-stu-id="468fe-125"><xref:Microsoft.VisualBasic.Strings.ChrW%28System.Int32%29> method</span></span>  
  
-   <span data-ttu-id="468fe-126"><xref:Microsoft.VisualBasic.Constants.vbBack>상수</span><span class="sxs-lookup"><span data-stu-id="468fe-126"><xref:Microsoft.VisualBasic.Constants.vbBack> constant</span></span>  
  
-   <span data-ttu-id="468fe-127"><xref:Microsoft.VisualBasic.Constants.vbCr>상수</span><span class="sxs-lookup"><span data-stu-id="468fe-127"><xref:Microsoft.VisualBasic.Constants.vbCr> constant</span></span>  
  
-   <span data-ttu-id="468fe-128"><xref:Microsoft.VisualBasic.Constants.vbCrLf>상수</span><span class="sxs-lookup"><span data-stu-id="468fe-128"><xref:Microsoft.VisualBasic.Constants.vbCrLf> constant</span></span>  
  
-   <span data-ttu-id="468fe-129"><xref:Microsoft.VisualBasic.Constants.vbFormFeed>상수</span><span class="sxs-lookup"><span data-stu-id="468fe-129"><xref:Microsoft.VisualBasic.Constants.vbFormFeed> constant</span></span>  
  
-   <span data-ttu-id="468fe-130"><xref:Microsoft.VisualBasic.Constants.vbLf>상수</span><span class="sxs-lookup"><span data-stu-id="468fe-130"><xref:Microsoft.VisualBasic.Constants.vbLf> constant</span></span>  
  
-   <span data-ttu-id="468fe-131"><xref:Microsoft.VisualBasic.Constants.vbNewLine>상수</span><span class="sxs-lookup"><span data-stu-id="468fe-131"><xref:Microsoft.VisualBasic.Constants.vbNewLine> constant</span></span>  
  
-   <span data-ttu-id="468fe-132"><xref:Microsoft.VisualBasic.Constants.vbNullChar>상수</span><span class="sxs-lookup"><span data-stu-id="468fe-132"><xref:Microsoft.VisualBasic.Constants.vbNullChar> constant</span></span>  
  
-   <span data-ttu-id="468fe-133"><xref:Microsoft.VisualBasic.Constants.vbNullString>상수</span><span class="sxs-lookup"><span data-stu-id="468fe-133"><xref:Microsoft.VisualBasic.Constants.vbNullString> constant</span></span>  
  
-   <span data-ttu-id="468fe-134"><xref:Microsoft.VisualBasic.Constants.vbTab>상수</span><span class="sxs-lookup"><span data-stu-id="468fe-134"><xref:Microsoft.VisualBasic.Constants.vbTab> constant</span></span>  
  
-   <span data-ttu-id="468fe-135"><xref:Microsoft.VisualBasic.Constants.vbVerticalTab>상수</span><span class="sxs-lookup"><span data-stu-id="468fe-135"><xref:Microsoft.VisualBasic.Constants.vbVerticalTab> constant</span></span>  
  
-   <span data-ttu-id="468fe-136">일부 개체는 `My` 유형</span><span class="sxs-lookup"><span data-stu-id="468fe-136">Some objects of the `My` type</span></span>  
  
 <span data-ttu-id="468fe-137">사용 하 여 컴파일하는 경우는 `/vbruntime*` 옵션과 코드 핵심 기능이 포함 되어 있지 않으면 Visual Basic 런타임 라이브러리에서 멤버 참조, 컴파일러는 멤버를 사용할 수 있는지를 나타내는 오류를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="468fe-137">If you compile using the `/vbruntime*` option and your code references a member from the Visual Basic Runtime Library that is not embedded with the core functionality, the compiler returns an error that indicates that the member is not available.</span></span>  
  
## <a name="referencing-a-specified-library"></a><span data-ttu-id="468fe-138">지정된 된 라이브러리 참조</span><span class="sxs-lookup"><span data-stu-id="468fe-138">Referencing a specified library</span></span>  
 <span data-ttu-id="468fe-139">사용할 수는 `path` 인수를 기본 Visual Basic 런타임 라이브러리 대신 사용자 지정 런타임 라이브러리에 대 한 참조를 사용 하 여 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="468fe-139">You can use the `path` argument to compile with a reference to a custom runtime library instead of the default Visual Basic Runtime Library.</span></span>  
  
 <span data-ttu-id="468fe-140">경우에 대 한 값은 `path` 인수는 DLL에는 정규화 된 경로, 컴파일러에서 런타임 라이브러리와 해당 파일을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="468fe-140">If the value for the `path` argument is a fully qualified path to a DLL, the compiler will use that file as the runtime library.</span></span> <span data-ttu-id="468fe-141">경우에 대 한 값은 `path` 인수가 DLL에는 정규화 된 경로, Visual Basic 컴파일러 현재 폴더에서 식별 된 DLL에 대 한 가장 먼저 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="468fe-141">If the value for the `path` argument is not a fully qualified path to a DLL, the Visual Basic compiler will search for the identified DLL in the current folder first.</span></span> <span data-ttu-id="468fe-142">사용 하 여 지정 된 경로에서 검색 한 다음는 [/sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md) 컴파일러 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="468fe-142">It will then search in the path that you have specified by using the [/sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md) compiler option.</span></span> <span data-ttu-id="468fe-143">경우는 `/sdkpath` 컴파일러 옵션이 사용 되지 않으면, 컴파일러는.NET Framework 폴더에 식별 된 DLL에 대 한 검색 (`%systemroot%\Microsoft.NET\Framework\versionNumber`).</span><span class="sxs-lookup"><span data-stu-id="468fe-143">If the `/sdkpath` compiler option is not used, the compiler will search for the identified DLL in the .NET Framework folder (`%systemroot%\Microsoft.NET\Framework\versionNumber`).</span></span>  
  
## <a name="example"></a><span data-ttu-id="468fe-144">예제</span><span class="sxs-lookup"><span data-stu-id="468fe-144">Example</span></span>  
 <span data-ttu-id="468fe-145">사용 하는 방법을 보여 주는 다음 예제는 `/vbruntime` 옵션을 사용자 지정 라이브러리에 대 한 참조를 사용 하 여 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="468fe-145">The following example shows how to use the `/vbruntime` option to compile with a reference to a custom library.</span></span>  
  
```  
vbc /vbruntime:C:\VBLibraries\CustomVBLibrary.dll  
```  
  
## <a name="see-also"></a><span data-ttu-id="468fe-146">참고 항목</span><span class="sxs-lookup"><span data-stu-id="468fe-146">See Also</span></span>  
 [<span data-ttu-id="468fe-147">Visual Basic 코어 – Visual Studio 2010 s p 1의 새로운 컴파일 모드</span><span class="sxs-lookup"><span data-stu-id="468fe-147">Visual Basic Core – New compilation mode in Visual Studio 2010 SP1</span></span>](http://blogs.msdn.com/b/vbteam/archive/2011/01/10/vb-core-new-compilation-mode-in-visual-studio-2010-sp1.aspx)  
 [<span data-ttu-id="468fe-148">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="468fe-148">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="468fe-149">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="468fe-149">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [<span data-ttu-id="468fe-150">/sdkpath</span><span class="sxs-lookup"><span data-stu-id="468fe-150">/sdkpath</span></span>](../../../visual-basic/reference/command-line-compiler/sdkpath.md)
